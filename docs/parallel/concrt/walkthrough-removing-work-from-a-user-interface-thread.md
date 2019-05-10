---
title: 'チュートリアル: ユーザー インターフェイス スレッドからの処理の除去'
ms.date: 04/25/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 3bd41b1815737730067929c4728b32181cb2fc03
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856997"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>チュートリアル: ユーザー インターフェイス スレッドからの処理の除去

このドキュメントでは、同時実行ランタイムを使用して、ワーカー スレッドに Microsoft Foundation Classes (MFC) アプリケーションでユーザー インターフェイス (UI) スレッドによって実行される作業を移動する方法を示します。 このドキュメントでは、時間のかかる描画操作のパフォーマンスを向上させる方法も示します。

UI スレッドから作業を削除するには、ブロック操作をオフロード、たとえば、ワーカー スレッドの描画を向上できます、アプリケーションの応答性。 このチュートリアルでは、ブロック時間のかかる操作を示すために、マンデルブロ フラクタルを生成する描画ルーチンを使用します。 マンデルブロ フラクタルの生成は、各ピクセルの計算は、その他のすべての計算に依存しないために、並列化の有力候補もします。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを開始する前に、次のトピックを参照してください。

- [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)

- [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)

- [PPL における取り消し処理](cancellation-in-the-ppl.md)

また、このチュートリアルを開始する前に、MFC アプリケーションの開発と GDI + の基本を理解することをお勧めします。 MFC の詳細については、次を参照してください。 [MFC Desktop Applications](../../mfc/mfc-desktop-applications.md)します。 GDI + の詳細については、次を参照してください。 [GDI +](https://msdn.microsoft.com/library/windows/desktop/ms533798)します。

##  <a name="top"></a> セクション

このチュートリアルは、次のセクションで構成されています。

- [MFC アプリケーションの作成](#application)

- [マンデルブロ アプリケーションの逐次バージョンを実装します。](#serial)

- [ユーザー インターフェイス スレッドからの処理の除去](#removing-work)

- [描画パフォーマンスの向上](#performance)

- [キャンセルのサポートを追加します。](#cancellation)

##  <a name="application"></a> MFC アプリケーションの作成

このセクションでは、基本的な MFC アプリケーションを作成する方法について説明します。

### <a name="to-create-a-visual-c-mfc-application"></a>Visual C MFC アプリケーションを作成するには

1. 使用して、 **MFC アプリケーション ウィザード**すべての既定の設定で、MFC アプリケーションを作成します。 「[チュートリアル:新しい MFC シェル コントロールを使用して](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md)Visual Studio のバージョンのウィザードを開く方法の詳細について。

1. たとえば、プロジェクトの名前を入力`Mandelbrot`、順にクリックします**OK**を表示する、 **MFC アプリケーション ウィザード**。

1. **アプリケーションの種類**ペインで、 **1 つのドキュメント**します。 いることを確認、**ドキュメント/ビュー アーキテクチャ サポート** チェック ボックスがオフになっています。

1. クリックして**完了**、プロジェクトを作成し、閉じます、 **MFC アプリケーション ウィザード**します。

   アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションを構築する、**ビルド** メニューのをクリックして**ソリューションのビルド**します。 アプリケーションが正常にビルドする場合をクリックしてアプリケーションを実行**デバッグの開始**上、**デバッグ**メニュー。

##  <a name="serial"></a> マンデルブロ アプリケーションの逐次バージョンを実装します。

このセクションでは、マンデルブロ フラクタルを描画する方法について説明します。 このバージョンでは、マンデルブロ フラクタルを描画する GDI +[ビットマップ](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap)オブジェクトし、クライアント ウィンドウにそのビットマップの内容をコピーします。

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>マンデルブロ アプリケーションの逐次バージョンを実装するには

1. Stdafx.h に、次のコードを追加`#include`ディレクティブ。

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. ChildView.h の後、`pragma`ディレクティブ、定義、`BitmapPtr`型。 `BitmapPtr`型へのポインターを使用する、`Bitmap`オブジェクトを複数のコンポーネントで共有できます。 `Bitmap`不要になったすべてのコンポーネントによって参照されている場合、オブジェクトを削除します。

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. ChildView.h で次のコードを追加、`protected`のセクション、`CChildView`クラス。

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. ChildView.cpp、コメント アウトするか、次の行を削除します。

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   デバッグ ビルドでこの手順により、アプリケーションを使用して、`DEBUG_NEW`アロケーターで、GDI + と互換性がありません。

1. ChildView.cpp で追加、`using`ディレクティブを`Gdiplus`名前空間。

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. コンス トラクターとデストラクターの次のコードを追加、`CChildView`クラスを初期化し、GDI + をシャット ダウンします。

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. `CChildView::DrawMandelbrot` メソッドを実装します。 このメソッドを指定した、マンデルブロ フラクタルの描画`Bitmap`オブジェクト。

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. `CChildView::OnPaint` メソッドを実装します。 このメソッドを呼び出す`CChildView::DrawMandelbrot`の内容をコピーし、`Bitmap`ウィンドウへのオブジェクト。

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. 構築し実行すると、アプリケーションが正常に更新されたことを確認します。

次の図は、マンデルブロ アプリケーションの結果を示します。

![マンデルブロ アプリケーション](../../parallel/concrt/media/mandelbrot.png "マンデルブロ アプリケーション")

各ピクセルの計算は計算コストが高いため、UI スレッドは、計算全体が完了するまで追加のメッセージを処理できません。 これにより、アプリケーションの応答性が低下する可能性があります。 ただし、UI スレッドから作業を削除することで、この問題を軽減することができます。

[[トップ](#top)]

##  <a name="removing-work"></a> UI スレッドからの処理の除去

このセクションでは、マンデルブロ アプリケーションで UI スレッドから描画の処理を削除する方法を示します。 UI スレッドから描画の作業をワーカー スレッドに移動して、UI スレッドは、ワーカー スレッドがバック グラウンドで、イメージを生成するようにメッセージを処理できます。

同時実行ランタイムには、タスクを実行する 3 つの方法が用意されています:[タスク グループ](../../parallel/concrt/task-parallelism-concurrency-runtime.md)、[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)、および[軽量タスク](../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。 この例では UI スレッドから作業を削除するのには、これらのメカニズムのいずれかを使用できますが、 [concurrency::task_group](reference/task-group-class.md)タスク グループは、キャンセルをサポートするためのオブジェクトします。 このチュートリアルでは、クライアント ウィンドウがサイズ変更時に実行される作業の量を削減して、ウィンドウが破棄されるときに、クリーンアップを実行するキャンセル後で使用します。

またこの例では、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) UI スレッドとワーカー スレッドが互いに通信するを有効にするオブジェクト。 ポインターを送信するワーカー スレッドが、イメージを生成した後、`Bitmap`オブジェクトを`unbounded_buffer`オブジェクトし、UI スレッドに描画メッセージを投稿します。 UI スレッドを受信し、`unbounded_buffer`オブジェクト、`Bitmap`オブジェクトし、クライアント ウィンドウに描画します。

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>UI スレッドから描画の処理を削除するには

1. Stdafx.h に、次のコードを追加`#include`ディレクティブ。

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. ChildView.h で追加`task_group`と`unbounded_buffer`メンバー変数を`protected`のセクション、`CChildView`クラス。 `task_group` ; の描画を実行するタスクを保持するオブジェクト、`unbounded_buffer`オブジェクトが完了したマンデルブロ イメージを保持します。

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. ChildView.cpp で追加、`using`ディレクティブを`concurrency`名前空間。

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. `CChildView::DrawMandelbrot`メソッドの呼び出しの後、 `Bitmap::UnlockBits`、呼び出し、 [concurrency::send](reference/concurrency-namespace-functions.md#send)関数に渡す、 `Bitmap` UI スレッドへのオブジェクト。 UI スレッドに描画メッセージを投稿し、クライアント領域を無効にします。

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. 更新プログラム、`CChildView::OnPaint`メソッドは、更新を受信する`Bitmap`オブジェクトし、クライアント ウィンドウにイメージを描画します。

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   `CChildView::OnPaint`メソッドは、メッセージ バッファーのいずれかが存在しない場合は、マンデルブロ イメージを生成するタスクを作成します。 メッセージ バッファーにが含まれていない、`Bitmap`初期のペイント メッセージなど、クライアント ウィンドウの前面に別のウィンドウに移動する場合のオブジェクト。

1. 構築し実行すると、アプリケーションが正常に更新されたことを確認します。

描画の処理はバック グラウンドで実行されるため、UI は応答性を高めるようになりました。

[[トップ](#top)]

##  <a name="performance"></a> 描画パフォーマンスの向上

マンデルブロ フラクタルの生成は、各ピクセルの計算は、その他のすべての計算に依存しないため、並列処理の適切な候補です。 描画のプロシージャを並列化する変換、外側`for`ループ、`CChildView::DrawMandelbrot`メソッドへの呼び出しを[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムは、次のようにします。

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

ビットマップの各要素の計算は、独立系であるために、ビットマップ メモリにアクセスする描画操作を同期する必要はありません。 これにより、パフォーマンスを利用可能なプロセッサの数に応じてスケールできます。

[[トップ](#top)]

##  <a name="cancellation"></a> キャンセルのサポートを追加します。

このセクションでは、ウィンドウのサイズ変更を処理する方法と、ウィンドウが破棄されるときに、アクティブな描画タスクを取り消す方法について説明します。

ドキュメント[PPL における取り消し処理](cancellation-in-the-ppl.md)ランタイムでのキャンセルのしくみについて説明します。 キャンセルが協調;そのため、それは直ちに行われません。 取り消されたタスクを停止するには、ランタイムは、ランタイムにタスクからの後続の呼び出し中に内部例外をスローします。 前のセクションを使用する方法を示しています、`parallel_for`描画タスクのパフォーマンスを向上させるアルゴリズム。 呼び出し`parallel_for`と、ランタイム、タスクを停止でき、したがって取り消し機能を有効にします。

### <a name="cancelling-active-tasks"></a>アクティブなタスクのキャンセル

マンデルブロ アプリケーション作成`Bitmap`次元には、クライアント ウィンドウのサイズが一致するオブジェクト。 クライアント ウィンドウのサイズを変更するたびに、アプリケーションは、新しいウィンドウ サイズのイメージを生成する、追加のバック グラウンド タスクを作成します。 アプリケーションにこれらの中間イメージが必要としません。最終的なウィンドウ サイズのイメージのみが必要です。 この追加作業を実行してから、アプリケーションを防ぐためには、メッセージ ハンドラーの場合は、アクティブな描画タスクを取り消すことができます、`WM_SIZE`と`WM_SIZING`ウィンドウのサイズが変更された後でメッセージと、再スケジュール図面動作します。

アクティブな描画タスクを取り消す場合に、ウィンドウのサイズが変更されたときに、アプリケーションが呼び出す、 [concurrency::task_group::cancel](reference/task-group-class.md#cancel)ハンドラーのメソッド、`WM_SIZING`と`WM_SIZE`メッセージ。 ハンドラーは、`WM_SIZE`呼び出しでメッセージも、 [::task_group::wait](reference/task-group-class.md#wait)メソッドすべてのアクティブなタスクを完了して、更新されたウィンドウのサイズに描画タスクを再スケジュールするを待つことです。

クライアント ウィンドウが破棄されるときに、アクティブな描画タスクをキャンセルすることをお勧めします。 アクティブな描画タスクのキャンセルは、エントリのクライアント ウィンドウが破棄された後、ワーカー スレッドは UI スレッドにメッセージが post しないことを確認します。 アプリケーション用のハンドラーで、アクティブな描画タスクのキャンセル、`WM_DESTROY`メッセージ。

### <a name="responding-to-cancellation"></a>キャンセルに応答

`CChildView::DrawMandelbrot`描画タスクを実行するメソッドには、キャンセルに応答する必要があります。 ランタイムは、タスクをキャンセルする例外処理を使用するため、`CChildView::DrawMandelbrot`メソッドは、すべてのリソースが正しくクリーンアップを保証するために、例外セーフ メカニズムを使用する必要があります。 この例では、 *Resource Acquisition Is Initialization* (RAII) パターンをタスクが取り消された場合、ビットマップのビットはロックしないことを保証します。

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>マンデルブロ アプリケーションでキャンセルのサポートを追加するには

1. ChildView.h での`protected`のセクション、`CChildView`クラスでの宣言を追加、 `OnSize`、 `OnSizing`、および`OnDestroy`メッセージ マップ関数です。

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. ChildView.cpp でのハンドラーを含むメッセージ マップの変更、 `WM_SIZE`、 `WM_SIZING`、および`WM_DESTROY`メッセージ。

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. `CChildView::OnSizing` メソッドを実装します。 このメソッドは、既存の描画タスクをキャンセルします。

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. `CChildView::OnSize` メソッドを実装します。 このメソッドは、既存の描画タスクをキャンセルし、更新されたクライアント ウィンドウ サイズの新しい描画タスクを作成します。

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. `CChildView::OnDestroy` メソッドを実装します。 このメソッドは、既存の描画タスクをキャンセルします。

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. ChildView.cpp で定義、`scope_guard`クラスは、RAII パターンを実装します。

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. 次のコードを追加、`CChildView::DrawMandelbrot`メソッドを呼び出した後`Bitmap::LockBits`:

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   このコードでは、キャンセルを処理を作成して、`scope_guard`オブジェクト。 オブジェクトがスコープを離れたときに、ビットマップのビットがロック解除します。

1. 最後の変更、`CChildView::DrawMandelbrot`メソッドを`scope_guard`がビットマップのビットがロックされた後は、すべてのメッセージが UI スレッドに送信される前にオブジェクトします。 これにより、UI スレッドは、ビットマップのビットがロックされていない前に更新されません。

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

9. 構築し実行すると、アプリケーションが正常に更新されたことを確認します。

ウィンドウのサイズを変更するときに、作業を描画は最終的なウィンドウ サイズに対してのみ実行されます。 アクティブな描画タスクは、ウィンドウが破棄されるときにも取り消されます。

[[トップ](#top)]

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)
