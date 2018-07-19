---
title: インターネット クライアント クラスの前提条件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet files [MFC], writing to
- Internet [MFC], connections
- FTP (File Transfer Protocol), MFC classes
- Gopher prerequisites [MFC]
- files [MFC], writing to
- classes [MFC], connections
- HTTP [MFC], prerequisites for Internet clients
- connections [MFC], classes for
- Internet client class prerequisites [MFC]
- files [MFC], reading
- URLs [MFC], Internet client applications
- prerequisites, Internet client classes [MFC]
- Gopher client applications [MFC]
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6c16c3658ee5d27def4892997c50115dc0b8831
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354038"
---
# <a name="prerequisites-for-internet-client-classes"></a>インターネット クライアント クラスの必要条件
(たとえば、ファイルの読み取り)、インターネット クライアントによって実行されるいくつかの操作 (この場合は、インターネット接続を確立する) の前提条件を持つことです。 次の表は、一部のクライアント操作の前提条件を一覧表示します。  
  
### <a name="general-internet-url-ftp-gopher-or-http"></a>一般的なインターネット URL (FTP、Gopher、または HTTP)  
  
|アクション|必須コンポーネント|  
|------------|------------------|  
|接続を確立します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)インターネット クライアント アプリケーションの基礎を確立するためにします。|  
|URL を開きます。|接続を確立します。 呼び出す[できます](../mfc/reference/cinternetsession-class.md#openurl)です。 `OpenURL`関数は、読み取り専用のリソース オブジェクトを返します。|  
|データの読み取りの URL です。|URL を開きます。 呼び出す[細かい](../mfc/reference/cinternetfile-class.md#read)です。|  
|インターネット オプションを設定します。|接続を確立します。 呼び出す[CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption)です。|  
|ステータス情報で呼び出される関数を設定します。|接続を確立します。 呼び出す[CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)です。 オーバーライド[:onstatuscallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)呼び出しを処理します。|  
  
### <a name="ftp"></a>FTP  
  
|アクション|必須コンポーネント|  
|------------|------------------|  
|FTP 接続を確立します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)このインターネット クライアント アプリケーションの基礎として。 呼び出す[CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)を作成する、 [CFtpConnection](../mfc/reference/cftpconnection-class.md)オブジェクト。|  
|最初のリソースを検索します。|FTP 接続を確立します。 作成、 [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)オブジェクト。 呼び出す[CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile)です。|  
|すべての利用可能なリソースを列挙します。|最初のファイルを検索します。 呼び出す[CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile) FALSE が返されるまでです。|  
|FTP ファイルを開きます。|FTP 接続を確立します。 呼び出す[CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile)を作成して開く、 [CInternetFile](../mfc/reference/cinternetfile-class.md)オブジェクト。|  
|FTP ファイルを読み取る。|読み取りアクセス権を持つ FTP ファイルを開きます。 呼び出す[細かい](../mfc/reference/cinternetfile-class.md#read)です。|  
|FTP ファイルに書き込みます。|書き込みアクセス権を持つ FTP ファイルを開きます。 呼び出す[CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write)です。|  
|サーバー上のクライアントのディレクトリを変更します。|FTP 接続を確立します。 呼び出す[CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)です。|  
|サーバー上のクライアントの現在のディレクトリを取得します。|FTP 接続を確立します。 呼び出す[CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory)です。|  
  
### <a name="http"></a>HTTP  
  
|アクション|必須コンポーネント|  
|------------|------------------|  
|HTTP 接続を確立します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)このインターネット クライアント アプリケーションの基礎として。 呼び出す[代わりに](../mfc/reference/cinternetsession-class.md#gethttpconnection)を作成する、 [CHttpConnection](../mfc/reference/chttpconnection-class.md)オブジェクト。|  
|HTTP ファイルを開きます。|HTTP 接続を確立します。 呼び出す[しないで](../mfc/reference/chttpconnection-class.md#openrequest)を作成する、 [CHttpFile](../mfc/reference/chttpfile-class.md)オブジェクト。 呼び出す[CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders)です。 呼び出す[chttpfile::sendrequest](../mfc/reference/chttpfile-class.md#sendrequest)です。|  
|HTTP ファイルを読み取る。|HTTP ファイルを開きます。 呼び出す[細かい](../mfc/reference/cinternetfile-class.md#read)です。|  
|HTTP 要求に関する情報を取得します。|HTTP 接続を確立します。 呼び出す[しないで](../mfc/reference/chttpconnection-class.md#openrequest)を作成する、 [CHttpFile](../mfc/reference/chttpfile-class.md)オブジェクト。 呼び出す[CHttpFile::QueryInfo](../mfc/reference/chttpfile-class.md#queryinfo)です。|  
  
### <a name="gopher"></a>gopher  
  
|アクション|必須コンポーネント|  
|------------|------------------|  
|Gopher の接続を確立します。|作成、 [CInternetSession](../mfc/reference/cinternetsession-class.md)このインターネット クライアント アプリケーションの基礎として。 呼び出す[代わり](../mfc/reference/cinternetsession-class.md#getgopherconnection)を作成する、[関数](../mfc/reference/cgopherconnection-class.md)です。|  
|現在のディレクトリ内の最初のファイルを検索します。|Gopher の接続を確立します。 作成、 [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)オブジェクト。 呼び出す[CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator)を作成する、[関数](../mfc/reference/cgopherlocator-class.md)オブジェクト。 ロケーターを[CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile)です。 呼び出す[なった](../mfc/reference/cgopherfilefind-class.md#getlocator)必要がある場合、後で、ファイルのロケーターを取得します。|  
|すべての利用可能なファイルを列挙します。|最初のファイルを検索します。 呼び出す[CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) FALSE が返されるまでです。|  
|Gopher ファイルを開きます。|Gopher の接続を確立します。 Gopher ロケーターを作成[CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator)のロケーターを検索または[なった](../mfc/reference/cgopherfilefind-class.md#getlocator)です。 呼び出す[CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)です。|  
|Gopher ファイルを読み取る。|Gopher ファイルを開きます。 使用して[CGopherFile](../mfc/reference/cgopherfile-class.md)です。|  
  
## <a name="see-also"></a>関連項目  
 [Win32 インターネット拡張機能 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [インターネット クライアント アプリケーションの作成用の MFC クラス](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
