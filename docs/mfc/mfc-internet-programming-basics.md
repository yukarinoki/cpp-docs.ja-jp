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
ms.openlocfilehash: 5a8fb7bf07ec631869075c5977dcec468143ad56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366285"
---
# <a name="mfc-internet-programming-basics"></a>MFC インターネット プログラミングの基礎

Microsoft では、クライアント アプリケーションとサーバー アプリケーションの両方をプログラミングするための API を多数提供しています。 インターネット向けに多くの新しいアプリケーションが作成され、テクノロジ、ブラウザ機能、およびセキュリティ オプションが変更されると、新しい種類のアプリケーションが作成されます。 ブラウザはクライアント コンピュータ上で動作し、Www Web へのアクセスを提供し、テキスト、グラフィックス、ActiveX コントロール、およびドキュメントを含む HTML ページを表示します。 サーバーは FTP、HTTP、gopher サービスを提供し、CGI を使用してサーバー拡張アプリケーションを実行します。 カスタム アプリケーションは、インターネット上で情報を取得し、データを提供できます。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

![クライアント アプリケーションとサーバー アプリケーション](../mfc/media/vc38bq1.gif "クライアント サーバー アプリケーション")

MFC には、インターネット プログラミングをサポートするクラスが用意されています。 [COleControl](../mfc/reference/colecontrol-class.md)と[CDocObjectServer](../mfc/reference/cdocobjectserver-class.md)および関連する MFC クラスを使用して、ActiveX コントロールとアクティブ ドキュメントを記述できます。 [CInternetSession、CFtpConnection](../mfc/reference/cinternetsession-class.md)、および[CFtpConnection](../mfc/reference/cftpconnection-class.md)[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)などの MFC クラスを使用して、FTP、HTTP、gopher などのインターネット プロトコルを使用してファイルと情報を取得できます。

## <a name="in-this-section"></a>このセクションの内容

- [インターネット関連の MFC クラス](../mfc/internet-related-mfc-classes.md)

- [トピック別インターネット情報](../mfc/internet-information-by-topic.md)

- [タスク別のインターネット情報](../mfc/internet-information-by-task.md)

- [インターネット上のアクティブなテクノロジー](../mfc/active-technology-on-the-internet.md)

- [ウィニネットの基本](../mfc/wininet-basics.md)

- [HTML の基礎](../mfc/html-basics.md)

## <a name="related-sections"></a>関連項目

- [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)

- [インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)

- [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

- [MFC インターネット プログラミングの作業](../mfc/mfc-internet-programming-tasks.md)

- [アプリケーションのデザイン上の検討事項](../mfc/application-design-choices.md)

- [MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)

- [インターネット アプリケーションのテスト](../mfc/testing-internet-applications.md)

- [インターネット セキュリティ](../mfc/internet-security-cpp.md)

- [DHTML コントロールに対する ATL のサポート](../atl/atl-support-for-dhtml-controls.md)

## <a name="web-sites-for-more-information"></a><a name="_core_web_sites_for_more_information"></a>詳細については、Web サイト

マイクロソフトのインターネット テクノロジの詳細については、[マイクロソフト開発者ネットワーク (MSDN) Web](https://go.microsoft.com/fwlink/p/?linkid=56322)サイトを参照してください。 (リンクは予告なく変更される場合があります。

開発者向けのこの Web サイトには、Microsoft 開発ツールとテクノロジの使用に関する情報と、最近の会議と今後の会議に関するトップ 記事が含まれています。 このページから、.NET や XML デベロッパー センターなど、関連する多くの開発者向けサイトにアクセスできます。 ベータ版の SDK やサンプルもダウンロードできます。

[ワールドワイドウェブコンソーシアム(W3C)は](https://go.microsoft.com/fwlink/p/?linkid=37125)、HTML、HTTP、CGI、およびその他のワールドワイドウェブ技術の仕様を公開しています。

## <a name="more-internet-help"></a><a name="_core_more_internet_help"></a>その他のインターネット ヘルプ

Windows SDK の OLE セクションには、OLE プログラミングに関する追加情報が含まれています。 ここでは、MFC クラスを使用するのではなく、Win32 WinInet 関数を直接使用する方法について詳しく説明します。 また、インターネット テクノロジに関する概要情報も含まれています。
