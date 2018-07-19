---
title: クラウドし、Visual C でのプログラミングを Web |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-azure
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b63611f1-9723-44d0-ba7f-c3ebef341313
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 360404530df8d07a3cd8fc35654c0c9563ae29fe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412401"
---
# <a name="cloud-and-web-programming-in-visual-c"></a>Visual C++ でのクラウドおよび Web プログラミング

C++ では、Web とクラウドに接続するためのいくつかの方法があります。

## <a name="cloud-programming-options"></a>クラウドのプログラミングのオプション

- [Microsoft Azure Mobile Services](http://www.windowsazure.com/develop/mobile/)

   Windows Azure モバイル サービスに接続するユニバーサル Windows プラットフォーム (UWP) アプリまたは Windows デスクトップ アプリで使用できるネイティブの Api を提供します。 Web サイトの例のほとんどは C# を使用していますが、C++ も使用できます。 詳しくは、「 [クイック スタート: C++ を使ったモバイル サービスの追加](http://msdn.microsoft.com/library/windows/apps/dn263181.aspx)」をご覧ください。

- [C++ 用の Microsoft Azure ストレージ クライアント ライブラリ](https://blogs.msdn.microsoft.com/windowsazurestorage/2015/04/29/microsoft-azure-storage-client-library-for-c-v1-0-0-general-availability/)

   C++ 用の Azure ストレージ クライアント ライブラリには、次の機能など、Azure のストレージを使用するための包括的な API が用意されています。

  - 作成、読み取り、削除、および blob コンテナー、テーブル、およびキューを一覧表示します。
  - 作成、読み取り、正符号の blob を一覧とコピー読み書き可能な blob の範囲を削除します。
  - 挿入、削除、置換、merge、および Azure のテーブル内のエンティティをクエリします。
  - Enqueue および Azure キューにメッセージをデキューします。
  - コンテナー、blob、テーブル、キュー、および遅延ボックスの一覧し、遅延のエンティティをクエリ

- [OneDrive API](https://dev.onedrive.com/README.htm)

   OneDrive API では、一連のファイルおよび SharePoint Server 2016 と Office 365 でのフォルダーへのアプリケーションに接続する HTTP サービスを提供します。

- [C++ REST SDK (Codename "Casablanca")](https://github.com/Microsoft/cpprestsdk)

   REST サービスと対話するためには、最近、クロスプラット フォーム、非同期 API を提供します。

  - JSON ドキュメントの解析とシリアル化の組み込みサポートを持つ、任意の HTTP サーバーに対して REST 呼び出しを実行します。
  - OAuth 1 と 2、ローカルのリダイレクトのリスナーを含むをサポートしています
  - リモート サービスに対して Websocket の接続を確立します。
  - 完全に非同期タスク組み込み threadpool を含め、PPL に基づく API

   Windows デスクトップ (7 以降)、Windows Server (2012 以降)、ユニバーサル Windows プラットフォーム、Linux、os X、Android、および iOS をサポートしています。 

- [Windows::Web::Http::HttpClient](https://msdn.microsoft.com/en-us/library/windows/apps/windows.web.http.httpclient.aspx)

   System.Web 名前空間にある同じ名前の .NET Framework クラスでモデル化された Windows ランタイムの HTTP クライアント クラスです。 `HttpClient` は、HTTP 経由の非同期アップロードとダウンロード、およびパイプラインにカスタム HTTP ハンドラーを挿入するためのパイプライン フィルターを完全にサポートします。 Windows SDK には、メーター付きネットワークや OAuth 認証用のサンプル フィルターが含まれています。 使用することお勧めをユニバーサル Windows プラットフォームのみを対象とするアプリの場合、`Windows::Web:HttpClient`クラスです。 

- [IXMLHTTPRequest2 インターフェイス](http://msdn.microsoft.com/library/windows/apps/hh831151.aspx)

   HTTP 経由でインターネットに接続する Windows ランタイム アプリまたは Windows デスクトップ アプリで使用することができ、問題の GET、PUT などの他の HTTP コマンドをネイティブの COM インターフェイスを提供します。 詳細については、次を参照してください。[チュートリアル: 接続を使用してタスクおよび XML HTTP 要求](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)です。

- [Windows インターネット (WinInet)](http://msdn.microsoft.com/library/windows/desktop/aa385331\(v=vs.85\).aspx)

   Windows デスクトップ アプリでインターネットに接続するために使用できる Windows API。

## <a name="see-also"></a>関連項目

[Visual C++](../visual-cpp-in-visual-studio.md) <br/>
[ネットワークと web サービス](/windows/uwp/networking/)
