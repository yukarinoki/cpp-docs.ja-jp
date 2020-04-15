---
title: WinInet の基礎
ms.date: 11/04/2016
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
ms.openlocfilehash: b989e5c3df63ee7b5129d01468a0f869772ed286
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367321"
---
# <a name="wininet-basics"></a>WinInet の基礎

WinInet を使用して、FTP サポートを追加して、アプリケーション内からファイルをダウンロードおよびアップロードできます。 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)をオーバーライドし *、dwContext*パラメーターを使用して、ファイルを検索およびダウンロードするときにユーザーに進行状況情報を提供できます。

この記事では、次のトピックを取り上げます。

- [非常に単純なブラウザを作成する](#_core_create_a_very_simple_browser)

- [Web ページのダウンロード](#_core_download_a_web_page)

- [ファイルの FTP](#_core_ftp_a_file)

- [Gopher ディレクトリを取得する](#_core_retrieve_a_gopher_directory)

- [ファイル転送時の進行状況情報の表示](#_core_display_progress_information_while_transferring_files)

以下のコードの抜粋では、単純なブラウザの作成方法、Web ページのダウンロード方法、ファイル FTP ファイルのダウンロード方法、gopher ファイルの検索方法を示します。 これらは完全な例としては意味されず、すべて例外処理が含まれているわけではありません。

WinInet の詳細については、「 [Win32 インターネット拡張機能 (WinInet)」](../mfc/win32-internet-extensions-wininet.md)を参照してください。

## <a name="create-a-very-simple-browser"></a><a name="_core_create_a_very_simple_browser"></a>非常に単純なブラウザを作成する

[!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]

## <a name="download-a-web-page"></a><a name="_core_download_a_web_page"></a>Web ページのダウンロード

[!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]

## <a name="ftp-a-file"></a><a name="_core_ftp_a_file"></a>ファイルの FTP

[!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]

## <a name="retrieve-a-gopher-directory"></a><a name="_core_retrieve_a_gopher_directory"></a>Gopher ディレクトリを取得する

[!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]

## <a name="use-onstatuscallback"></a>オンステータスコールバックを使用する

WinInet クラスを使用する場合は、アプリケーションの[CInternetSession](../mfc/reference/cinternetsession-class.md)オブジェクトの[OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)メンバーを使用して、状態情報を取得できます。 独自の`CInternetSession`オブジェクトを派生させ、`OnStatusCallback`をオーバーライドし、状態のコールバックを有効にした`OnStatusCallback`場合、MFC はそのインターネット セッションのすべてのアクティビティに関する進行状況情報を使用して関数を呼び出します。

1 つのセッションが複数の接続をサポートする場合があるため (有効期間中に、さまざまな異なる`OnStatusCallback`操作を実行する可能性があります)、特定の接続またはトランザクションで各状況変更を識別するメカニズムが必要です。 このメカニズムは、WinInet サポート クラスの多くのメンバー関数に与えられたコンテキスト ID パラメーターによって提供されます。 このパラメーターは常に**DWORD**型であり、常に*dwContext*という名前になります。

特定のインターネット オブジェクトに割り当てられたコンテキストは、オブジェクトがオブジェクトのメンバーで発生`OnStatusCallback`するアクティビティを`CInternetSession`識別するためにのみ使用されます。 呼び出`OnStatusCallback`しは、いくつかのパラメーターを受け取ります。これらのパラメータは連携して、どのトランザクションと接続の進行状況がアプリケーションに対して行われたかを示します。

オブジェクトを`CInternetSession`作成するときに、コンストラクターに*dwContext*パラメーターを指定できます。 `CInternetSession`それ自体はコンテキスト ID を使用しません。代わりに、コンテキスト ID は、独自のコンテキスト ID を明示的に取得しない任意の**InternetConnection**派生オブジェクトに渡されます。 さらに、異なる`CInternetConnection`コンテキスト ID を明示的に指定`CInternetFile`しない場合、これらのオブジェクトは、作成したオブジェクトにコンテキスト ID を渡します。 一方、独自のコンテキスト ID を指定した場合、オブジェクトと、そのコンテキスト ID に関連付けられた作業がオブジェクトと作業に関連付けられます。 コンテキスト ID を使用して、関数内で与えられているステータス情報を識別できます`OnStatusCallback`。

## <a name="display-progress-information-while-transferring-files"></a><a name="_core_display_progress_information_while_transferring_files"></a>ファイル転送時の進行状況情報の表示

たとえば、FTP サーバーとの接続を作成してファイルを読み取り、HTTP サーバーに接続して Web ページを取得するアプリケーションを作成する場合、`CInternetSession`オブジェクト、2`CInternetConnection`つのオブジェクト (1`CFtpSession`つは a、もう`CHttpSession`1 つは`CInternetFile`a)、2 つのオブジェクト (各接続に 1 つ) を作成します。 *dwContext*パラメーターにデフォルト値を使用した場合、FTP 接続の`OnStatusCallback`進行状況を示す呼び出しと HTTP 接続の進行状況を示す呼び出しを区別することはできません。 *dwContext* ID を指定すると、後で`OnStatusCallback`でテストできます。

## <a name="see-also"></a>関連項目

[MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)<br/>
[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)
