---
title: CGopherConnection クラス
ms.date: 11/04/2016
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
ms.openlocfilehash: eade1a82b674d5ad2e91146559139445ef017180
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373707"
---
# <a name="cgopherconnection-class"></a>CGopherConnection クラス

gopher インターネット サーバーへの接続を管理します。

> [!NOTE]
> クラス`CGopherConnection` `CGopherFile`、、`CGopherFileFind``CGopherLocator`およびメンバーは Windows XP プラットフォームでは動作しないため、非推奨になりましたが、以前のプラットフォームでは引き続き動作します。

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
|[CGopherConnection::ロケーターの作成](#createlocator)|Gopher サーバー上のファイルを検索する[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクトを作成します。|
|[コファーコネクション::ゲットアトリビュート](#getattribute)|gopher オブジェクトに関する属性情報を取得します。|
|[CGopherConnection::オープンファイル](#openfile)|gopher ファイルを開きます。|

## <a name="remarks"></a>解説

gopher サービスは、MFC WinInet クラスによって認識される 3 つのインターネット サービスの 1 つです。

このクラス`CGopherConnection`には、コンストラクタと、gopher サービスを管理する 3 つの追加のメンバー関数[が](#createlocator)含[GetAttribute](#getattribute)[まれています。](#openfile)

gopher インターネット サーバーと通信するには、まず CInternetSession のインスタンスを作成してから、オブジェクトを作成`CGopherConnection`してポインタを返す[CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)を呼び出す必要があります。 [CInternetSession](../../mfc/reference/cinternetsession-class.md) オブジェクトを`CGopherConnection`直接作成することはありません。

他の MFC`CGopherConnection`インターネット クラスとの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。 他の 2 つのサポートされているインターネット サービスの使用方法の詳細については、FTP と HTTP のクラス[CHttpConnection](../../mfc/reference/chttpconnection-class.md)と[CFtpConnection](../../mfc/reference/cftpconnection-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cgopherconnectioncgopherconnection"></a><a name="cgopherconnection"></a>CGopherConnection::CGopherConnection

このメンバー関数は、`CGopherConnection`オブジェクトを構築するために呼び出されます。

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

*セッション*<br/>
関連する C[インターネット セッション](../../mfc/reference/cinternetsession-class.md)オブジェクトへのポインター。

*hコネクテッド*<br/>
現在のインターネット セッションの Windows ハンドル。

*を行う*<br/>
FTP サーバー名を含む文字列へのポインター。

*dw コンテキスト*<br/>
操作のコンテキスト識別子。 *dwContext*は[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)によって返される操作の状態情報を識別します。 デフォルトは 1 に設定されています。ただし、操作に対して特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとオブジェクトが行うすべての作業は、そのコンテキスト ID に関連付けられます。

*ユーザー名*<br/>
ログインするユーザーの名前を指定する、NULL で終わる文字列へのポインター。 NULL の場合、デフォルトは匿名です。

*パスワード*<br/>
ログインに使用するパスワードを指定する、null で終わる文字列へのポインター。 *pstrPassword*と*pstrUserName*の両方が NULL の場合、既定の匿名パスワードはユーザーの電子メール名です。 *pstrPassword*が NULL (または空の文字列) で *、pstrUserName*が NULL でない場合は、空白のパスワードが使用されます。 次の表は、4 つの設定の*pstrUserName*と*pstrPassword*の動作を示しています。

|*ユーザー名*|*パスワード*|FTP サーバーに送信されたユーザー名|FTP サーバーに送信されるパスワード|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL または " "|NULL または " "|「匿名」|ユーザーの電子メール名|
|NULL 以外の文字列|NULL または " "|*ユーザー名*|" "|
|NULL 非 NULL 文字列|ERROR|ERROR||
|NULL 以外の文字列|NULL 以外の文字列|*ユーザー名*|*パスワード*|

*nポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

### <a name="remarks"></a>解説

`CGopherConnection`直接作成することはありません。 代わりに、オブジェクトを作成し、そのオブジェクトへのポインターを`CGopherConnection`返す[CISession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)を呼び出します。

## <a name="cgopherconnectioncreatelocator"></a><a name="createlocator"></a>CGopherConnection::ロケーターの作成

gopher サーバー上のファイルを検索または識別するための gopher ロケーターを作成します。

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

*文字列を表示します。*<br/>
取得する gopher ドキュメントまたはディレクトリの名前を含む文字列へのポインター。 *パラメーターが*NULL の場合は、gopher サーバーの既定のディレクトリが返されます。

*文字列*<br/>
項目を取得するために gopher サーバーに送信されるセレクター文字列へのポインター。 *文字列を*NULL にできます。

*ドウゴファータイプ*<br/>
これにより *、pstrSelectorString*がディレクトリまたはドキュメントを参照するかどうか、および要求が gopher であるか gopher+ であるかを指定します。 Windows SDK の構造[GOPHER_FIND_DATA](/windows/win32/api/wininet/ns-wininet-gopher_find_dataw)の属性を参照してください。

*プストルロケーター*<br/>
開くファイルを識別する文字列へのポインター。 一般的に、この文字列は[CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator)への呼び出しから返されます。

*サーバー名*<br/>
gopher サーバー名を含む文字列へのポインター。

*nポート*<br/>
この接続のインターネット ポートを識別する番号。

### <a name="return-value"></a>戻り値

[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクト。

### <a name="remarks"></a>解説

静的バージョンのメンバー関数ではサーバーを指定する必要がありますが、非静的バージョンでは接続オブジェクトのサーバー名が使用されます。

gopher サーバーから情報を取得するには、アプリケーションはまず gopher ロケーターを取得する必要があります。 アプリケーションは、そのロケーターを不透明トークンとして扱う必要があります (つまり、アプリケーションはロケーターを使用できますが、直接操作したり比較したりすることはできません)。 通常、アプリケーションは[、CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile)メンバー関数への呼び出しにロケーターを使用して、特定の情報を取得します。

## <a name="cgopherconnectiongetattribute"></a><a name="getattribute"></a>コファーコネクション::ゲットアトリビュート

gopher サーバーから項目に関する特定の属性情報を取得します。

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>パラメーター

*リロケータ*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクトへの参照。

*要求された属性*<br/>
要求された属性の名前を指定するスペースで区切られた文字列。

*結果*<br/>
ロケーターの種類を受け取る[CString](../../atl-mfc-shared/reference/cstringt-class.md)への参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

## <a name="cgopherconnectionopenfile"></a><a name="openfile"></a>CGopherConnection::オープンファイル

gopher サーバー上のファイルを開くには、このメンバー関数を呼び出します。

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*リロケータ*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクトへの参照。

*dwFlags*<br/>
INTERNET_FLAG_* フラグの任意の組み合わせ。 INTERNET_FLAG_フラグの詳細については[、CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl)を参照\*してください。

*を見る*<br/>
ファイル ビュー文字列へのポインター。 サーバーにファイルのビューが複数存在する場合、このパラメーターは開くファイル ビューを指定します。 *pstrView*が NULL の場合、既定のファイル ビューが使用されます。

*dw コンテキスト*<br/>
開かれているファイルのコンテキスト ID。 *dwContext*の詳細については **、「解説**」を参照してください。

### <a name="return-value"></a>戻り値

開く[CGopherFile](../../mfc/reference/cgopherfile-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

コンテキスト識別子を選択した値に設定するには *、dwContext*の既定値をオーバーライドします。 コンテキスト識別子は、[その CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト`CGopherConnection`によって作成されたオブジェクトのこの特定の操作に関連付けられます。 値は、それが識別される操作の状態を提供するために[CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="see-also"></a>関連項目

[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cftpconnection-class.md)<br/>
[CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[CGopherLocator クラス](../../mfc/reference/cgopherlocator-class.md)<br/>
[クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[CInternetSession クラス](../../mfc/reference/cinternetsession-class.md)
