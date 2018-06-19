---
title: WinInet の基礎 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38506d0b25918bbc9d70ec1801971b070d620bf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385925"
---
# <a name="wininet-basics"></a>WinInet の基礎
WinInet を使用して、ダウンロードしてから、アプリケーション内のファイルをアップロードする FTP サポートを追加することができます。 オーバーライドできます[OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)を使用して、`dwContext`を検索して、ファイルをダウンロードすると、ユーザーに進行状況に関する情報を提供するパラメーターです。  
  
 この記事には、次のトピックが含まれています。  
  
-   [非常に単純なブラウザーを作成します。](#_core_create_a_very_simple_browser)  
  
-   [Web ページをダウンロードします。](#_core_download_a_web_page)  
  
-   [FTP ファイル](#_core_ftp_a_file)  
  
-   [Gopher ディレクトリを取得します。](#_core_retrieve_a_gopher_directory)  
  
-   [ファイルの転送中に進行状況に関する情報を表示します。](#_core_display_progress_information_while_transferring_files)  
  
 以下の各コードでは、単純なブラウザーの作成、Web ページ、FTP、ファイルをダウンロードおよび gopher ファイルを検索する方法を示します。 完全な例として、意図されていないとが含まれていない例外処理にはします。  
  
 Wininet の基礎の詳細については、次を参照してください。 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)です。  
  
##  <a name="_core_create_a_very_simple_browser"></a> 非常に単純なブラウザーを作成します。  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a> Web ページをダウンロードします。  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a> FTP ファイル  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Gopher ディレクトリを取得します。  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]  
  
## <a name="use-onstatuscallback"></a>OnStatusCallback を使用します。  
 WinInet クラスを使用するには、する場合は、使用、 [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) 、アプリケーションのメンバー [CInternetSession](../mfc/reference/cinternetsession-class.md)ステータス情報を取得するオブジェクト。 派生させた場合、独自`CInternetSession`オブジェクト、オーバーライド`OnStatusCallback`、状態のコールバックを有効にして MFC を呼び出す、`OnStatusCallback`進行状況が、インターネット、そのセッションで、すべてのアクティビティに関する情報を持つ関数です。  
  
 1 つのセッションは、いくつかの接続 (、有効期間が多くの異なる個別の操作を実行する可能性があります) をサポートするため`OnStatusCallback`特定の接続またはトランザクションの各状態の変更を識別するメカニズムが必要です。 このメカニズムは、WinInet のサポート クラスのメンバー関数の多くに指定されたコンテキストの ID パラメーターによって提供されます。 このパラメーターは常に型`DWORD`は常に名前と`dwContext`です。  
  
 インターネットの特定のオブジェクトに割り当てられているコンテキストが内のオブジェクトがアクティビティの識別にのみ使用されます、`OnStatusCallback`のメンバー、`CInternetSession`オブジェクト。 呼び出し`OnStatusCallback`いくつかのパラメーターを受け取るこれらのパラメーターが連携する進行状況がどのトランザクションと接続されています、アプリケーションに指示します。  
  
 作成するときに、`CInternetSession`オブジェクトを指定できます、`dwContext`コンス トラクターのパラメーターです。 `CInternetSession` 自体、コンテキスト ID を使用しません。いずれかにコンテキスト ID を渡す代わりに、**です**-独自のコンテキスト ID を取得しない明示的にオブジェクトを派生します。 それら`CInternetConnection`オブジェクトがに沿ってコンテキスト ID を渡す`CInternetFile`オブジェクトを別のコンテキスト ID を明示的に指定しない場合に作成します。 独自の特定のコンテキスト ID、オブジェクトおよびその動作はそのコンテキスト ID に関連付けられるを指定するはその一方で、 指定されているどのようなステータス情報を識別する Id コンテキストを使用することができます、`OnStatusCallback`関数。  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> ファイルの転送中に進行状況に関する情報を表示します。  
 たとえば、ファイルの読み取りに FTP サーバーとの接続を作成し、Web ページの取得に HTTP サーバーにも接続するアプリケーションを記述する場合があります、`CInternetSession`オブジェクト、2 つ`CInternetConnection`オブジェクト (いずれかになります、 **CFtpSession**し、もう一方が、 **CHttpSession**)、2 つと`CInternetFile`オブジェクト (接続ごとに 1 つ)。 既定値を使用した場合、`dwContext`パラメーターでないことができますを区別する、 `OnStatusCallback` FTP 接続と HTTP 接続の進行状況を示す呼び出しの進行状況を示す呼び出し。 指定した場合、 `dwContext` ID で、後でのテストできます`OnStatusCallback`、どの操作がコールバックを生成することがわかります。  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

