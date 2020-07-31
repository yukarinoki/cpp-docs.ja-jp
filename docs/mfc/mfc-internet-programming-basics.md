---
title: MFC インターネット プログラミングの基礎
ms.date: 11/19/2018
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
ms.openlocfilehash: c9825cdcb5cb0963a4e0d3acdeb36dfee54b70fc
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86405027"
---
# <a name="mfc-internet-programming-basics"></a>MFC インターネット プログラミングの基礎

Microsoft では、クライアントアプリケーションとサーバーアプリケーションの両方をプログラミングするための多くの Api を提供しています。 多くの新しいアプリケーションがインターネット向けに作成されています。また、テクノロジ、ブラウザーの機能、セキュリティオプションの変更により、新しい種類のアプリケーションが作成されます。 ブラウザーはクライアントコンピューター上で実行され、World Wide Web へのアクセスを提供し、テキスト、グラフィックス、ActiveX コントロール、およびドキュメントを含む HTML ページを表示します。 サーバーは、FTP、HTTP、および gopher サービスを提供し、CGI を使用してサーバー拡張アプリケーションを実行します。 カスタムアプリケーションは、情報を取得し、インターネット上のデータを提供することができます。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

![クライアントアプリケーションとサーバーアプリケーション](../mfc/media/vc38bq1.gif "クライアント サーバー アプリケーション")

MFC には、インターネットプログラミングをサポートするクラスが用意されています。 [COleControl](reference/colecontrol-class.md)および[CDocObjectServer](reference/cdocobjectserver-class.md)および関連する MFC クラスを使用して、ActiveX コントロールとアクティブなドキュメントを記述できます。 [CInternetSession](reference/cinternetsession-class.md)、 [CFtpConnection](reference/cftpconnection-class.md)、 [CAsyncMonikerFile](reference/casyncmonikerfile-class.md)などの MFC クラスを使用して、FTP、HTTP、gopher などのインターネットプロトコルを使用してファイルや情報を取得できます。

## <a name="in-this-section"></a>このセクションの内容

- [インターネット関連の MFC クラス](internet-related-mfc-classes.md)

- [トピック別のインターネット情報](internet-information-by-topic.md)

- [タスク別のインターネット情報](internet-information-by-task.md)

- [インターネット上のアクティブなテクノロジ](active-technology-on-the-internet.md)

- [WinInet の基礎](wininet-basics.md)

- [HTML の基礎](html-basics.md)

## <a name="related-sections"></a>関連項目

- [インターネット上の ActiveX コントロール](activex-controls-on-the-internet.md)

- [インターネット上の非同期モニカー](asynchronous-monikers-on-the-internet.md)

- [Win32 インターネット拡張機能 (WinInet)](win32-internet-extensions-wininet.md)

- [MFC インターネット プログラミングの作業](mfc-internet-programming-tasks.md)

- [アプリケーションのデザイン上の検討事項](application-design-choices.md)

- [MFC アプリケーションの作成](writing-mfc-applications.md)

- [インターネット アプリケーションのテスト](testing-internet-applications.md)

- [インターネット セキュリティ](internet-security-cpp.md)

- [DHTML コントロールに対する ATL のサポート](../atl/atl-support-for-dhtml-controls.md)

## <a name="websites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>Web サイトの詳細情報

Microsoft インターネットテクノロジの詳細については、「 [Microsoft Docs](https://docs.microsoft.com/)」を参照してください。

[World Wide Web コンソーシアム (W3C)](https://go.microsoft.com/fwlink/p/?linkid=37125)は、HTML、HTTP、CGI、およびその他の World Wide Web テクノロジの仕様を発行します。

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>その他のインターネットヘルプ

Windows SDK の OLE セクションには、OLE プログラミングに関する追加情報が含まれています。 この情報では、MFC クラスを使用するのではなく、Win32 WinInet 関数を直接使用する方法について詳しく説明します。 また、インターネットテクノロジの概要についても説明します。
