---
title: MFC WinInet クラスを使用してインターネット クライアント アプリケーションを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 822b75ec71d79b6e40ec6b61a77239707c32ce39
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384437"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法
すべてのインターネット クライアント アプリケーションの基礎は、インターネット セッションです。 MFC クラスのオブジェクトとしてインターネット セッションを実装する[CInternetSession](../mfc/reference/cinternetsession-class.md)です。 このクラスを使用して、1 つのインターネット セッションまたは複数の同時セッションを作成できます。  
  
 を、サーバーと通信する必要があります、[関数](../mfc/reference/cinternetconnection-class.md)オブジェクトと同様に、`CInternetSession`です。 作成することができます、`CInternetConnection`を使用して[CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)、[代わりに](../mfc/reference/cinternetsession-class.md#gethttpconnection)、または[代わり](../mfc/reference/cinternetsession-class.md#getgopherconnection). それらの各呼び出しは、プロトコルの種類に固有です。 これらの呼び出しには、サーバー上の読み取りまたは書き込みのファイルは開かないでください。 データを読み取ったり書き込んだりする場合は、個別の手順として、ファイルを開く必要があります。  
  
 ほとんどのインターネット セッションを`CInternetSession`オブジェクトの動作を手の形は手で、 [CInternetFile](../mfc/reference/cinternetfile-class.md)オブジェクト。  
  
-   インターネット セッションの場合は、インスタンスを作成する必要があります[CInternetSession](../mfc/reference/cinternetsession-class.md)です。  
  
-   インスタンスを作成する場合は、インターネット セッション データ読み取りまたは書き込みをする必要があります`CInternetFile`(またはそのサブクラス[CHttpFile](../mfc/reference/chttpfile-class.md)または[CGopherFile](../mfc/reference/cgopherfile-class.md))。 呼び出してデータを読み取る最も簡単な方法は、[できます](../mfc/reference/cinternetsession-class.md#openurl)です。 この関数は、入力された Universal Resource Locator (URL) を解析し、URL で指定されたサーバーへの接続を開きます読み取り専用を返します`CInternetFile`オブジェクト。 `CInternetSession::OpenURL` 1 つのプロトコルの種類に固有ではありません: 同じ呼び出しは、FTP、HTTP、または gopher URL に対して機能します。 `CInternetSession::OpenURL` ローカル ファイルにも使用 (を返す、`CStdioFile`の代わりに、 `CInternetFile`)。  
  
-   セッションは読み書きデータ、インターネットが FTP ディレクトリ内のファイルを削除するなど、他のタスクを実行する場合のインスタンスを作成する必要がありますいない`CInternetFile`です。  
  
 作成する方法を次の 2 つが、`CInternetFile`オブジェクト。  
  
-   使用する場合`CInternetSession::OpenURL`への呼び出し、サーバー接続を確立するために`OpenURL`を返します、`CStdioFile`です。  
  
-   場合を使用して**CInternetSession::GetFtpConnection**、 `GetGopherConnection`、または`GetHttpConnection`サーバー接続を確立するために呼び出す必要があります`CFtpConnection::OpenFile`、 `CGopherConnection::OpenFile`、または**しないで、** 、それぞれを返す、 `CInternetFile`、 `CGopherFile`、または`CHttpFile`、それぞれします。  
  
 インターネット クライアント アプリケーションの実装手順に基づいて汎用的なインターネット クライアントを作成するかどうかによって異なる**OpenURL**またはのいずれかを使用してプロトコル固有のクライアント、 **GetConnection**関数。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [FTP、HTTP、および gopher で一般的に動作するインターネット クライアント アプリケーションを記述する方法](../mfc/steps-in-a-typical-internet-client-application.md)  
  
-   [ファイルを開く FTP クライアント アプリケーションを記述する方法](../mfc/steps-in-a-typical-ftp-client-application.md)  
  
-   [ファイルを開くことができませんが、ファイルを削除するなどのディレクトリ操作を実行する FTP クライアント アプリケーションを記述する方法](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)  
  
-   [Gopher クライアント アプリケーションを作成する方法](../mfc/steps-in-a-typical-gopher-client-application.md)  
  
-   [HTTP クライアント アプリケーションを記述する方法](../mfc/steps-in-a-typical-http-client-application.md)  
  
## <a name="see-also"></a>関連項目  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント アプリケーションの作成用の MFC クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [インターネット クライアント クラスの必要条件](../mfc/prerequisites-for-internet-client-classes.md)
