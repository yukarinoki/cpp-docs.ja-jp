---
title: CGopherConnection クラス |Microsoft Docs
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
ms.openlocfilehash: 176dfc9027951f06f55dd04757b9acb7c7d8a2ec
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43199626"
---
# <a name="cgopherconnection-class"></a>CGopherConnection クラス
gopher インターネット サーバーへの接続を管理します。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`と Windows XP のプラットフォームで機能しませんが、引き続き以前のプラットフォームで動作するため、そのメンバーが使用されなくなりました。  
  
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
|[CGopherConnection::CreateLocator](#createlocator)|作成、 [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) gopher サーバー上のファイルを検索するオブジェクト。|  
|[CGopherConnection::GetAttribute](#getattribute)|Gopher オブジェクトの属性情報を取得します。|  
|[CGopherConnection::OpenFile](#openfile)|Gopher ファイルを開きます。|  
  
## <a name="remarks"></a>Remarks  
 Gopher サービスでは、MFC WinInet クラスによって認識される 3 つのインターネット サービスの 1 つです。  
  
 クラスは、`CGopherConnection`コンス トラクターと gopher サービスを管理する 3 つの追加のメンバー関数が含まれています: [OpenFile](#openfile)、 [CreateLocator](#createlocator)、および[GetAttribute](#getattribute).  
  
 Gopher インターネット サーバーと通信のインスタンスを作成する必要がありますまず[CInternetSession](../../mfc/reference/cinternetsession-class.md)を呼び出して[代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)、作成し、 `CGopherConnection`オブジェクトし、ポインターを返します。 作成することはありません、`CGopherConnection`オブジェクトに直接します。  
  
 方法の詳細については、`CGopherConnection`クラスでは、その他の MFC インターネット機能は、記事をご覧ください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。 FTP、HTTP が、クラスを参照する他の 2 つの使用に関する詳細については、インターネット サービスをサポートされている、 [CHttpConnection](../../mfc/reference/chttpconnection-class.md)と[CFtpConnection](../../mfc/reference/cftpconnection-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection  
 このメンバー関数が構築すると呼ばれる、`CGopherConnection`オブジェクト。  
  
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
 *pSession*  
 関連するへのポインター [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。  
  
 *hConnected*  
 現在のインターネット セッションの Windows ハンドル。  
  
 *pstrServer*  
 FTP サーバーの名前を含む文字列へのポインター。  
  
 *独自*  
 操作のコンテキストの識別子。 *独自*によって返される操作の状態情報を識別する[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)します。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はコンテキスト ID に関連付けられる  
  
 *pstrUserName*  
 ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 NULL の場合、既定値は匿名です。  
  
 *pstrPassword*  
 ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方*pstrPassword*と*pstrUserName*匿名の既定のパスワードはユーザーの電子メール名が NULL の場合。 場合*pstrPassword*が NULL (または空の文字列) が、 *pstrUserName*が NULL でない空白のパスワードを使用します。 次の表の 4 種類の設定の動作は、 *pstrUserName*と*pstrPassword*:  
  
|*pstrUserName*|*pstrPassword*|FTP サーバーに送信されるユーザー名|FTP サーバーに送信されたパスワード|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|NULL または""|NULL または""|「匿名」|ユーザーの電子メール名|  
|NULL 以外の文字列|NULL または""|*pstrUserName*|" "|  
|NULL 以外の文字列が NULL|ERROR|ERROR||  
|NULL 以外の文字列|NULL 以外の文字列|*pstrUserName*|*pstrPassword*|  
  
 *ポート*  
 サーバーで使用する TCP/IP ポートを識別する番号。  
  
### <a name="remarks"></a>Remarks  
 作成することはありません、`CGopherConnection`直接します。 代わりに、呼び出す[代わり](../../mfc/reference/cinternetsession-class.md#getgopherconnection)、作成し、`CGopherConnection`オブジェクトし、ポインターを返します。  
  
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
 *pstrDisplayString*  
 Gopher ドキュメントまたは取得するディレクトリの名前を含む文字列へのポインター。 場合、 *pstrDisplayString*パラメーターが NULL、gopher サーバーの既定のディレクトリが返されます。  
  
 *pstrSelectorString*  
 項目を取得するために、gopher サーバーに送信されるセレクター文字列へのポインター。 *pstrSelectorString* NULL を指定できます。  
  
 *dwGopherType*  
 これを指定するかどうか*pstrSelectorString*ディレクトリまたはドキュメントを参照しているかどうか、要求が gopher か gopher + とします。 構造の属性を参照してください。 [GOPHER_FIND_DATA](/windows/desktop/api/wininet/ns-wininet-gopher_find_dataa) Windows SDK に含まれています。  
  
 *pstrLocator*  
 開くファイルを識別する文字列へのポインター。 一般に、この文字列がへの呼び出しから返される[なった](../../mfc/reference/cgopherfilefind-class.md#getlocator)します。  
  
 *pstrServerName*  
 Gopher サーバー名を含む文字列へのポインター。  
  
 *ポート*  
 この接続のインターネットのポートを識別する番号。  
  
### <a name="return-value"></a>戻り値  
 A [CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 静的メンバー関数のバージョンでは、静的でないバージョンでは、接続オブジェクトから、サーバー名を使用するサーバーを指定する必要があります。  
  
 Gopher サーバーから情報を取得するために、アプリケーションはまず gopher ロケーターを取得する必要があります。 アプリケーションはロケーターを不透明なトークンとして扱う必要がありますし (は、アプリケーションできますロケーターを使用してが直接的にではありません操作または比較)。 通常、アプリケーションがへの呼び出しのロケーターを使用、 [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile)メンバー関数は、特定の情報を取得します。  
  
##  <a name="getattribute"></a>  CGopherConnection::GetAttribute  
 Gopher サーバーからの項目に関する特定の属性情報を取得するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>パラメーター  
 *refLocator*  
 参照を[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
 *strRequestedAttributes*  
 要求された属性の名前を指定する、スペースで区切られた文字列。  
  
 *strResult*  
 参照を[CString](../../atl-mfc-shared/reference/cstringt-class.md)ロケーターの種類を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。  
  
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
 *refLocator*  
 参照を[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
 *dwFlags*  
 INTERNET_FLAG_ * フラグの組み合わせ。 参照してください[できます](../../mfc/reference/cinternetsession-class.md#openurl)INTERNET_FLAG_ について詳しくは\*フラグ。  
  
 *pstrView*  
 ファイル ビューの文字列へのポインター。 ファイルのいくつかのビューは、サーバーに存在する場合、このパラメーターを開くには、どのファイル ビューを指定します。 場合*pstrView*が null の場合、既定のファイル ビューを使用します。  
  
 *独自*  
 開いているファイルのコンテキスト ID。 参照してください**解説**の詳細については*独自*します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CGopherFile](../../mfc/reference/cgopherfile-class.md)開かれているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 上書き、*独自*の既定値は、独自の値にコンテキスト id を設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CGopherConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)が識別される操作の状態を提供します。 記事をご覧ください[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)コンテキスト識別子の詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFtpConnection クラス](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator クラス](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)
