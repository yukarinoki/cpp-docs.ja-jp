---
title: 'チュートリアル: タスクおよび XML HTTP 要求を使用した接続'
ms.date: 04/25/2019
helpviewer_keywords:
- connecting to web services, UWP apps [C++]
- IXMLHTTPRequest2 and tasks, example
- IXHR2 and tasks, example
ms.assetid: e8e12d46-604c-42a7-abfd-b1d1bb2ed6b3
ms.openlocfilehash: 2c627a543ec18702bf5358ff0170bec177fd7497
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032266"
---
# <a name="walkthrough-connecting-using-tasks-and-xml-http-requests"></a>チュートリアル: タスクおよび XML HTTP 要求を使用した接続

この例では[、IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2)および[IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback)インターフェイスを使用して、HTTP GET 要求と POST 要求をユニバーサル Windows プラットフォーム (UWP) アプリの Web サービスに送信するタスクと共に使用する方法を示します。 タスクと `IXMLHTTPRequest2` を組み合わせることによって、他のタスクと共に構成するコードを記述できます。 たとえば、タスクのチェーンの一部としてダウンロード タスクを使用できます。 ダウンロード タスクは、処理が取り消された場合にも応答できます。

> [!TIP]
> C++ REST SDK を使用して、C++ アプリを使用する UWP アプリまたはデスクトップ C++ アプリから HTTP 要求を実行することもできます。 詳しくは[、C++ REST SDK (コードネーム 「カサブランカ」) を](https://github.com/Microsoft/cpprestsdk)参照してください。

タスクの詳細については、「[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。 UWP アプリでタスクを使用する方法の詳細については[、「C++ での非同期プログラミング](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)」および[「C++ での非同期操作の作成」を参照](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)してください。

このドキュメントでは、最初に `HttpRequest` およびそのサポート クラスを作成する方法を示します。 次に、C++ と XAML を使用する UWP アプリからこのクラスを使用する方法を示します。

タスクを使用するが`IXMLHTTPRequest2`、タスクを使用しない例については、「[クイック スタート: XML HTTP 要求を使用した接続 (IXMLHTTPRequest2)」](/previous-versions/windows/apps/hh770550\(v=win.10\))を参照してください。

> [!TIP]
> `IXMLHTTPRequest2`UWP`IXMLHTTPRequest2Callback`アプリで使用することをお勧めするインターフェイスです。 また、この例をデスクトップ アプリケーションでの使用に適用することもできます。

## <a name="prerequisites"></a>前提条件

UWP サポートは、Visual Studio 2017 以降では省略可能です。 インストールするには、Windows の [スタート] メニューから Visual Studio インストーラーを開き、使用している Visual Studio のバージョンを選択します。 [**変更**] ボタンをクリックし **、[UWP 開発**] タイルがオンになっていることを確認します。 [**オプション コンポーネント]** で **、[C++ UWP ツール**] がオンになっていることを確認します。 Visual Studio 2017 の場合は v141 を使用し、Visual Studio 2019 の場合は v142 を使用します。

## <a name="defining-the-httprequest-httprequestbufferscallback-and-httprequeststringcallback-classes"></a>HttpRequest、HttpRequestBuffersCallback、および HttpRequestStringCallback クラスを定義する

`IXMLHTTPRequest2` インターフェイスを使用して HTTP を通じた Web 要求を作成する場合、`IXMLHTTPRequest2Callback` インターフェイスを実装して、サーバーの応答を受け取り、他のイベントに対応します。 この例では `HttpRequest` クラスを定義して Web 要求を作成し、`HttpRequestBuffersCallback` と `HttpRequestStringCallback` クラスを定義して応答を処理しています。 `HttpRequestBuffersCallback` および `HttpRequestStringCallback` クラスは `HttpRequest` クラスをサポートします。`HttpRequest` クラスはアプリケーション コードからのみ使用できます。

`GetAsync` クラスの `PostAsync` および `HttpRequest` メソッドを使うと、HTTP GET および POST のそれぞれの操作を開始することができます。 これらのメソッドは、`HttpRequestStringCallback` クラスを使用して、サーバー応答を文字列として読み取ります。 `SendAsync` と `ReadAsync` のメソッドは、大きなコンテンツをストリーム転送することができます。 これらのメソッドは、操作を表す[同時実行性::task](../../parallel/concrt/reference/task-class.md)をそれぞれ返します。 The `GetAsync` および `PostAsync` のメソッドは `task<std::wstring>` の値を生成し、`wstring` の部分がサーバーの応答を表します。 `SendAsync` および `ReadAsync` のメソッドは `task<void>` の値を生成します。これらのタスクは、送信と読み取り操作が完了すると、完了します。

インターフェイスは`IXMLHTTPRequest2`非同期的に動作するため、この例では[、同時実行を使用します::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)コールバック オブジェクトが完了するか、ダウンロード操作をキャンセルした後に完了するタスクを作成します。 `HttpRequest` クラスは、このタスクからタスク ベースの継続を作成し、最終結果を設定します。 `HttpRequest` クラスは、タスク ベースの継続を使って、前のタスクがエラーを生成したり取り消された場合でも、継続タスクが実行されるようにします。 タスクベースの継続の詳細については、「[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。

取り消し操作をサポートするため、`HttpRequest`、`HttpRequestBuffersCallback`、および `HttpRequestStringCallback` のクラスは、キャンセル トークンを使用します。 と`HttpRequestBuffersCallback``HttpRequestStringCallback`クラスは[、同時実行::cancellation_token::register_callback](reference/cancellation-token-class.md#register_callback)メソッドを使用して、タスク完了イベントが取り消しに応答できるようにします。 この取り消しのコールバックは、ダウンロードを中止します。 キャンセルの詳細については、「[キャンセル](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)」を参照してください。

### <a name="to-define-the-httprequest-class"></a>HttpRequest クラスを定義するには

1. メイン メニューの [**新** > **しい** > **プロジェクト**] をクリックします。

1. C++**の空のアプリ (ユニバーサル Windows)** テンプレートを使用して、空の XAML アプリ プロジェクトを作成します。 この例では、プロジェクトの名前を `UsingIXMLHTTPRequest2`とします。

1. プロジェクトに HttpRequest.h という名前のヘッダー ファイルと HttpRequest.cpp という名前のソース ファイルを追加します。

1. 次のコードを pch.h に追加します。

   [!code-cpp[concrt-using-ixhr2#1](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_1.h)]

1. 次のコードを HttpRequest.h に追加します。

   [!code-cpp[concrt-using-ixhr2#2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_2.h)]

1. 次のコードを HttpRequest.cpp に追加します。

   [!code-cpp[concrt-using-ixhr2#3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_3.cpp)]

## <a name="using-the-httprequest-class-in-a-uwp-app"></a>UWP アプリでの HttpRequest クラスの使用

このセクションでは、UWP アプリで`HttpRequest`クラスを使用する方法を示します。 このアプリケーションは、URL リソースを定義する入力ボックス、GET と POST の操作を実行するボタン コマンド、現在の操作を取り消すボタン コマンドを提供します。

### <a name="to-use-the-httprequest-class"></a>HttpRequest クラスを使用するには

1. MainPage.xaml で、[次のようにスタックパネル](/uwp/api/windows.ui.xaml.controls.stackpanel)要素を定義します。

   [!code-xml[concrt-using-ixhr2#A1](../../parallel/concrt/codesnippet/xaml/walkthrough-connecting-using-tasks-and-xml-http-requests_4.xaml)]

1. MainPage.xaml.h で、この `#include` ディレクティブを追加します。

   [!code-cpp[concrt-using-ixhr2#A2](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_5.h)]

1. MainPage.xaml.h で、これらの `private` メンバー変数を `MainPage` クラスに追加します。

   [!code-cpp[concrt-using-ixhr2#A3](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_6.h)]

1. MainPage.xaml.h で `private` メソッド `ProcessHttpRequest` を宣言します。

   [!code-cpp[concrt-using-ixhr2#A4](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_7.h)]

1. MainPage.xaml.cpp で、これらの `using` ステートメントを追加します。

   [!code-cpp[concrt-using-ixhr2#A5](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_8.cpp)]

1. MainPage.xaml.cpp で、`GetButton_Click` クラスの `PostButton_Click`、 `CancelButton_Click`、 `MainPage` メソッドを実装します。

   [!code-cpp[concrt-using-ixhr2#A6](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_9.cpp)]

   > [!TIP]
   > アプリでキャンセルのサポートが不要な場合は、[同時実行性::cancellation_token::none](reference/cancellation-token-class.md#none) `HttpRequest::GetAsync`を`HttpRequest::PostAsync`メソッドとメソッドに渡します。

1. MainPage.xaml.cpp で `MainPage::ProcessHttpRequest` メソッドを実装します。

   [!code-cpp[concrt-using-ixhr2#A7](../../parallel/concrt/codesnippet/cpp/walkthrough-connecting-using-tasks-and-xml-http-requests_10.cpp)]

1. プロジェクトのプロパティの [**リンカ**] の`msxml6.lib`下で、**入力**を指定し、 を指定`shcore.lib`します。

実行中のアプリケーションを次に示します。

![実行中の Windows ランタイム アプリ](../../parallel/concrt/media/concrt_usingixhr2.png "実行中の Windows ランタイム アプリ")

## <a name="next-steps"></a>次の手順

[同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

## <a name="see-also"></a>関連項目

[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[C++ での非同期プログラミング](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)<br/>
[UWP アプリ用 C++ での非同期操作の作成](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)<br/>
[クイック スタート: XML HTTP 要求 (IXMLHTTPRequest2)](/previous-versions/windows/apps/hh770550\(v=win.10\))
[タスク クラス (同時実行ランタイム) を](../../parallel/concrt/reference/task-class.md)使用した接続<br/>
[task_completion_event クラス](../../parallel/concrt/reference/task-completion-event-class.md)
