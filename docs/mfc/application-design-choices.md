---
title: アプリケーションの設計の選択肢 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76a49d2ecfc79e35da55d1393cf3880b15fba7d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="application-design-choices"></a>アプリケーションのデザイン上の検討事項
この記事では、インターネットのプログラミング時に考慮する設計上の問題について説明します。  
  
 この記事で説明されているトピックは次のとおりです。  
  
-   [イントラネットとインターネットの比較](#_core_intranet_versus_internet)  
  
-   [クライアントまたはサーバー アプリケーション](#_core_client_or_server_application)  
  
-   [](#_core_the_web_page)  
  
-   [ブラウザーまたはスタンドアロンのアプリケーション](#_core_browser_or_standalone)  
  
-   [インターネット上で COM](#_core_com_on_the_internet)  
  
-   [クライアント データ サービスをダウンロードします。](#_core_client_data_download_services)  
  
 参照してください、プログラムの作成を開始する準備ができたら場合[MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)です。  
  
##  <a name="_core_intranet_versus_internet"></a> イントラネットとインターネットの比較  
 多くのアプリケーションは、インターネット上で実行しには、ブラウザーとインターネット アクセスを持つユーザーにアクセスします。 企業は、イントラネット、TCP/IP プロトコルを使用して会社のネットワークと Web ブラウザーを実装してもいます。 イントラネットでは、会社全体の情報を簡単にアップグレード可能なサーバーの全体のソースを提供します。 これらは、ソフトウェアをアップグレードするためのアンケートを作表や、カスタマー サポート、および情報の配信のために使用できます。 次の表では、インターネットおよびイントラネットの機能を比較します。  
  
|インターネット|イントラネット|  
|--------------|--------------|  
|低帯域幅|高帯域幅|  
|データおよびシステムのセキュリティが低下|データおよびシステムへのアクセス制御|  
|コンテンツの最小限の制御|コンテンツの高いコントロール|  
  
##  <a name="_core_client_or_server_application"></a> クライアントまたはサーバー アプリケーション  
 アプリケーションには、クライアント コンピューターまたはサーバー コンピューターでを実行できます。 アプリケーションは、可能性がありますも、サーバーに格納されているとし、ダウンロード、インターネット経由でしてクライアント コンピューターで実行します。 MFC WinInet クラスは、ファイルをダウンロードするクライアント アプリケーションのために使用されます。 MFC と非同期モニカー クラスは、ファイルをダウンロードし、コントロールのプロパティに使用されます。 ActiveX コントロールとアクティブなドキュメントのクラスは、クライアント アプリケーションおよびクライアントを実行するサーバーからダウンロードされたアプリケーションで使用されます。  
  
##  <a name="_core_the_web_page"></a> Web ページ: HTML、アクティブなドキュメントは、ActiveX コントロール  
 Microsoft では、Web ページのコンテンツを提供するいくつかの方法を提供します。 標準の HTML または HTML web ページで使用できる ActiveX コントロールなどの動的なコンテンツを提供する、オブジェクト タグなどの拡張機能です。  
  
 Web ブラウザーは、通常の HTML ページを表示します。 アクティブなドキュメントでは、COM 対応のブラウザーの単純なポイント アンド クリック インターフェイスでも、アプリケーションのデータを表示できます。 Active ドキュメント サーバーでは、独自のメニューとツールバーで、全体のクライアント領域でドキュメントを完全なフレームを表示できます。  
  
 記述する ActiveX コントロールは、サーバーから非同期的にダウンロードおよび Web ページに表示されることができます。 VBScript などのスクリプト言語を使用して、サーバーに情報を送信する前にクライアント側検証を実行することができます。  
  
##  <a name="_core_browser_or_standalone"></a> ブラウザーまたはスタンドアロンのアプリケーション  
 HTML ページと、ブラウザーで表示される Active ドキュメント サーバーに埋め込まれている ActiveX コントロールを記述することができます。 Web サーバー上の ISAPI アプリケーションを実行する要求を送信するボタンを含む HTML ページを記述することができます。 インターネット プロトコルを使用してファイルをダウンロードし、これまで、ブラウザー アプリケーションを使用せずにユーザーに情報を表示するスタンドアロン アプリケーションを作成することができます。  
  
##  <a name="_core_com_on_the_internet"></a> インターネット上で COM  
 ActiveX コントロール、アクティブなドキュメント、および非同期モニカーは、COM (コンポーネント オブジェクト モデル) テクノロジを使用します。  
  
 ActiveX コントロールは、インターネット サイト上のドキュメントおよびページに動的なコンテンツを提供します。 COM では、ActiveX コントロールとアクティブなドキュメントを使用してフル フレーム ドキュメントを構築できます。  
  
 非同期モニカーが増分を含む、インターネット環境でもを実行するコントロールを有効にする機能を提供またはプログレッシブはデータをダウンロードすることを意味します。 コントロールは、可能性があるデータを取得して、非同期的に同時に他のコントロールでも動作もする必要があります。  
  
##  <a name="_core_client_data_download_services"></a> クライアント データ サービスをダウンロードします。  
 クライアントにデータを転送に役立つ Api の 2 つのセットとは、wininet の基礎と非同期モニカーです。 大きな .gif と .avi ファイル、HTML ページ上の ActiveX コントロールがある場合は、か非同期モニカーを使用するか、wininet の基礎を非同期的を使用して、非同期的にダウンロードして、ユーザーへの応答性を変更できます。  
  
 インターネット上の一般的なタスクはデータを転送しています。 Active テクノロジを使用して、(たとえば、ActiveX コントロールがある場合) は既に場合、は、プログレッシブ ダウンロードしながらデータを表示するために非同期モニカーを使用できます。 WinInet を使用して、HTTP、FTP、gopher などの一般的なインターネット プロトコルを使用してデータを転送することができます。 どちらの方法は、プロトコルに依存しないを示し、WinSock と TCP/IP の使用に抽象レイヤーを提供します。 使用することもできます[WinSock](../mfc/windows-sockets-in-mfc.md)直接です。  
  
 次の表では、MFC を使用して、インターネット経由でデータを転送する方法はいくつかまとめたものです。  
  
|このプロトコルを使用します。|これらの条件下で|これらのクラスを使用します。|  
|-----------------------|----------------------------|-------------------------|  
|[インターネット ダウンロードを使用して非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)|COM、ActiveX コントロールを使用して非同期転送およびインターネット プロトコル。|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)、[関数](../mfc/reference/cdatapathproperty-class.md)|  
|[Wininet の基礎](../mfc/win32-internet-extensions-wininet.md)|HTTP、FTP、および gopher インターネット プロトコル。 データは、同期または非同期で転送されることができ、システム全体のキャッシュに格納されます。|[CInternetSession](../mfc/reference/cinternetsession-class.md)、 [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)、 [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)、し、さらに多くです。|  
|[WinSock](../mfc/windows-sockets-in-mfc.md)|効率性を高めるおよび制御します。 ソケットおよび TCP/IP プロトコルを理解が必要です。|[CSocket](../mfc/reference/csocket-class.md)、 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)   
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)

