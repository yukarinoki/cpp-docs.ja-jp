---
description: 詳細については、「アプリケーション設計の選択」を参照してください。
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
ms.openlocfilehash: 0402cfe8cb58ed538e1429d2edc4f95cc9a23a0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335930"
---
# <a name="application-design-choices"></a>アプリケーションのデザイン上の検討事項

この記事では、インターネットのプログラミング時に考慮する必要がある設計上の問題について説明します。

この記事では、次のトピックについて説明します。

- [イントラネットとインターネット](#_core_intranet_versus_internet)

- [クライアントまたはサーバーアプリケーション](#_core_client_or_server_application)

- [Web ページ](#_core_the_web_page)

- [ブラウザーまたは Stand-Alone アプリケーション](#_core_browser_or_standalone)

- [インターネット上の COM](#_core_com_on_the_internet)

- [クライアントデータダウンロードサービス](#_core_client_data_download_services)

今すぐプログラムの記述を開始する準備ができている場合は、「 [MFC アプリケーションの作成](writing-mfc-applications.md)」を参照してください。

## <a name="intranet-versus-internet"></a><a name="_core_intranet_versus_internet"></a> イントラネットとインターネット

多くのアプリケーションはインターネット上で実行され、ブラウザーとインターネットアクセスを持つすべてのユーザーがアクセスできます。 企業は、TCP/IP プロトコルと Web ブラウザーを使用する企業全体のネットワークであるイントラネットも実装しています。 イントラネットは、簡単にアップグレード可能な中央のソースを提供して、会社全体の情報を提供します。 これらの情報は、ソフトウェアのアップグレード、カスタマーサポート、および情報配信のために使用できます。 次の表は、インターネットとイントラネットの機能を比較したものです。

|インターネット|イントラネット|
|--------------|--------------|
|低帯域幅|高帯域幅|
|データとシステムのセキュリティの低下|データおよびシステムへのアクセスを制御する|
|最小限のコンテンツ制御|コンテンツの高制御|

## <a name="client-or-server-application"></a><a name="_core_client_or_server_application"></a> クライアントまたはサーバーアプリケーション

アプリケーションは、クライアントコンピューターまたはサーバーコンピューターで実行できます。 また、アプリケーションをサーバーに保存し、インターネット経由でダウンロードして、クライアントコンピューターで実行することもできます。 MFC WinInet クラスは、クライアントアプリケーションがファイルをダウンロードするために使用されます。 MFC と非同期モニカークラスを使用して、ファイルおよびコントロールのプロパティをダウンロードします。 ActiveX コントロールおよびアクティブドキュメントのクラスは、クライアントアプリケーションおよびクライアントで実行するためにサーバーからダウンロードされるアプリケーションに使用されます。

## <a name="the-web-page-html-active-documents-activex-controls"></a><a name="_core_the_web_page"></a> Web ページ: HTML、アクティブドキュメント、ActiveX コントロール

Microsoft では、Web ページにコンテンツを提供するいくつかの方法を提供しています。 Web ページでは、オブジェクトタグなどの標準の HTML または HTML 拡張機能を使用して、ActiveX コントロールなどの動的なコンテンツを提供できます。

通常、Web ブラウザーは HTML ページを表示します。 アクティブドキュメントでは、COM 対応ブラウザーの単純なポイントアンドクリックインターフェイスにアプリケーションのデータを表示することもできます。 アクティブなドキュメントサーバーでは、クライアント領域全体にフレーム全体を表示し、独自のメニューやツールバーを表示できます。

作成した ActiveX コントロールは、サーバーから非同期的にダウンロードし、Web ページに表示できます。 VBScript などのスクリプト言語を使用して、サーバーに情報を送信する前にクライアント側の検証を実行することができます。

## <a name="browser-or-stand-alone-application"></a><a name="_core_browser_or_standalone"></a> ブラウザーまたは Stand-Alone アプリケーション

HTML ページに埋め込まれている ActiveX コントロールと、ブラウザーで表示されるアクティブなドキュメントサーバーを作成できます。 Web サーバーで ISAPI アプリケーションを実行するための要求を送信するためのボタンを含む HTML ページを作成できます。 ブラウザーアプリケーションを使用しなくても、インターネットプロトコルを使用してファイルをダウンロードし、ユーザーに情報を表示するスタンドアロンアプリケーションを作成できます。

## <a name="com-on-the-internet"></a><a name="_core_com_on_the_internet"></a> インターネット上の COM

ActiveX コントロール、アクティブドキュメント、および非同期モニカーはすべて、COM (コンポーネントオブジェクトモデル) テクノロジを使用します。

ActiveX コントロールは、インターネットサイト上のドキュメントやページに動的なコンテンツを提供します。 COM では、アクティブなドキュメントを使用して ActiveX コントロールとフルフレームドキュメントを作成できます。

非同期モニカーは、データをダウンロードする増分またはプログレッシブの方法を含め、インターネット環境でコントロールを適切に実行できるようにする機能を提供します。 また、コントロールは、同時にデータを非同期に取得する可能性がある他のコントロールとも連携して動作する必要があります。

## <a name="client-data-download-services"></a><a name="_core_client_data_download_services"></a> クライアントデータダウンロードサービス

クライアントへのデータ転送に役立つ2つの Api セットは、WinInet と非同期モニカーです。 HTML ページに大きな .gif ファイルと .avi ファイル、および ActiveX コントロールがある場合は、非同期モニカーを使用するか、または WinInet を非同期的に使用することで、ユーザーの応答性を高めることができます。

インターネット上の一般的なタスクは、データを転送しています。 アクティブなテクノロジを既に使用している場合 (ActiveX コントロールがある場合など) は、非同期モニカーを使用して、データのダウンロード時にデータをプログレッシブレンダリングできます。 WinInet を使用すると、HTTP、FTP、gopher などの一般的なインターネットプロトコルを使用してデータを転送できます。 どちらの方法でもプロトコルに依存しないため、WinSock と TCP/IP を使用する抽象レイヤーを提供します。 引き続き [WinSock](windows-sockets-in-mfc.md) を直接使用することができます。

次の表は、MFC を使用してインターネット経由でデータを転送するいくつかの方法をまとめたものです。

|このプロトコルを使用する|次の条件下|これらのクラスの使用|
|-----------------------|----------------------------|-------------------------|
|[非同期モニカーを使用したインターネットダウンロード](asynchronous-monikers-on-the-internet.md)|COM、ActiveX コントロール、および任意のインターネットプロトコルを使用した非同期転送の場合。|[CAsyncMonikerFile](reference/casyncmonikerfile-class.md)、 [CDataPathProperty](reference/cdatapathproperty-class.md)|
|[WinInet](win32-internet-extensions-wininet.md)|HTTP、FTP、および gopher 用のインターネットプロトコル。 データは同期的または非同期的に転送でき、システム全体のキャッシュに格納されます。|[CInternetSession](reference/cinternetsession-class.md)、 [CFtpFileFind](reference/cftpfilefind-class.md)、 [CGopherFileFind](reference/cgopherfilefind-class.md)などです。|
|[Firewall](windows-sockets-in-mfc.md)|最大限の効率と制御。 ソケットと TCP/IP プロトコルについて理解する必要があります。|[CSocket](reference/csocket-class.md)、 [CAsyncSocket](reference/casyncsocket-class.md)|

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングタスク](mfc-internet-programming-tasks.md)<br/>
[MFC インターネットプログラミングの基礎](mfc-internet-programming-basics.md)<br/>
[Win32 インターネット拡張機能 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[インターネット上の非同期モニカー](asynchronous-monikers-on-the-internet.md)
