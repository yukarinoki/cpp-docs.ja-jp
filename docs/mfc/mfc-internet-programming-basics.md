---
title: MFC インターネット プログラミングの基礎 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ISAPI extensions, programming with ISAPI
- Internet applications [MFC]
- ISAPI
- ActiveX controls [MFC], Internet
- programming [MFC], Internet
- Web applications [MFC], MFC classes
- ISAPI filters [MFC], programming with ISAPI
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], writing
- Internet applications [MFC], Active technology
- Active technology [MFC]
- Internet content [MFC]
- WinInet classes [MFC]
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6896daddc0eb900f9e2a29497eb2dd8a1dc78446
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255610"
---
# <a name="mfc-internet-programming-basics"></a>MFC インターネット プログラミングの基礎
Microsoft は、クライアントとサーバーの両方のアプリケーションのプログラミングの多くの Api を提供します。 多くの新しいアプリケーションが、インターネットに書き込まれていると、テクノロジ、ブラウザーの機能、およびセキュリティ オプションの変更、新しい種類のアプリケーションが書き込まれます。 World Wide Web にアクセスするため、テキスト、グラフィック、ActiveX コントロール、およびドキュメントを含む HTML ページを表示して、クライアント コンピューターでブラウザーを実行します。 サーバーは、FTP、HTTP、および gopher サービスを提供し、CGI を使用してサーバー拡張機能のアプリケーションを実行します。 カスタム アプリケーションでは、情報を取得でき、インターネット上にデータを提供することができます。  
  
 ![クライアントおよびサーバー アプリケーション](../mfc/media/vc38bq1.gif "vc38bq1")  
  
 MFC は、インターネット プログラミングをサポートするクラスを提供します。 使用することができます[COleControl](../mfc/reference/colecontrol-class.md)と[関数](../mfc/reference/cdocobjectserver-class.md)と関連の MFC クラスが ActiveX コントロールとアクティブなドキュメントを記述します。 などの MFC クラスを使用することができます[CInternetSession](../mfc/reference/cinternetsession-class.md)、 [CFtpConnection](../mfc/reference/cftpconnection-class.md)、および[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)ファイルと、FTP などのインターネット プロトコルを使用して情報を取得するにはHTTP、および gopher です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [インターネット関連の MFC クラス](../mfc/internet-related-mfc-classes.md)  
  
-   [項目別のインターネット情報](../mfc/internet-information-by-topic.md)  
  
-   [タスク別のインターネット情報](../mfc/internet-information-by-task.md)  
  
-   [インターネット上の Active テクノロジ](../mfc/active-technology-on-the-internet.md)  
  
-   [WinInet の基礎](../mfc/wininet-basics.md)  
  
-   [HTML の基礎](../mfc/html-basics.md)  
  
## <a name="related-sections"></a>関連項目  
  
-   [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)  
  
-   [インターネット上の Active ドキュメント](../mfc/active-documents-on-the-internet.md)  
  
-   [インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)  
  
-   [アプリケーションのデザイン上の検討事項](../mfc/application-design-choices.md)  
  
-   [MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)  
  
-   [インターネット アプリケーションのテスト](../mfc/testing-internet-applications.md)  
  
-   [インターネット セキュリティ](../mfc/internet-security-cpp.md)  
  
-   [DHTML コントロールの ATL サポート](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a> 詳細については、Web サイト  
 Microsoft Internet テクノロジに関する詳細については、次を参照してください。、 [Microsoft Developer Network (MSDN)](http://go.microsoft.com/fwlink/p/?linkid=56322) Web サイトです。 (リンクは、将来予告なしに変更可能性があります)。  
  
 開発者向けのこの Web サイトには、Microsoft の開発ツールとテクノロジ、および最新と今後の会議のトップ記事の使用に関する情報が含まれています。 このページには、.NET、および XML のデベロッパー センターを含む、多くの関連 developer サイトにジャンプすることができます。 ベータ版の Sdk およびサンプルをダウンロードすることもできます。  
  
 [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/p/?linkid=37125) HTML、HTTP、CGI、およびその他の World Wide Web テクノロジの仕様を公開します。  
  
##  <a name="_core_more_internet_help"></a> さらにインターネット ヘルプ  
 Windows SDK の OLE セクションには、OLE プログラミングに関する追加情報が含まれています。 この情報は、MFC クラスではなく、直接、Win32 WinInet 関数の使用方法の詳細を説明します。 また、インターネット技術に関する概要情報も含まれます。  
  
## <a name="see-also"></a>関連項目  



