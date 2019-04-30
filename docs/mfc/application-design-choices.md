---
title: アプリケーションのデザイン上の検討事項
ms.date: 11/04/2016
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
ms.openlocfilehash: cdb294e4ab808a7e4cbcec457f6e744eff9f12cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394664"
---
# <a name="application-design-choices"></a>アプリケーションのデザイン上の検討事項

この記事では、インターネットに対してプログラミングするときに考慮する設計上の問題について説明します。

この記事で説明したトピックは次のとおりです。

- [イントラネットとインターネットの比較](#_core_intranet_versus_internet)

- [クライアントまたはサーバー アプリケーション](#_core_client_or_server_application)

- [](#_core_the_web_page)

- [ブラウザーまたはスタンドアロンのアプリケーション](#_core_browser_or_standalone)

- [インターネット上で COM](#_core_com_on_the_internet)

- [クライアント データ サービスをダウンロードします。](#_core_client_data_download_services)

参照してくださいプログラムの作成を開始する準備が整ったら場合[MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)です。

##  <a name="_core_intranet_versus_internet"></a> イントラネットとインターネットの比較

多くのアプリケーションは、インターネット上で実行され、ブラウザーとインターネットへのアクセスを持つすべてのユーザーからアクセスできます。 企業イントラネットでは、これは、会社のネットワークの TCP/IP プロトコルを使用して Web ブラウザーも実装しています。 イントラネットでは、会社全体の情報のソースを簡単にアップグレード可能なサーバーの全体を提供します。 これらは、ソフトウェアをアップグレードするため、配信してアンケートをまとめる、カスタマー サポート、および情報の配信のために使用できます。 次の表は、インターネットおよびイントラネットの機能を比較します。

|インターネット|イントラネット|
|--------------|--------------|
|低帯域幅|高帯域幅|
|データとシステムのセキュリティが低下|データとシステムに対するアクセスの制御|
|コンテンツの最小限の制御|コンテンツの高いコントロール|

##  <a name="_core_client_or_server_application"></a> クライアントまたはサーバー アプリケーション

アプリケーションは、クライアント コンピューターまたはサーバー コンピューター上で実行できます。 アプリケーションは、可能性がありますも、サーバーに格納されていると、ダウンロード、インターネット経由でし実行するクライアント コンピューター。 MFC WinInet クラスは、ファイルをダウンロードするクライアント アプリケーションのために使用されます。 MFC と非同期モニカー クラスは、ファイルをダウンロードし、コントロールのプロパティに使用されます。 ActiveX コントロールとアクティブなドキュメントのクラスは、クライアント アプリケーションと、クライアントで実行するサーバーからダウンロードされるアプリケーションに使用されます。

##  <a name="_core_the_web_page"></a> Web ページ:HTML、アクティブなドキュメントは、ActiveX コントロール

Microsoft では、Web ページのコンテンツを提供するためのいくつかの方法を提供します。 標準の HTML または HTML web ページを使用できる ActiveX コントロールなどの動的なコンテンツを提供する、オブジェクト タグなどの拡張機能。

Web ブラウザーは、通常の HTML ページを表示します。 アクティブなドキュメントでは、COM 対応のブラウザーの単純なポイント アンド クリック インターフェイスでも、アプリケーションのデータを表示できます。 Active ドキュメント サーバーでは、全体のクライアント領域で、独自のメニューとツールバーで、ドキュメント、完全なフレームを表示できます。

記述する ActiveX コントロールをサーバーから非同期的にダウンロードし、Web ページに表示されます。 VBScript などのスクリプト言語を使用して、サーバーに情報を送信する前にクライアント側検証を実行することができます。

##  <a name="_core_browser_or_standalone"></a> ブラウザーまたはスタンドアロンのアプリケーション

HTML ページと、ブラウザーで表示されるアクティブなドキュメント サーバーに埋め込まれている ActiveX コントロールを記述することができます。 Web サーバー上の ISAPI アプリケーションを実行する要求を送信するためのボタンを含む HTML ページを記述することができます。 インターネット プロトコルを使用してファイルをダウンロードし、これまで、ブラウザー アプリケーションを使用せず、ユーザーに情報を表示するスタンドアロン アプリケーションを記述することができます。

##  <a name="_core_com_on_the_internet"></a> インターネット上で COM

ActiveX コントロール、アクティブなドキュメント、および非同期モニカーの COM (コンポーネント オブジェクト モデル) のテクノロジを使用します。

ActiveX コントロールは、インターネット サイト上のドキュメントおよびページに動的なコンテンツを提供します。 COM では、ActiveX コントロールとアクティブなドキュメントを使用して完全なフレームのドキュメントを構築できます。

非同期モニカーが増分など、インターネット環境で適切に動作するコントロールを有効にする機能を提供またはプログレッシブはデータをダウンロードすることを意味します。 コントロールは、同時に取得して、データ非同期的に同時に他のコントロールでうまく動作する必要がありますもします。

##  <a name="_core_client_data_download_services"></a> クライアント データ サービスをダウンロードします。

クライアントにデータを転送に役立つ Api の 2 つのセットは、WinInet と非同期モニカーです。 大きな .gif と .avi ファイル、HTML ページ上の ActiveX コントロールがある場合は、いずれかの非同期モニカーまたは非同期的に、WinInet を使用して、非同期的にダウンロードしてユーザーに応答性を高めることができます。

インターネット上の一般的なタスクがデータを転送しています。 (たとえば、ActiveX コントロールがある場合) アクティブなテクノロジを既に使用する場合は、プログレッシブ ダウンロード データを表示するために非同期モニカーを使用できます。 WinInet を使用して、HTTP、FTP、gopher などの一般的なインターネット プロトコルを使用してデータを転送することができます。 どちらの方法では、プロトコル独立性を提供し、WinSock、TCP/IP を使用する抽象層を提供します。 使用することもできます[WinSock](../mfc/windows-sockets-in-mfc.md)直接します。

次の表では、MFC を使用して、インターネット経由でデータを転送する方法はいくつかまとめたものです。

|このプロトコルを使用します。|これらの条件下で|これらのクラスを使用します。|
|-----------------------|----------------------------|-------------------------|
|[インターネットの非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)|COM、ActiveX コントロールを使用して非同期転送およびインターネット プロトコル。|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)、 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|HTTP、FTP、および gopher インターネット プロトコル。 データは同期的または非同期的に転送できるし、システム全体のキャッシュに格納されます。|[CInternetSession](../mfc/reference/cinternetsession-class.md)、 [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)、 [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)、その他。|
|[WinSock](../mfc/windows-sockets-in-mfc.md)|効率を最大化および制御します。 ソケットおよび TCP/IP プロトコルを理解が必要です。|[CSocket](../mfc/reference/csocket-class.md)、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)
