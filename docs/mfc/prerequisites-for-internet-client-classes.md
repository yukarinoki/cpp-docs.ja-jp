---
title: インターネット クライアント クラスの必要条件
ms.date: 11/04/2016
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
ms.openlocfilehash: aaf5756df69728e8ae89fb278bc0671bfc6840b7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619826"
---
# <a name="prerequisites-for-internet-client-classes"></a>インターネット クライアント クラスの必要条件

インターネットクライアント (ファイルの読み取りなど) によって実行される一部の操作には、前提条件となるアクション (この場合は、インターネット接続の確立) があります。 次の表に、一部のクライアントアクションの前提条件を示します。

### <a name="general-internet-url-ftp-gopher-or-http"></a>一般的なインターネット URL (FTP、Gopher、または HTTP)

|アクション|前提条件|
|------------|------------------|
|接続を確立します。|[CInternetSession](reference/cinternetsession-class.md)を作成して、インターネットクライアントアプリケーションの基礎を確立します。|
|URL を開きます。|接続を確立します。 [CInternetSession:: OpenURL](reference/cinternetsession-class.md#openurl)を呼び出します。 関数は、読み取り専用の `OpenURL` リソースオブジェクトを返します。|
|URL データを読み取ります。|URL を開きます。 [CInternetFile:: Read](reference/cinternetfile-class.md#read)を呼び出します。|
|インターネットオプションを設定します。|接続を確立します。 [CInternetSession:: SetOption](reference/cinternetsession-class.md#setoption)を呼び出します。|
|ステータス情報を使用して呼び出される関数を設定します。|接続を確立します。 [CInternetSession:: EnableStatusCallback](reference/cinternetsession-class.md#enablestatuscallback)を呼び出します。 呼び出しを処理するには、 [CInternetSession:: OnStatusCallback](reference/cinternetsession-class.md#onstatuscallback)をオーバーライドします。|

### <a name="ftp"></a>FTP

|アクション|前提条件|
|------------|------------------|
|FTP 接続を確立します。|このインターネットクライアントアプリケーションのベースとして[CInternetSession](reference/cinternetsession-class.md)を作成します。 [CInternetSession:: GetFtpConnection](reference/cinternetsession-class.md#getftpconnection)を呼び出して、 [CFtpConnection](reference/cftpconnection-class.md)オブジェクトを作成します。|
|最初のリソースを検索します。|FTP 接続を確立します。 [CFtpFileFind](reference/cftpfilefind-class.md)オブジェクトを作成します。 [CFtpFileFind:: FindFile](reference/cftpfilefind-class.md#findfile)を呼び出します。|
|使用可能なすべてのリソースを列挙します。|最初のファイルを検索します。 FALSE を返すまで[CFtpFileFind:: FindNextFile](reference/cftpfilefind-class.md#findnextfile)を呼び出します。|
|FTP ファイルを開きます。|FTP 接続を確立します。 [CFtpConnection:: OpenFile](reference/cftpconnection-class.md#openfile)を呼び出して、 [CInternetFile](reference/cinternetfile-class.md)オブジェクトを作成して開きます。|
|FTP ファイルを読み取ります。|読み取りアクセス権を持つ FTP ファイルを開きます。 [CInternetFile:: Read](reference/cinternetfile-class.md#read)を呼び出します。|
|FTP ファイルに書き込みます。|書き込みアクセス権を持つ FTP ファイルを開きます。 [CInternetFile:: Write](reference/cinternetfile-class.md#write)を呼び出します。|
|サーバー上のクライアントのディレクトリを変更します。|FTP 接続を確立します。 [CFtpConnection:: SetCurrentDirectory](reference/cftpconnection-class.md#setcurrentdirectory)を呼び出します。|
|サーバー上のクライアントの現在のディレクトリを取得します。|FTP 接続を確立します。 [CFtpConnection:: GetCurrentDirectory](reference/cftpconnection-class.md#getcurrentdirectory)を呼び出します。|

### <a name="http"></a>HTTP

|アクション|前提条件|
|------------|------------------|
|HTTP 接続を確立します。|このインターネットクライアントアプリケーションのベースとして[CInternetSession](reference/cinternetsession-class.md)を作成します。 [CInternetSession:: GetHttpConnection](reference/cinternetsession-class.md#gethttpconnection)を呼び出して、 [CHttpConnection](reference/chttpconnection-class.md)オブジェクトを作成します。|
|HTTP ファイルを開きます。|HTTP 接続を確立します。 [CHttpConnection:: OpenRequest](reference/chttpconnection-class.md#openrequest)を呼び出して、 [CHttpFile](reference/chttpfile-class.md)オブジェクトを作成します。 [CHttpFile:: AddRequestHeaders](reference/chttpfile-class.md#addrequestheaders)を呼び出します。 [CHttpFile:: SendRequest](reference/chttpfile-class.md#sendrequest)を呼び出します。|
|HTTP ファイルを読み取ります。|HTTP ファイルを開きます。 [CInternetFile:: Read](reference/cinternetfile-class.md#read)を呼び出します。|
|HTTP 要求に関する情報を取得します。|HTTP 接続を確立します。 [CHttpConnection:: OpenRequest](reference/chttpconnection-class.md#openrequest)を呼び出して、 [CHttpFile](reference/chttpfile-class.md)オブジェクトを作成します。 [CHttpFile:: QueryInfo](reference/chttpfile-class.md#queryinfo)を呼び出します。|

### <a name="gopher"></a>Gopher

|アクション|前提条件|
|------------|------------------|
|Gopher 接続を確立します。|このインターネットクライアントアプリケーションのベースとして[CInternetSession](reference/cinternetsession-class.md)を作成します。 [CInternetSession:: GetGopherConnection](reference/cinternetsession-class.md#getgopherconnection)を呼び出して、 [CGopherConnection](reference/cgopherconnection-class.md)を作成します。|
|現在のディレクトリ内の最初のファイルを検索します。|Gopher 接続を確立します。 [CGopherFileFind](reference/cgopherfilefind-class.md)オブジェクトを作成します。 [CGopherConnection:: CreateLocator](reference/cgopherconnection-class.md#createlocator)を呼び出して、 [CGopherLocator](reference/cgopherlocator-class.md)オブジェクトを作成します。 ロケーターを[CGopherFileFind:: FindFile](reference/cgopherfilefind-class.md#findfile)に渡します。 [CGopherFileFind:: GetLocator](reference/cgopherfilefind-class.md#getlocator)を呼び出して、後で必要になったときにファイルのロケーターを取得します。|
|使用可能なすべてのファイルを列挙します。|最初のファイルを検索します。 FALSE を返すまで[CGopherFileFind:: FindNextFile](reference/cgopherfilefind-class.md#findnextfile)を呼び出します。|
|Gopher ファイルを開きます。|Gopher 接続を確立します。 [CGopherConnection:: CreateLocator](reference/cgopherconnection-class.md#createlocator)を使用して gopher ロケーターを作成するか、 [CGopherFileFind:: getlocator](reference/cgopherfilefind-class.md#getlocator)でロケーターを検索します。 [CGopherConnection:: OpenFile](reference/cgopherconnection-class.md#openfile)を呼び出します。|
|Gopher ファイルを読み取ります。|Gopher ファイルを開きます。 [CGopherFile](reference/cgopherfile-class.md)を使用します。|

## <a name="see-also"></a>関連項目

[Win32 インターネット拡張機能 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[インターネット クライアント アプリケーションの作成用の MFC クラス](mfc-classes-for-creating-internet-client-applications.md)<br/>
[MFC WinInet クラスを使ってインターネット クライアント アプリケーションを作成する方法](writing-an-internet-client-application-using-mfc-wininet-classes.md)
