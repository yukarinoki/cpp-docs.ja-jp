---
title: Visual C++ でのクラウドおよび Web プログラミング
ms.date: 11/04/2016
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
ms.openlocfilehash: 3d71e36b6209c693940f2ebe6b5e9c73bc0c9d9d
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708038"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++ でのクラウドおよび Web プログラミング

C++ では、Web とクラウドに接続するためのいくつかの方法があります。

## <a name="cloud-programming-options"></a>クラウドのプログラミング オプション

- [Microsoft Azure Mobile Services](http://www.windowsazure.com/develop/mobile/)

  ユニバーサル Windows プラットフォーム (UWP) アプリまたは Windows デスクトップ アプリで、Microsoft Azure Mobile Services に接続するために使用できる、ネイティブな API を提供します。 Web サイトの例のほとんどは C# を使用していますが、C++ も使用できます。 詳細については、「[クイック スタート:CC++ を使ったモバイル サービスの追加](https://msdn.microsoft.com/library/windows/apps/dn263181.aspx)」を参照してください。

- [C++ 用 Microsoft Azure Storage クライアント ライブラリ](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

  C++ 用 Microsoft Azure Storage クライアント ライブラリでは、Azure Storage を操作するための包括的な API が提供されています。これには次の機能が含まれますが、これに限定されるわけではありません。

  - BLOB コンテナー、テーブル、キューの作成、読み取り、削除、一覧表示。
  - BLOB の作成、読み取り、削除、一覧表示と、BLOB 範囲の読み取りと書き込み。
  - Azure テーブル内のエンティティの挿入、削除、置換、結合、クエリ。
  - Azure キューでのメッセージのエンキューとデキュー。
  - コンテナー、BLOB、テーブル、キューの遅延リスト、およびエンティティの遅延クエリ

- [OneDrive API](https://dev.onedrive.com/README.htm)

  OneDrive API では、アプリケーションを Office 365 と SharePoint Server 2016 のファイルとフォルダーに接続する一連の HTTP サービスが提供されます。

- [C++ REST SDK (Codename "Casablanca")](https://github.com/Microsoft/cpprestsdk)

  REST サービスと対話するための最新のクロスプラットフォームの非同期 API を提供します。

  - JSON ドキュメントの解析とシリアル化の組み込みサポートにより、任意の HTTP サーバーに対して REST 呼び出しを実行する
  - OAuth 1 と 2 (ローカル リダイレクト リスナーを含む) をサポート
  - リモート サービスに対する Websocket 接続
  - PPL に基づく完全な非同期タスク API (組み込みの Threadpool を含む)

  Windows デスクトップ (7 以降)、Windows Server (2012 以降)、ユニバーサル Windows プラットフォーム、Linux、OSX、Android、および iOS をサポートしています。

- [Windows::Web::Http::HttpClient](/uwp/api/windows.web.http.httpclient)

  System.Web 名前空間にある同じ名前の .NET Framework クラスでモデル化された Windows ランタイムの HTTP クライアント クラスです。 `HttpClient` は、HTTP 経由の非同期アップロードとダウンロード、およびパイプラインにカスタム HTTP ハンドラーを挿入するためのパイプライン フィルターを完全にサポートします。 Windows SDK には、メーター付きネットワークや OAuth 認証用のサンプル フィルターが含まれています。 ユニバーサル Windows プラットフォームのみを対象とするアプリには、`Windows::Web:HttpClient` クラスを使用することをお勧めします。

- [IXMLHTTPRequest2 インターフェイス](/windows/desktop/api/msxml6/nn-msxml6-ixmlhttprequest2)

  Windows ランタイム アプリまたは Windows デスクトップ アプリで、HTTP 経由でインターネットに接続し、GET、PUT などの HTTP コマンドを発行するために使用できる、ネイティブな COM インターフェイスを提供します。 詳細については、「[チュートリアル:タスクおよび XML HTTP 要求を使用した接続](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)」を参照してください。

- [Windows インターネット (WinInet)](/windows/desktop/WinInet/portal)

  Windows デスクトップ アプリでインターネットに接続するために使用できる Windows API。

## <a name="see-also"></a>関連項目

[Visual Studio での C++](../overview/visual-cpp-in-visual-studio.md) <br/>
[ネットワークと Web サービス](/windows/uwp/networking/)
