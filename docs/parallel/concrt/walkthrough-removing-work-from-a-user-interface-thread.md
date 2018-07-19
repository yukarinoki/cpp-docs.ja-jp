---
title: 'チュートリアル: ユーザー インターフェイス スレッドからの処理の除去 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0502ce728c35b08d927cea48ee5b82756980aec5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694288"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>チュートリアル: ユーザー インターフェイス スレッドからの処理の除去
このドキュメントでは、同時実行ランタイムを使用して、Microsoft Foundation Classes (MFC) アプリケーションをワーカー スレッドのユーザー インターフェイス (UI) スレッドで実行される作業を移動する方法を示します。 このドキュメントでは、時間のかかる描画操作のパフォーマンスを向上させる方法も示します。  
  
 UI スレッドから作業を削除するには、ブロッキング操作をオフロードすることにより、たとえば、ワーカー スレッドへの描画、応答性が向上、アプリケーションのです。 このチュートリアルでは、長いブロッキング操作を示すためにマンデルブロ フラクタルを生成する描画ルーチンを使用します。 マンデルブロ フラクタルの生成は、各ピクセルの計算が他のすべての計算に依存しないために、並列化に適した候補ではもです。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを開始する前に、次のトピックを参照してください。  
  
-   [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)  
  
-   [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)  
  
-   [PPL における取り消し処理](cancellation-in-the-ppl.md)  
  
 また MFC アプリケーションの開発の基本を理解することをお勧めして[!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]このチュートリアルを開始する前にします。 MFC の詳細については、次を参照してください。 [MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)です。 詳細については[!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]を参照してください[GDI +](https://msdn.microsoft.com/en-us/library/windows/desktop/ms533798)です。  
  
##  <a name="top"></a> セクション  
 このチュートリアルは、次のセクションで構成されています。  
  
-   [MFC アプリケーションの作成](#application)  
  
-   [マンデルブロ アプリケーションの逐次バージョンを実装します。](#serial)  
  
-   [ユーザー インターフェイス スレッドから作業を削除します。](#removing-work)  
  
-   [描画パフォーマンスの向上](#performance)  
  
-   [キャンセルのサポートの追加](#cancellation)  
  
##  <a name="application"></a> MFC アプリケーションの作成  
 このセクションでは、基本の MFC アプリケーションを作成する方法について説明します。  
  
### <a name="to-create-a-visual-c-mfc-application"></a>Visual C MFC アプリケーションを作成するには  
  
1.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
2.  **新しいプロジェクト**] ダイアログ ボックスで、**インストールされたテンプレート**ペインで、 **Visual C**、[、**テンプレート**ペインで、**MFC アプリケーション**です。 たとえば、プロジェクトの名前を入力`Mandelbrot`、順にクリック **[ok]** を表示する、 **MFC アプリケーション ウィザード**です。  
  
3.  **アプリケーションの種類**ペインで、 **1 つのドキュメント**です。 いることを確認、**ドキュメント/ビュー アーキテクチャ サポート** チェック ボックスがオフになっています。  
  
4.  をクリックして**完了**、プロジェクトを作成し、閉じます、 **MFC アプリケーション ウィザード**です。  
  
     アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド** メニューのをクリックして**ソリューションのビルド**です。 アプリケーションが正常にビルドされたアプリケーションを実行 をクリックして**デバッグの開始**上、**デバッグ**メニュー。  
  
##  <a name="serial"></a> マンデルブロ アプリケーションの逐次バージョンを実装します。  
 このセクションでは、マンデルブロ フラクタルを描画する方法について説明します。 このバージョンを描画するマンデルブロ フラクタル、 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [ビットマップ](https://msdn.microsoft.com/library/ms534420.aspx)オブジェクトし、クライアント ウィンドウにそのビットマップの内容をコピーします。  
  
#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>マンデルブロ アプリケーションの逐次バージョンを実装するには  
  
1.  Stdafx.h で次のコードを追加`#include`ディレクティブ。  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  ChildView.h の後に、`pragma`ディレクティブ、定義、`BitmapPtr`型です。 `BitmapPtr`型へのポインターを使用する、`Bitmap`を複数のコンポーネントで共有するオブジェクト。 `Bitmap`のコンポーネントから参照されなくなったときにオブジェクトを削除します。  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  ChildView.h、次のコードを追加、`protected`のセクションで、`CChildView`クラス。  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  ChildView.cpp、コメント アウトするか、次の行を削除します。  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     デバッグ ビルドで、この手順により、アプリケーションを使用して、`DEBUG_NEW`アロケーターと互換性がありません[!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]です。  
  
5.  ChildView.cpp で追加、`using`ディレクティブを`Gdiplus`名前空間。  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  コンス トラクターとデストラクターの次のコードを追加、`CChildView`クラスを初期化およびシャット ダウン[!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]です。  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  `CChildView::DrawMandelbrot` メソッドを実装します。 このメソッドを指定したマンデルブロ フラクタルを描画する`Bitmap`オブジェクト。  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  `CChildView::OnPaint` メソッドを実装します。 このメソッドを呼び出す`CChildView::DrawMandelbrot`の内容をコピーし、`Bitmap`ウィンドウへのオブジェクト。  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. ビルドおよび実行することによって、アプリケーションが正常に更新されたことを確認します。  
  
 マンデルブロ アプリケーションの結果を次の図に示します。  
  
 ![マンデルブロ アプリケーション](../../parallel/concrt/media/mandelbrot.png "マンデルブロ")  
  
 各ピクセルの計算は計算コストが高いため、UI スレッドは、全体的な計算が終了するまで他のメッセージを処理できません。 これにより、アプリケーションの応答性が低下する可能性があります。 ただし、UI スレッドから作業を削除することによってこの問題を軽減することができます。  
  
 [[トップ](#top)]  
  
##  <a name="removing-work"></a> UI スレッドからの処理の除去  
 このセクションでは、マンデルブロ アプリケーションの UI スレッドから描画処理を削除する方法を示します。 UI スレッドから描画処理をワーカー スレッドに移動して、UI スレッドはワーカー スレッドがバック グラウンドで、イメージを生成するようにメッセージを処理できます。  
  
 同時実行ランタイムには、タスクを実行する 3 つの方法が用意されています:[タスク グループ](../../parallel/concrt/task-parallelism-concurrency-runtime.md)、[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)、および[軽量タスク](../../parallel/concrt/task-scheduler-concurrency-runtime.md)です。 UI スレッドから作業を削除するこれらのメカニズムのいずれかを使用できますが、この例では、 [concurrency::task_group](reference/task-group-class.md)オブジェクトをタスク グループは、キャンセルをサポートします。 このチュートリアルは、後に、クライアント ウィンドウをサイズ変更するとときに、実行される作業の量を削減して、ウィンドウが破棄されるときにクリーンアップを実行するキャンセルの機能を使用します。  
  
 またこの例では、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) UI スレッドとワーカー スレッドが相互通信が有効にするオブジェクト。 ワーカー スレッドは、イメージを生成へのポインターに送信、`Bitmap`オブジェクトを`unbounded_buffer`オブジェクトし、UI スレッドに描画メッセージをポストします。 UI スレッドを受信し、`unbounded_buffer`オブジェクト、`Bitmap`オブジェクトし、クライアント ウィンドウを描画します。  
  
#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>UI スレッドから描画処理を削除するには  
  
1.  Stdafx.h で次のコードを追加`#include`ディレクティブ。  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  ChildView.h で追加`task_group`と`unbounded_buffer`メンバー変数を`protected`のセクションで、`CChildView`クラスです。 `task_group` ; の描画を実行するタスクを保持するオブジェクト、`unbounded_buffer`オブジェクトが完了したマンデルブロ イメージを格納します。  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  ChildView.cpp で追加、`using`ディレクティブを`concurrency`名前空間。  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  

4.  `CChildView::DrawMandelbrot`メソッドの呼び出しの後に、 `Bitmap::UnlockBits`、呼び出し、 [concurrency::send](reference/concurrency-namespace-functions.md#send)関数に渡す、 `Bitmap` UI スレッドへのオブジェクト。 UI スレッドに描画メッセージを投稿し、クライアント領域を無効にします。  

  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  更新プログラム、`CChildView::OnPaint`メソッドを更新された受信`Bitmap`オブジェクトし、クライアント ウィンドウにイメージを描画します。  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     `CChildView::OnPaint`メソッドは、メッセージ バッファーのいずれかが存在しない場合、マンデルブロ イメージを生成するタスクを作成します。 メッセージ バッファーには含まれません、`Bitmap`ケースを別のウィンドウが、クライアント ウィンドウの前に移動すると、最初の描画メッセージなどのオブジェクト。  
  
6.  ビルドおよび実行することによって、アプリケーションが正常に更新されたことを確認します。  
  
 描画処理はバック グラウンドで実行されるため、UI が応答性の高いようになりました。  
  
 [[トップ](#top)]  
  
##  <a name="performance"></a> 描画パフォーマンスの向上  

 マンデルブロ フラクタルの生成では、並列化の候補は各ピクセルの計算が他のすべての計算に依存しないためです。 描画のプロシージャを並列化する変換、外側`for`ループ、`CChildView::DrawMandelbrot`メソッドへの呼び出しに、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムは、次のようにします。  

  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 ビットマップの各要素の計算とは無関係であるために、ビットマップのメモリにアクセスする描画操作を同期するためにはありません。 これにより、パフォーマンスの利用可能なプロセッサ数としてスケールを設定できます。  
  
 [[トップ](#top)]  
  
##  <a name="cancellation"></a> キャンセルのサポートの追加  
 このセクションでは、ウィンドウ サイズの変更を処理する方法と、ウィンドウが破棄されるときに、アクティブな描画タスクをキャンセルする方法について説明します。  
  
 ドキュメント[PPL における取り消し処理](cancellation-in-the-ppl.md)ランタイムでのキャンセルのしくみについて説明します。 キャンセルは協調的です。そのため、これは直ちに行われません。 取り消されたタスクを停止するには、ランタイムは、ランタイムにタスクからの後続の呼び出し中に内部例外をスローします。 前のセクションを使用する方法を示しています、`parallel_for`描画タスクのパフォーマンスを向上するためのアルゴリズムです。 呼び出し`parallel_for`タスクを中止するランタイムを有効にでき、したがって作業をキャンセルします。  
  
### <a name="cancelling-active-tasks"></a>アクティブなタスクのキャンセル  
 マンデルブロ アプリケーション作成`Bitmap`の次元には、クライアント ウィンドウのサイズが一致するオブジェクト。 [クライアント] ウィンドウのサイズを変更するたびに、アプリケーションは新しいウィンドウのサイズのイメージを生成する、追加のバック グラウンド タスクを作成します。 アプリケーションでこれら中間的なイメージが必要ありません。最終的なウィンドウ サイズのイメージのみが必要です。 この追加作業を実行してから、アプリケーションを防ぐためには、メッセージ ハンドラーでアクティブな描画タスクを取り消すことができます、`WM_SIZE`と`WM_SIZING`ウィンドウのサイズは変更後のメッセージとし、再スケジュール図面動作します。  
  
 アクティブな描画タスクを取り消す場合に、ウィンドウのサイズが変更されるときを呼び出して、 [concurrency::task_group::cancel](reference/task-group-class.md#cancel)に対応するハンドラーのメソッド、`WM_SIZING`と`WM_SIZE`メッセージ。 ハンドラーを`WM_SIZE`呼び出しのメッセージも、 [concurrency::task_group::wait](reference/task-group-class.md#wait)メソッドすべてのアクティブなタスクを完了して、更新されたウィンドウのサイズに描画タスクを再スケジュールするを待つことです。  
  
 クライアント ウィンドウが破棄されるは、アクティブな描画タスクをキャンセルすることをお勧めします。 アクティブな描画タスクをキャンセルでは、以下のことワーカー スレッドのメッセージをポストしない UI スレッドに、クライアント ウィンドウが破棄された後になります。 アプリケーションのハンドラーでアクティブな描画タスクのキャンセル、`WM_DESTROY`メッセージ。  
  
### <a name="responding-to-cancellation"></a>取り消し処理に応答  
 `CChildView::DrawMandelbrot`描画タスクを実行するメソッドには、キャンセルに応答する必要があります。 ランタイムが例外をタスクのキャンセル処理を使用しているため、`CChildView::DrawMandelbrot`メソッドで例外セーフ メカニズムを使用しているすべてのリソースが正しくクリーンアップを保証する必要があります。 この例では、 *Resource Acquisition Is Initialization* (RAII) パターンをタスクが取り消された場合に、ビットマップのビットがロックいないことを保証します。  
  
##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>マンデルブロ アプリケーションで取り消し処理のサポートを追加するには  
  
1.  ChildView.h、内で、`protected`のセクションで、`CChildView`クラス、宣言を追加、 `OnSize`、 `OnSizing`、および`OnDestroy`メッセージ マップ関数。  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  ChildView.cpp でのハンドラーを含むメッセージ マップの変更、 `WM_SIZE`、 `WM_SIZING`、および`WM_DESTROY`メッセージ。  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  `CChildView::OnSizing` メソッドを実装します。 このメソッドは、既存の図面タスクをキャンセルします。  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  `CChildView::OnSize` メソッドを実装します。 このメソッドは、既存の図面のタスクをすべて取り消し、更新されたクライアント ウィンドウ サイズの場合は、新しい図面タスクを作成します。  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  `CChildView::OnDestroy` メソッドを実装します。 このメソッドは、既存の図面タスクをキャンセルします。  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  ChildView.cpp では、定義、`scope_guard`クラスは、RAII パターンを実装します。  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  次のコードを追加、`CChildView::DrawMandelbrot`メソッド呼び出しの後に`Bitmap::LockBits`:  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     このコードは、作成することでキャンセルを処理する`scope_guard`オブジェクト。 オブジェクトがスコープを離れたときに、ビットマップのビットがロック解除します。  
  
8.  最後の変更、`CChildView::DrawMandelbrot`を消去するメソッド、`scope_guard`オブジェクトのビットマップのビットがロックされた後は、UI スレッドにすべてのメッセージを送信する前にします。 これにより、UI スレッドは、ビットマップのビットがロック解除する前に更新されません。  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. ビルドおよび実行することによって、アプリケーションが正常に更新されたことを確認します。  
  
 ウィンドウのサイズを変更する作業の描画が最終的なウィンドウ サイズに対してのみ実行されます。 アクティブな描画タスクは、ウィンドウが破棄されるときにも取り消されます。  
  
 [[トップ](#top)]  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)   
 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)   
 [PPL における取り消し処理](cancellation-in-the-ppl.md)   
 [MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)
