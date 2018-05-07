---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3dc5dae7758c77d335cf6e1255d8caba28df9f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cgopherconnection-class"></a>関数クラス
gopher インターネット サーバーへの接続を管理します。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`し、Windows XP のプラットフォームでは機能しませんが、引き続き以前のプラットフォームで動作するため、そのメンバーが使用されなくなりました。  
  
## <a name="syntax"></a>構文  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|`CGopherConnection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|作成、[関数](../../mfc/reference/cgopherlocator-class.md)gopher サーバー上のファイルを検索するオブジェクト。|  
|[CGopherConnection::GetAttribute](#getattribute)|Gopher オブジェクトの属性情報を取得します。|  
|[CGopherConnection::OpenFile](#openfile)|Gopher ファイルを開きます。|  
  
## <a name="remarks"></a>コメント  
 Gopher サービスは、MFC WinInet クラスによって認識される 3 つのインターネット サービスのいずれかです。  
  
 クラス`CGopherConnection`コンス トラクターと、gopher サービスを管理する次の 3 つの他のメンバー関数が含まれています: [OpenFile](#openfile)、 [CreateLocator](#createlocator)、および[GetAttribute](#getattribute).  
  
 Gopher インターネット サーバーを通信するためのインスタンスを作成する必要がありますまず[CInternetSession](../../mfc/reference/cinternetsession-class.md)、およびを呼び出す[代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)、作成する、 `CGopherConnection`オブジェクトし、ポインターを返します。 作成することはありません、`CGopherConnection`オブジェクトに直接できます。  
  
 方法の詳細について`CGopherConnection`クラスでは、その他の MFC インターネット機能が、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。 詳細については、その他の 2 つを使用するには、インターネット サービスがサポートされている、FTP、HTTP を参照してくださいクラス[CHttpConnection](../../mfc/reference/chttpconnection-class.md)と[CFtpConnection](../../mfc/reference/cftpconnection-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection  
 このメンバー関数は構築するために、`CGopherConnection`オブジェクト。  
  
```  
CGopherConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CGopherConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSession`  
 関連するへのポインター [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。  
  
 `hConnected`  
 現在のインターネット セッションの Windows ハンドル。  
  
 `pstrServer`  
 FTP サーバーの名前を含む文字列へのポインター。  
  
 `dwContext`  
 操作のコンテキストの識別子。 `dwContext` によって返される操作のステータス情報を識別する[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)です。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はしたコンテキスト ID と関連付けられます  
  
 `pstrUserName`  
 ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 場合**NULL**、既定値は匿名です。  
  
 `pstrPassword`  
 ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方`pstrPassword`と`pstrUserName`は**NULL**既定の匿名パスワードはユーザーの電子メール名。 場合`pstrPassword`は**NULL** (または空の文字列) が、`pstrUserName`は**NULL**、空白のパスワードを使用します。 次の表の 4 種類の設定の動作は、`pstrUserName`と`pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP サーバーに送信されるユーザー名|FTP サーバーに送信されたパスワード|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL**または""|**NULL**または""|「匿名」|ユーザーの電子メール名|  
|非- **NULL**文字列|**NULL**または""|`pstrUserName`|" "|  
|**NULL**以外**NULL**文字列|**エラー**|**エラー**||  
|非- **NULL**文字列|非- **NULL**文字列|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 サーバーで使用する TCP/IP ポートを識別する番号。  
  
### <a name="remarks"></a>コメント  
 作成することはありません、`CGopherConnection`直接です。 代わりに、呼び出し[代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)、作成する、`CGopherConnection`オブジェクトし、ポインターを返します。  
  
##  <a name="createlocator"></a>  CGopherConnection::CreateLocator  
 検索または gopher サーバー上のファイルを識別する gopher ロケーターを作成するには、このメンバー関数を呼び出します。  
  
```  
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType);  
  
static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

 
static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,  
    LPCTSTR pstrDisplayString,  
    LPCTSTR pstrSelectorString,  
    DWORD dwGopherType,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>パラメーター  
 `pstrDisplayString`  
 Gopher ドキュメントまたは取得するディレクトリの名前を含む文字列へのポインター。 場合、`pstrDisplayString`パラメーターは**NULL**、gopher サーバーの既定のディレクトリが返されます。  
  
 `pstrSelectorString`  
 項目を取得するために、gopher サーバーに送信されるセレクター文字列へのポインター。 `pstrSelectorString` 指定できます**NULL**です。  
  
 *dwGopherType*  
 これを指定するかどうか`pstrSelectorString`ディレクトリやドキュメントを参照および要求が gopher か gopher + です。 構造体の属性を参照してください[GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) Windows SDK に含まれています。  
  
 `pstrLocator`  
 開くには、ファイルを識別する文字列へのポインター。 一般に、この文字列への呼び出しから返される[なった](../../mfc/reference/cgopherfilefind-class.md#getlocator)です。  
  
 *pstrServerName*  
 Gopher サーバー名を含む文字列へのポインター。  
  
 `nPort`  
 この接続のインターネット ポートを識別する番号。  
  
### <a name="return-value"></a>戻り値  
 A[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 静的メンバー関数のバージョンでは、静的でないバージョンで、接続オブジェクトから、サーバー名を使用してサーバーを指定する必要があります。  
  
 Gopher サーバーから情報を取得するために、アプリケーションはまず gopher ロケーターを取得する必要があります。 アプリケーションは、不透明なトークンとしてロケーターを扱うし、必要があります (つまり、アプリケーションことができますロケーターを使用してが直接操作または比較)。 通常、アプリケーション、呼び出しのために、ロケーターを使用、 [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile)特定の情報を取得します。  
  
##  <a name="getattribute"></a>  CGopherConnection::GetAttribute  
 Gopher サーバーからの項目に関する特定の属性情報を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>パラメーター  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
 *strRequestedAttributes*  
 要求された属性の名前を指定する、スペースで区切られた文字列。  
  
 `strResult`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)ロケーターの種類を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
##  <a name="openfile"></a>  CGopherConnection::OpenFile  
 Gopher サーバー上のファイルを開くには、このメンバー関数を呼び出します。  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `refLocator`  
 参照、[関数](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
 `dwFlags`  
 INTERNET_FLAG_ * フラグの組み合わせ。 参照してください[できます](../../mfc/reference/cinternetsession-class.md#openurl)INTERNET_FLAG_ の詳細については\*フラグ。  
  
 `pstrView`  
 ファイル ビューの文字列へのポインター。 ファイルのいくつかのビューは、サーバーに存在する場合、このパラメーターは、ファイルを開くにはビューを指定します。 場合`pstrView`は**NULL**既定のファイルのビューを使用します。  
  
 `dwContext`  
 開いているファイルのコンテキスト ID です。 参照してください**解説**の詳細については`dwContext`します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CGopherFile](../../mfc/reference/cgopherfile-class.md)オブジェクトを開くことができません。  
  
### <a name="remarks"></a>コメント  
 `dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CGopherConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)特定ために使用する操作の状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/cinternetconnection-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFtpConnection クラス](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)   
 [関数クラス](../../mfc/reference/cinternetconnection-class.md)   
 [関数クラス](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)
