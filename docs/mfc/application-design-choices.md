---
title: アプリケーションのデザイン上の検討事項
ms.date: 09/12/2019
helpviewer_keywords:
- design
- application design [MFC], design goals
- application design [MFC], Internet applications
- Internet applications [MFC], designing applications
- Internet [MFC], vs. intranets
- applications [MFC], Internet
- server applications [MFC], vs. client applications on Internet
- client applications [MFC], vs. server applications on Internet
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
ms.openlocfilehash: 89f3e5c108de1cf7b3b73a33a08e2c50b1333c92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374627"
---
# <a name="application-design-choices"></a>アプリケーションのデザイン上の検討事項

この資料では、インターネット用プログラミング時に考慮すべき設計上の問題について説明します。

この記事で扱うトピックは次のとおりです。

- [イントラネットとインターネット](#_core_intranet_versus_internet)

- [クライアントアプリケーションまたはサーバーアプリケーション](#_core_client_or_server_application)

- [ウェブページ](#_core_the_web_page)

- [ブラウザまたはスタンドアロン アプリケーション](#_core_browser_or_standalone)

- [インターネット上の COM](#_core_com_on_the_internet)

- [クライアント データ ダウンロード サービス](#_core_client_data_download_services)

プログラムの作成を開始する準備が整ったら、「 [MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)」を参照してください。

## <a name="intranet-versus-internet"></a><a name="_core_intranet_versus_internet"></a>イントラネットとインターネット

多くのアプリケーションはインターネット上で動作し、ブラウザとインターネットアクセスを持つすべてのユーザーがアクセスできます。 企業は、TCP/IP プロトコルと Web ブラウザを使用した企業全体のネットワークであるイントラネットも実装しています。 イントラネットは、会社全体の情報を簡単にアップグレードできる中央ソースを提供します。 ソフトウェアのアップグレード、アンケートの提供と集計、カスタマー サポート、情報配信に使用できます。 次の表は、インターネットとイントラネットの機能を比較しています。

|インターネット|イントラネット|
|--------------|--------------|
|低帯域幅|高帯域幅|
|データとシステムのセキュリティの低下|データおよびシステムへのアクセス制御|
|コンテンツの最小限の制御|コンテンツの高い制御|

## <a name="client-or-server-application"></a><a name="_core_client_or_server_application"></a>クライアントアプリケーションまたはサーバーアプリケーション

アプリケーションは、クライアント コンピュータまたはサーバー コンピュータ上で実行できます。 アプリケーションはサーバーに保存され、インターネット経由でダウンロードされ、クライアント コンピュータ上で実行される場合もあります。 MFC WinInet クラスは、クライアント アプリケーションがファイルをダウンロードするために使用されます。 MFC クラスと非同期モニカー クラスは、ファイルとコントロールのプロパティをダウンロードするために使用されます。 ActiveX コントロールと Active ドキュメントのクラスは、クライアント アプリケーションと、サーバーからダウンロードされたアプリケーションでクライアント上で実行するために使用されます。

## <a name="the-web-page-html-active-documents-activex-controls"></a><a name="_core_the_web_page"></a>Web ページ: HTML、アクティブ ドキュメント、ActiveX コントロール

マイクロソフトでは、Web ページ上でコンテンツを提供する方法をいくつか提供しています。 Web ページでは、オブジェクト タグなどの標準の HTML または HTML 拡張機能を使用して、ActiveX コントロールなどの動的なコンテンツを提供できます。

通常、Web ブラウザには HTML ページが表示されます。 アクティブ ドキュメントは、COM 対応ブラウザの単純なポイント アンド クリック インターフェイスでアプリケーションのデータを表示することもできます。 Active ドキュメント サーバーでは、独自のメニューとツール バーを使用して、クライアント領域全体にドキュメント全体を表示できます。

作成した ActiveX コントロールは、サーバーから非同期的にダウンロードして Web ページに表示できます。 VBScript などのスクリプト言語を使用して、サーバーに情報を送信する前にクライアント側の検証を実行できます。

## <a name="browser-or-stand-alone-application"></a><a name="_core_browser_or_standalone"></a>ブラウザまたはスタンドアロン アプリケーション

HTML ページに埋め込まれた ActiveX コントロールと、ブラウザで表示される Active ドキュメント サーバーを作成できます。 ボタンを含む HTML ページを作成して、Web サーバー上で ISAPI アプリケーションを実行する要求を送信できます。 インターネット プロトコルを使用してファイルをダウンロードし、ブラウザ アプリケーションを使用せずにユーザーに情報を表示するスタンドアロン アプリケーションを作成できます。

## <a name="com-on-the-internet"></a><a name="_core_com_on_the_internet"></a>インターネット上の COM

ActiveX コントロール、Active ドキュメント、および非同期モニカーはすべて、COM (コンポーネント オブジェクト モデル) テクノロジを使用します。

ActiveX コントロールは、インターネット サイト上のドキュメントやページに動的なコンテンツを提供します。 COM を使用すると、ActiveX ドキュメントを使用して ActiveX コントロールおよびフルフレーム ドキュメントを作成できます。

非同期モニカーは、データをダウンロードするためのインクリメンタルまたはプログレッシブ手段を含む、インターネット環境でコントロールが適切に機能できるようにする機能を提供します。 コントロールは、同時に非同期的にデータを取得する他のコントロールともうまく動作する必要があります。

## <a name="client-data-download-services"></a><a name="_core_client_data_download_services"></a>クライアント データ ダウンロード サービス

クライアントにデータを転送するのに役立つ API の 2 つのセットは、WinInet と非同期モニカーです。 HTML ページに大きな .gif ファイルと .avi ファイルと ActiveX コントロールがある場合は、非同期モニカーを使用するか、WinInet を非同期に使用して非同期的にダウンロードすることで、ユーザーへの応答性を向上させることができます。

インターネット上で一般的なタスクは、データを転送します。 既に Active テクノロジを使用している場合 (たとえば、ActiveX コントロールを使用している場合)、非同期モニカーを使用して、ダウンロード時にデータを段階的にレンダリングできます。 WinInet を使用すると、HTTP、FTP、gopher などの一般的なインターネット プロトコルを使用してデータを転送できます。 どちらの方法もプロトコルの独立性を提供し、WinSock と TCP/IP を使用するための抽象層を提供します。 [WinSock](../mfc/windows-sockets-in-mfc.md)を直接使用することもできます。

次の表は、MFC を使用してインターネット経由でデータを転送する方法の一覧です。

|使用するプロトコル|これらの条件下で|これらのクラスの使用|
|-----------------------|----------------------------|-------------------------|
|[非同期モニカーを使用したインターネットダウンロード](../mfc/asynchronous-monikers-on-the-internet.md)|COM、ActiveX コントロール、およびインターネット プロトコルを使用した非同期転送。|[ファイル](../mfc/reference/casyncmonikerfile-class.md)[、CDataパスプロパティ](../mfc/reference/cdatapathproperty-class.md)|
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|HTTP、FTP、および gopher のインターネット プロトコルの場合。 データは同期または非同期で転送でき、システム全体のキャッシュに格納されます。|[C インターネットセッション](../mfc/reference/cinternetsession-class.md)、 [CFtp ファイル検索](../mfc/reference/cftpfilefind-class.md)、 [CGopher ファイル検索](../mfc/reference/cgopherfilefind-class.md)、および他の多くの.|
|[Winsock](../mfc/windows-sockets-in-mfc.md)|最大限の効率と制御のために。 ソケットと TCP/IP プロトコルを理解する必要があります。|[Cソケット](../mfc/reference/csocket-class.md)、[同期ソケット](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)
