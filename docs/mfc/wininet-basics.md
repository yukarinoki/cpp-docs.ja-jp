---
description: '詳細情報: WinInet の基礎'
title: WinInet の基礎
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: 1ba8f9b898476849ca9bbb39b7850bbce3605154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172779"
---
# <a name="wininet-basics"></a>WinInet の基礎

WinInet を使用すると、アプリケーション内からファイルをダウンロードしてアップロードするための FTP サポートを追加できます。 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)をオーバーライドし、 *dwContext* パラメーターを使用して、ファイルを検索してダウンロードするときに、進行状況に関する情報をユーザーに提供することができます。

この記事では、次のトピックを取り上げます。

- [非常に単純なブラウザーを作成する](#_core_create_a_very_simple_browser)

- [Web ページをダウンロードする](#_core_download_a_web_page)

- [ファイルの FTP](#_core_ftp_a_file)

- [Gopher ディレクトリを取得する](#_core_retrieve_a_gopher_directory)

- [ファイルの転送中に進行状況の情報を表示する](#_core_display_progress_information_while_transferring_files)

次のコードは、単純なブラウザーを作成する方法、Web ページをダウンロードする方法、ファイルを FTP する方法、gopher ファイルを検索する方法を示しています。 これらは完全な例としてではなく、例外処理が含まれているわけではありません。

WinInet の詳細については、「 [Win32 インターネット拡張機能 (wininet)](../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a> 非常に単純なブラウザーを作成する

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a> Web ページをダウンロードする

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a> ファイルの FTP

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a> Gopher ディレクトリを取得する

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>OnStatusCallback を使用する

WinInet クラスを使用する場合は、アプリケーションの[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトの[OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)メンバーを使用して、ステータス情報を取得できます。 独自のオブジェクトを派生し、を `CInternetSession` オーバーライドし `OnStatusCallback` て、ステータスコールバックを有効にすると、MFC は、 `OnStatusCallback` そのインターネットセッションのすべてのアクティビティに関する進行状況情報を使用して関数を呼び出します。

1つのセッションで複数の接続がサポートされる可能性があるため (その有効期間を通じて、多くの異なる操作を実行する可能性があります)、には `OnStatusCallback` 特定の接続またはトランザクションで各状態の変更を識別するメカニズムが必要です。 このメカニズムは、WinInet サポートクラスの多くのメンバー関数に与えられたコンテキスト ID パラメーターによって提供されます。 このパラメーターは常に **DWORD** 型で、常に *dwContext* という名前になります。

特定のインターネットオブジェクトに割り当てられたコンテキストは、オブジェクトのメンバーによって発生するアクティビティを識別するためにのみ使用され `OnStatusCallback` `CInternetSession` ます。 の呼び出しは、 `OnStatusCallback` いくつかのパラメーターを受け取ります。これらのパラメーターは連携して、トランザクションと接続の進行状況をアプリケーションに通知します。

オブジェクトを作成するときに `CInternetSession` 、コンストラクターに *dwContext* パラメーターを指定できます。 `CInternetSession` 自体はコンテキスト ID を使用しません。代わりに、コンテキスト id は、明示的にコンテキスト ID を取得しない **Internetconnection** の派生オブジェクトに渡します。 さらに、 `CInternetConnection` `CInternetFile` 別のコンテキスト id を明示的に指定しない場合、これらのオブジェクトは、作成したオブジェクトにコンテキスト id を渡します。 一方、独自のコンテキスト ID を指定した場合、オブジェクトとそのコンテキスト id に関連付けられているすべての作業が、そのコンテキスト ID に関連付けられます。 コンテキスト Id を使用すると、関数でどのような状態情報が与えられているかを識別でき `OnStatusCallback` ます。

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a> ファイルの転送中に進行状況の情報を表示する

たとえば、FTP サーバーとの接続を作成してファイルを読み取り、HTTP サーバーに接続して Web ページを取得するアプリケーションを作成する場合、オブジェクト、2つのオブジェクト (1 つはで、もう1つは `CInternetSession` `CInternetConnection` `CFtpSession` a `CHttpSession` )、2つの `CInternetFile` オブジェクト (接続ごとに1つ) があります。 *DwContext* パラメーターに既定値を使用した場合、 `OnStatusCallback` FTP 接続の進行状況を示す呼び出しと、HTTP 接続の進行状況を示す呼び出しを区別できません。 *DwContext* ID を指定すると、後ででのテストが可能に `OnStatusCallback` なり、コールバックが生成された操作がわかります。

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングの基礎](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)
