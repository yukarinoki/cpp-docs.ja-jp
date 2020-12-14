---
description: '詳細情報: MFC WinInet クラスを使用したインターネットクライアントアプリケーションの作成'
title: MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
ms.openlocfilehash: 61cfe3e9892f2bde6d233728b7b95ca0edd16ee8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189133"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法

すべてのインターネットクライアントアプリケーションの基礎は、インターネットセッションです。 MFC は、 [CInternetSession](../mfc/reference/cinternetsession-class.md)クラスのオブジェクトとしてインターネットセッションを実装します。 このクラスを使用すると、1つのインターネットセッションまたは複数の同時セッションを作成できます。

サーバーと通信するには、 [CInternetConnection](../mfc/reference/cinternetconnection-class.md) オブジェクトとも必要 `CInternetSession` です。 を作成する `CInternetConnection` には、 [CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)、 [CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)、または [CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection)を使用します。 これらの各呼び出しは、プロトコルの種類に固有です。 これらの呼び出しでは、読み取りまたは書き込みのためにサーバー上でファイルが開かれません。 データの読み取りまたは書き込みを行う場合は、別の手順としてファイルを開く必要があります。

ほとんどのインターネットセッションでは、 `CInternetSession` オブジェクトは [CInternetFile](../mfc/reference/cinternetfile-class.md) オブジェクトを使用して手動で動作します。

- インターネットセッションの場合は、 [CInternetSession](../mfc/reference/cinternetsession-class.md)のインスタンスを作成する必要があります。

- インターネットセッションでデータの読み取りまたは書き込みを行う場合は、のインスタンス `CInternetFile` (またはそのサブクラス、 [CHttpFile](../mfc/reference/chttpfile-class.md) 、または [CGopherFile](../mfc/reference/cgopherfile-class.md)) を作成する必要があります。 データを読み取る最も簡単な方法は、 [CInternetSession:: OpenURL](../mfc/reference/cinternetsession-class.md#openurl)を呼び出すことです。 この関数は、ユーザーが指定したユニバーサルリソースロケーター (URL) を解析し、URL で指定されたサーバーへの接続を開いて、読み取り専用のオブジェクトを返し `CInternetFile` ます。 `CInternetSession::OpenURL` は、1つのプロトコルの種類に固有ではありません。 FTP、HTTP、または gopher の URL に対して同じ呼び出しが機能します。 `CInternetSession::OpenURL` ローカルファイルでも機能します (ではなくが返さ `CStdioFile` `CInternetFile` れます)。

- インターネットセッションでデータの読み取りまたは書き込みを行わず、FTP ディレクトリ内のファイルを削除するなどの他のタスクを実行する場合は、のインスタンスを作成する必要はありません `CInternetFile` 。

オブジェクトを作成するには、次の2つの方法があり `CInternetFile` ます。

- を使用し `CInternetSession::OpenURL` てサーバー接続を確立すると、を呼び出すと `OpenURL` が返さ `CStdioFile` れます。

- 、、またはを使用してサーバー接続を確立する場合は、それぞれ、、またはを呼び出して、それぞれ、、またはを `CInternetSession::GetFtpConnection` `GetGopherConnection` `GetHttpConnection` 返す必要があり `CFtpConnection::OpenFile` `CGopherConnection::OpenFile` `CHttpConnection::OpenRequest` `CInternetFile` `CGopherFile` `CHttpFile` ます。

インターネットクライアントアプリケーションを実装する手順は、に基づく汎用インターネットクライアントを作成するか、 `OpenURL` いずれかの機能を使用するプロトコル固有のクライアントを作成するかによって異なり `GetConnection` ます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [FTP、HTTP、および gopher で一般的に機能するインターネットクライアントアプリケーションを作成操作方法には](../mfc/steps-in-a-typical-internet-client-application.md)

- [ファイルを開く FTP クライアントアプリケーションを作成操作方法には](../mfc/steps-in-a-typical-ftp-client-application.md)

- [ファイルを開かず、ディレクトリ操作 (ファイルの削除など) を実行する FTP クライアントアプリケーションを作成操作方法には](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [Gopher クライアントアプリケーションを作成操作方法には](../mfc/steps-in-a-typical-gopher-client-application.md)

- [HTTP クライアントアプリケーションを作成操作方法には](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[インターネットクライアントアプリケーションを作成するための MFC クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[インターネットクライアントクラスの前提条件](../mfc/prerequisites-for-internet-client-classes.md)
