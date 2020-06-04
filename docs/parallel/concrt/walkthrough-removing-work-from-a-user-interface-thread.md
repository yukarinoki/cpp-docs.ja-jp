---
title: 'チュートリアル: ユーザー インターフェイス スレッドからの処理の除去'
ms.date: 08/19/2019
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
ms.openlocfilehash: 52bc98ef339a19c6ec2a53697f532a9a94b6c9a6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377441"
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>チュートリアル: ユーザー インターフェイス スレッドからの処理の除去

このドキュメントでは、同時実行ランタイムを使用して、Microsoft Foundation クラス (MFC) アプリケーションのユーザー インターフェイス (UI) スレッドによって実行される作業をワーカー スレッドに移動する方法を示します。 このドキュメントでは、長い描画操作のパフォーマンスを向上させる方法も示します。

描画などのブロック操作をワーカー スレッドにオフロードすることによって UI スレッドから作業を削除すると、アプリケーションの応答性が向上します。 このチュートリアルでは、長いブロッキング操作を示すために Mandelbrot フラクタルを生成する描画ルーチンを使用します。 マンデルブロフラクタルの生成は、各ピクセルの計算が他のすべての計算とは独立しているため、並列化の有力な候補でもあります。

## <a name="prerequisites"></a>前提条件

このチュートリアルを開始する前に、次のトピックを参照してください。

- [タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)

- [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)

- [PPL における取り消し処理](cancellation-in-the-ppl.md)

また、このチュートリアルを開始する前に、MFC アプリケーション開発と GDI+ の基本について理解しておくことをお勧めします。 MFC の詳細については、「 [MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)」を参照してください。 GDI+ の詳細については[、GDI+](/windows/win32/gdiplus/-gdiplus-gdi-start)を参照してください。

## <a name="sections"></a><a name="top"></a>セクション

このチュートリアルは、次のセクションで構成されています。

- [MFC アプリケーションの作成](#application)

- [マンデルブロ アプリケーションのシリアル バージョンの実装](#serial)

- [ユーザー インターフェイス スレッドからの作業の削除](#removing-work)

- [図面のパフォーマンスの向上](#performance)

- [キャンセルのサポートの追加](#cancellation)

## <a name="creating-the-mfc-application"></a><a name="application"></a>MFC アプリケーションの作成

ここでは、基本的な MFC アプリケーションの作成方法について説明します。

### <a name="to-create-a-visual-c-mfc-application"></a>Visual C++ MFC アプリケーションを作成するには

1. MFC**アプリケーション ウィザード**を使用して、すべての既定の設定を使用して MFC アプリケーションを作成します。 使用しているバージョンの Visual Studio のウィザードを開く方法については、「[チュートリアル: 新しい MFC シェル コントロールの使用](../../mfc/walkthrough-using-the-new-mfc-shell-controls.md)」を参照してください。

1. プロジェクトの名前を入力し、`Mandelbrot`次に **[OK] を**クリックして**MFC アプリケーション ウィザード**を表示します。

1. [**アプリケーションの種類]** ペインで、[**単一ドキュメント**] を選択します。 **[ドキュメント/ビュー アーキテクチャ のサポート**] チェック ボックスがオフになっていることを確認します。

1. [**完了] を**クリックしてプロジェクトを作成し **、MFC アプリケーション ウィザード**を閉じます。

   アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。 アプリケーションをビルドするには、[**ビルド**] メニューの [**ソリューションのビルド**] をクリックします。 アプリケーションが正常にビルドされた場合は、[**デバッグ**] メニューの [**デバッグの開始**] をクリックしてアプリケーションを実行します。

## <a name="implementing-the-serial-version-of-the-mandelbrot-application"></a><a name="serial"></a>マンデルブロ アプリケーションのシリアル バージョンの実装

このセクションでは、マンデルブロフラクタルを描く方法について説明します。 このバージョンでは、マンデルブロフラクタルを GDI+[ビットマップ](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap)オブジェクトに描画し、そのビットマップの内容をクライアント ウィンドウにコピーします。

#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>マンデルブロ アプリケーションのシリアル バージョンを実装するには

1. *pch.h* (2017 年以前のバージョンでは*stdafx.h)* `#include`に次のディレクティブを追加します。

   [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]

1. ChildView.h では、ディレクティブ`pragma`の後に型`BitmapPtr`を定義します。 この`BitmapPtr`型を使用すると、オブジェクト`Bitmap`へのポインターを複数のコンポーネントで共有できます。 `Bitmap`オブジェクトがどのコンポーネントからも参照されなくなると、オブジェクトは削除されます。

   [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]

1. ChildView.h で、クラスのセクションに次`protected`のコードを`CChildView`追加します。

   [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]

1. ChildView.cpp で、コメント アウトするか、次の行を削除します。

   [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]

   デバッグ ビルドでは、この手順では、アプリケーションが GDI+ と互換性のない`DEBUG_NEW`アロケーターを使用できないようにします。

1. ChildView.cpp で、名前空間`using`にディレクティブを`Gdiplus`追加します。

   [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]

1. クラスのコンストラクターとデストラクターに次のコードを`CChildView`追加して、GDI+ を初期化してシャットダウンします。

   [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]

1. `CChildView::DrawMandelbrot` メソッドを実装します。 このメソッドは、指定した`Bitmap`オブジェクトにマンデルブロ フラクタルを描画します。

   [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]

1. `CChildView::OnPaint` メソッドを実装します。 このメソッドは`CChildView::DrawMandelbrot`、オブジェクトの内容を呼び`Bitmap`出し、ウィンドウにコピーします。

   [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]

1. アプリケーションをビルドして実行して、アプリケーションが正常に更新されたことを確認します。

次の図は、マンデルブロ アプリケーションの結果を示しています。

![マンデルブロ アプリケーション](../../parallel/concrt/media/mandelbrot.png "マンデルブロ アプリケーション")

各ピクセルの計算は計算負荷が高いため、全体的な計算が完了するまで UI スレッドは追加のメッセージを処理できません。 これにより、アプリケーションの応答性が低下する可能性があります。 ただし、UI スレッドから作業を削除することで、この問題を解決できます。

[[トップ](#top)]

## <a name="removing-work-from-the-ui-thread"></a><a name="removing-work"></a>UI スレッドからの作業の削除

このセクションでは、Mandelbrot アプリケーションの UI スレッドから描画作業を削除する方法を示します。 UI スレッドからワーカー スレッドに描画作業を移動することで、ワーカー スレッドがバックグラウンドでイメージを生成する場合に、UI スレッドでメッセージを処理できます。

同時実行ランタイムには、タスクを実行する 3 つの方法が用意されています:[タスク グループ](../../parallel/concrt/task-parallelism-concurrency-runtime.md)、[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)、[および軽量タスク](../../parallel/concrt/task-scheduler-concurrency-runtime.md)。 これらのいずれかのメカニズムを使用して UI スレッドから作業を削除できますが、この例では、タスク グループがキャンセルをサポートするため[、同時実行::task_group](reference/task-group-class.md)オブジェクトを使用します。 このチュートリアルでは、後でキャンセルを使用して、クライアント ウィンドウのサイズを変更するときに実行される作業の量を減らし、ウィンドウが破棄されたときにクリーンアップを実行します。

この例では、[同時実行::unbounded_buffer](reference/unbounded-buffer-class.md)オブジェクトを使用して、UI スレッドとワーカー スレッドが相互に通信できるようにします。 ワーカー スレッドは、イメージを生成した後、`Bitmap``unbounded_buffer`オブジェクトへのポインターをオブジェクトに送信し、UI スレッドに描画メッセージをポストします。 UI スレッドは、オブジェクトからオブジェクト`unbounded_buffer`を`Bitmap`受け取り、クライアント ウィンドウに描画します。

#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>UI スレッドから描画作業を削除するには

1. *pch.h* (2017 年以前のバージョンでは*stdafx.h)* `#include`で、次のディレクティブを追加します。

   [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]

1. ChildView.h で、`task_group`クラス`unbounded_buffer`の`protected`セクションにメンバー変数を追加`CChildView`し、メンバー変数を追加します。 オブジェクト`task_group`には、描画を実行するタスクが保持されます。オブジェクト`unbounded_buffer`は、完成したマンデルブロのイメージを保持します。

   [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]

1. ChildView.cpp で、名前空間`using`にディレクティブを`concurrency`追加します。

   [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]

1. メソッドで`CChildView::DrawMandelbrot`の呼び出しの`Bitmap::UnlockBits`後、[同時実行::send](reference/concurrency-namespace-functions.md#send)関数を呼び`Bitmap`出して、オブジェクトを UI スレッドに渡します。 次に、UI スレッドに描画メッセージをポストし、クライアント領域を無効にします。

   [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]

1. 更新された`CChildView::OnPaint``Bitmap`オブジェクトを受け取り、クライアント ウィンドウにイメージを描画するメソッドを更新します。

   [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]

   メッセージ`CChildView::OnPaint`バッファにマンデルブロ イメージが存在しない場合、このメソッドは、Mandelbrot イメージを生成するタスクを作成します。 初期描画メッセージや、クライアント`Bitmap`ウィンドウの前に別のウィンドウが移動した場合など、メッセージ バッファーにはオブジェクトが含まれません。

1. アプリケーションをビルドして実行して、アプリケーションが正常に更新されたことを確認します。

描画作業がバックグラウンドで実行されるため、UI の応答性が向上しました。

[[トップ](#top)]

## <a name="improving-drawing-performance"></a><a name="performance"></a>図面のパフォーマンスの向上

各ピクセルの計算は他のすべての計算とは独立しているため、マンデルブロフラクタルの生成は並列化の候補として適しています。 描画プロシージャを並列化するには、`for``CChildView::DrawMandelbrot`メソッドの外側のループを[、次のように、同時実行::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムの呼び出しに変換します。

[!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]

各ビットマップ要素の計算は独立しているため、ビットマップ メモリにアクセスする描画操作を同期する必要はありません。 これにより、使用可能なプロセッサの数が増えるに応じてパフォーマンスを拡張できます。

[[トップ](#top)]

## <a name="adding-support-for-cancellation"></a><a name="cancellation"></a>キャンセルのサポートの追加

ここでは、ウィンドウのサイズ変更を処理する方法と、ウィンドウが破棄されたときにアクティブな描画タスクをキャンセルする方法について説明します。

PPL[のドキュメントの取り消しでは、](cancellation-in-the-ppl.md)ランタイムでの取り消しのしくみについて説明します。 キャンセルは協力的です。そのため、すぐには発生しません。 取り消されたタスクを停止するには、ランタイムは、後続のタスクからランタイムへの呼び出し中に内部例外をスローします。 前のセクションでは、`parallel_for`このアルゴリズムを使用して描画タスクのパフォーマンスを向上させる方法を示します。 呼び出`parallel_for`しを使用すると、ランタイムはタスクを停止できるため、取り消しが機能します。

### <a name="cancelling-active-tasks"></a>アクティブなタスクのキャンセル

Mandelbrot アプリケーションは`Bitmap`、サイズがクライアント ウィンドウのサイズと一致するオブジェクトを作成します。 クライアント ウィンドウのサイズを変更するたびに、アプリケーションは新しいウィンドウ サイズのイメージを生成する追加のバックグラウンド タスクを作成します。 アプリケーションでは、これらの中間イメージは必要ありません。最終的なウィンドウ サイズのイメージのみが必要です。 アプリケーションでこの追加作業を実行しないようにするには、 および`WM_SIZE``WM_SIZING`メッセージのメッセージ ハンドラでアクティブな描画タスクをキャンセルし、ウィンドウのサイズを変更した後に図面の作業を再スケジュールします。

ウィンドウのサイズが変更されたときにアクティブな描画タスクをキャンセルするには、アプリケーションは`WM_SIZING`、 および`WM_SIZE`メッセージのハンドラーで同時実行を呼び出します[。::task_group:cancel](reference/task-group-class.md#cancel)メソッド。 メッセージの`WM_SIZE`ハンドラーも、同時実行を呼び出します[::task_group:wait](reference/task-group-class.md#wait)メソッドは、すべてのアクティブなタスクが完了するのを待ってから、更新されたウィンドウ サイズの描画タスクをスケジュールし直します。

クライアント ウィンドウが破棄された場合は、アクティブな描画タスクをキャンセルすることをお勧めします。 アクティブな描画タスクをキャンセルすると、クライアント ウィンドウが破棄された後、ワーカー スレッドが UI スレッドにメッセージをポストしないようにします。 アプリケーションは、メッセージのハンドラー内のアクティブな描画タスクを`WM_DESTROY`取り消します。

### <a name="responding-to-cancellation"></a>キャンセルへの対応

描画`CChildView::DrawMandelbrot`タスクを実行するメソッドは、取り消しに応答する必要があります。 ランタイムは例外処理を使用してタスクを取り消`CChildView::DrawMandelbrot`すため、メソッドは例外セーフなメカニズムを使用して、すべてのリソースが正しくクリーンアップされるようにする必要があります。 この例では、*リソース取得の初期化*(RAII) パターンを使用して、タスクが取り消されたときにビットマップ ビットのロックが解除されることを保証します。

##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>マンデルブロ アプリケーションでキャンセルのサポートを追加するには

1. ChildView.h`protected`の`CChildView`クラスのセクションで、 、および`OnSize``OnSizing``OnDestroy`メッセージ マップ関数の宣言を追加します。

   [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]

1. ChildView.cpp で、メッセージ マップを変更して、 `WM_SIZE`、`WM_SIZING`および`WM_DESTROY`メッセージのハンドラーを含めます。

   [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]

1. `CChildView::OnSizing` メソッドを実装します。 このメソッドは、既存の描画タスクを取り消します。

   [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]

1. `CChildView::OnSize` メソッドを実装します。 このメソッドは、既存の描画タスクをキャンセルし、更新されたクライアント ウィンドウ サイズに対して新しい描画タスクを作成します。

   [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]

1. `CChildView::OnDestroy` メソッドを実装します。 このメソッドは、既存の描画タスクを取り消します。

   [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]

1. ChildView.cpp で、RAII パターンを`scope_guard`実装するクラスを定義します。

   [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]

1. の呼び出しの`CChildView::DrawMandelbrot`後、次のコード`Bitmap::LockBits`をメソッドに追加します。

   [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]

   このコードは、オブジェクトを作成`scope_guard`することによって取り消しを処理します。 オブジェクトがスコープを離れると、ビットマップ ビットのロックが解除されます。

1. ビットマップ ビットのロック`CChildView::DrawMandelbrot`が解除された後`scope_guard`、メッセージが UI スレッドに送信される前に、オブジェクトを閉じるには、メソッドの末尾を変更します。 これにより、ビットマップ ビットのロックが解除される前に UI スレッドが更新されないことが保証されます。

   [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]

1. アプリケーションをビルドして実行して、アプリケーションが正常に更新されたことを確認します。

ウィンドウのサイズを変更すると、描画作業は最終的なウィンドウ サイズに対してのみ実行されます。 ウィンドウが破棄されると、アクティブな描画タスクも取り消されます。

[[トップ](#top)]

## <a name="see-also"></a>関連項目

[同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)
