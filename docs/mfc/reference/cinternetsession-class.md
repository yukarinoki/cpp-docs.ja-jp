---
title: CInternetSession クラス
ms.date: 06/20/2018
f1_keywords:
- CInternetSession
- AFXINET/CInternetSession
- AFXINET/CInternetSession::CInternetSession
- AFXINET/CInternetSession::Close
- AFXINET/CInternetSession::EnableStatusCallback
- AFXINET/CInternetSession::GetContext
- AFXINET/CInternetSession::GetCookie
- AFXINET/CInternetSession::GetCookieLength
- AFXINET/CInternetSession::GetFtpConnection
- AFXINET/CInternetSession::GetGopherConnection
- AFXINET/CInternetSession::GetHttpConnection
- AFXINET/CInternetSession::OnStatusCallback
- AFXINET/CInternetSession::OpenURL
- AFXINET/CInternetSession::SetCookie
- AFXINET/CInternetSession::SetOption
helpviewer_keywords:
- CInternetSession [MFC], CInternetSession
- CInternetSession [MFC], Close
- CInternetSession [MFC], EnableStatusCallback
- CInternetSession [MFC], GetContext
- CInternetSession [MFC], GetCookie
- CInternetSession [MFC], GetCookieLength
- CInternetSession [MFC], GetFtpConnection
- CInternetSession [MFC], GetGopherConnection
- CInternetSession [MFC], GetHttpConnection
- CInternetSession [MFC], OnStatusCallback
- CInternetSession [MFC], OpenURL
- CInternetSession [MFC], SetCookie
- CInternetSession [MFC], SetOption
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
ms.openlocfilehash: 216f3bf0ce62eb6e69ad0650289c4c2d91f95159
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178162"
---
# <a name="cinternetsession-class"></a>CInternetSession クラス

単一のインターネット セッションまたは複数の同時インターネット セッションを作成し、初期化します。必要な場合は、プロキシ サーバーへの接続も記述します。

## <a name="syntax"></a>構文

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CInternetSession::CInternetSession](#cinternetsession)|`CInternetSession` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CInternetSession::Close](#close)|インターネット セッションが終了した場合に、インターネット接続を閉じます。|
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|ステータス コールバック ルーチンを確立します。|
|[CInternetSession::GetContext](#getcontext)|インターネット セッションが終了した場合に、インターネット接続を閉じます。|
|[CInternetSession::GetCookie](#getcookie)|指定した URL とそのすべての親の Url の cookie を返します。|
|[CInternetSession::GetCookieLength](#getcookielength)|バッファーに格納されているクッキーの長さを指定する変数を取得します。|
|[CInternetSession::GetFtpConnection](#getftpconnection)|サーバーと FTP セッションを開きます。 ユーザーをログオンします。|
|[代わり](#getgopherconnection)|接続を開こうとするアプリケーションを gopher サーバーを開きます。|
|[代わりに](#gethttpconnection)|接続を開こうとしているアプリケーションの HTTP サーバーを開きます。|
|[代入できます。](#onstatuscallback)|ステータス コールバックが有効にすると、操作の状態を更新します。|
|[できます](#openurl)|解析し、URL が開かれます。|
|[CInternetSession::SetCookie](#setcookie)|指定された URL の cookie を設定します。|
|[CInternetSession::SetOption](#setoption)|インターネット セッションのオプションを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CInternetSession::operator HINTERNET](#operator_hinternet)|現在のインターネット セッションへのハンドル。|

## <a name="remarks"></a>Remarks

作成することができる場合、アプリケーションの間のインターネット接続を維持する必要があります、`CInternetSession`クラスのメンバー [CWinApp](../../mfc/reference/cwinapp-class.md)します。

インターネット セッションが確立されると、呼び出す[OpenURL](#openurl)します。 `CInternetSession` グローバル関数を呼び出すことによって、URL を解析[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)します。 そのプロトコルの種類に関係なく`CInternetSession`URL を解釈し、管理します。 URL リソース file:// で識別されるローカル ファイルへの要求を処理できます。 `OpenURL` ポインターを返す、 [CStdioFile](../../mfc/reference/cstdiofile-class.md)オブジェクトの名前値を渡す場合は、ローカル ファイル。

使用してインターネット サーバーの URL を開くかどうか`OpenURL`、サイトから情報を読み取ることができます。 サーバー上にあるファイル (例、HTTP、FTP、または gopher) 用のサービスに固有の操作を実行する場合は、そのサーバーに適切な接続を確立する必要があります。 特定の種類の特定のサービスに直接接続を開くには、するには、次のメンバー関数のいずれかを使用します。

- [GetGopherConnection](#getgopherconnection) gopher サービスへの接続を開きます。

- [GetHttpConnection](#gethttpconnection)を HTTP サービスへの接続を開きます。

- [GetFtpConnection](#getftpconnection) FTP サービスへの接続を開きます。

[SetOption](#setoption)タイムアウト値、再試行の回数など、セッションのクエリ オプションを設定したりすることができます。

`CInternetSession` メンバー関数[SetCookie](#setcookie)、 [GetCookie](#getcookie)、および[GetCookieLength](#getcookielength)サーバーとスクリプトの管理により、Win32 cookie データベースを管理する手段を提供クライアント ワークステーションに関する状態情報。

インターネットの基本的なプログラミング タスクの詳細については、記事を参照してください。[インターネットの最初の手順。WinInet](../../mfc/wininet-basics.md)します。 MFC WinInet クラスを使用する全般については、記事を参照してください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。

> [!NOTE]
> `CInternetSession` スローされます、 [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)サポートされていないサービスの種類。 次の種類のサービスのみが現在サポートされています。FTP、HTTP、gopher、およびファイルです。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cinternetsession"></a> CInternetSession::CInternetSession

このメンバー関数が呼び出されます、`CInternetSession`オブジェクトが作成されます。

```cpp
CInternetSession(
    LPCTSTR pstrAgent = NULL,
    DWORD_PTR dwContext = 1,
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,
    LPCTSTR pstrProxyName = NULL,
    LPCTSTR pstrProxyBypass = NULL,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>パラメーター

*pstrAgent*<br/>
アプリケーションまたはインターネットの機能 (たとえば、「Microsoft インターネット ブラウザー」) を呼び出してエンティティ名前を識別する文字列へのポインター。 場合*pstrAgent* NULL (既定)、フレームワークによって、グローバル関数は、 [AfxGetAppName](application-information-and-management.md#afxgetappname)アプリケーションの名前を含む null で終わる文字列が返されます。 一部のプロトコルは、サーバーにアプリケーションを識別するために、この文字列を使用します。

*独自*<br/>
操作のコンテキストの識別子。 *独自*によって返される操作の状態情報を識別する[対応](#onstatuscallback)します。 既定値を 1 に設定します。ただし、操作の特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとその動作はコンテキスト ID に関連付けられる

*は*<br/>
必要なアクセスの種類。 次に、有効な値、うち 1 つだけを指定することがあります。

- INTERNET_OPEN_TYPE_PRECONFIG 接続に使用するには、レジストリの設定が構成済みです。 このアクセスの種類は、既定値として設定されます。 このプロキシ経由の接続に次のように設定します。*は*; でこの値にする、レジストリを適切に設定します。

- INTERNET_OPEN_TYPE_DIRECT は、インターネットに直接接続します。

- INTERNET_OPEN_TYPE_PROXY CERN プロキシ経由で接続します。

さまざまな種類のプロキシに接続する方法については、次を参照してください。[典型的な FTP クライアント アプリケーションでのステップ](../../mfc/steps-in-a-typical-ftp-client-application.md)します。

*pstrProxyName*<br/>
優先 CERN プロキシの名前場合*は*INTERNET_OPEN_TYPE_PROXY として設定されます。 既定では NULL です。

*pstrProxyBypass*<br/>
サーバーのアドレスのオプションのリストを含む文字列へのポインター。 プロキシへのアクセスを使用する場合は、これらのアドレスを迂回する可能性があります。 NULL 値が指定されている場合は、レジストリからバイパス リストを読み取ります。 このパラメーターは、意味のある場合にのみ*は*INTERNET_OPEN_TYPE_PROXY に設定されます。

*dwFlags*<br/>
さまざまなキャッシュ オプションを示します。 既定値は 0 に設定されます。 使用可能な値は次のとおりです。

- ローカルまたはゲートウェイ サーバーでは、データをキャッシュ INTERNET_FLAG_DONT_CACHE しません。

- INTERNET_FLAG_OFFLINE ダウンロード操作は、により、永続的なキャッシュにのみ満たされます。 項目がキャッシュに存在しない場合は、適切なエラー コードが返されます。 このフラグは、ビットごとに組み合わせることができます**または**( **&#124;**) 演算子。

### <a name="remarks"></a>Remarks

`CInternetSession` 最初のインターネット関数は、アプリケーションによって呼び出されます。 内部データ構造体を初期化し、アプリケーションからの以降の呼び出しを準備します。

インターネット接続を開くことができる場合`CInternetSession`スロー、 [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)します。

### <a name="example"></a>例

例をご覧ください[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)します。

## <a name="close"></a>  CInternetSession::Close

使用して、アプリケーションが完了すると、このメンバー関数を呼び出し、`CInternetSession`オブジェクト。

```cpp
virtual void Close();
```

### <a name="example"></a>例

例をご覧ください[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)します。

## <a name="enablestatuscallback"></a>  CInternetSession::EnableStatusCallback

ステータス コールバックを有効にするには、このメンバー関数を呼び出します。

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
コールバックが有効になっているかどうかを指定します。 既定では TRUE です。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しに失敗した場合は、スローされたエラーの原因を特定[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

ステータス コールバックを処理する際は、アプリケーションのステータス バーに (名前の解決、サーバーに接続する) などの操作の進行状況に関する状態を行うことができます。 長期的な操作中には、特には操作の状態が表示されます。

コールバックは、要求の処理中に発生する、ため、アプリケーションは、ネットワークへのデータのスループットの低下を防ぐために、コールバック内で可能な時間を節約する必要があります。 たとえば、コールバックでは、ダイアログ ボックスを配置するには、時間のかかる操作、サーバーは要求を終了する可能性があります。

ステータス コールバックは、任意のコールバックが保留になっている限り削除できません。

すべての操作を非同期的に処理するためには、独自のスレッドを作成するか、MFC を使用せず、WinInet 関数を使用する必要があります。

## <a name="getcontext"></a>  CInternetSession::GetContext

特定のアプリケーションのセッション コンテキスト値を取得するには、このメンバー関数を呼び出します。

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>戻り値

アプリケーションで定義されたコンテキストの識別子。

### <a name="remarks"></a>Remarks

[OnStatusCallback](#onstatuscallback)によって返されるコンテキスト ID を使用して`GetContext`特定のアプリケーションの状態を報告します。 たとえば、ユーザーがステータス情報を返す必要がありますインターネット要求をアクティブ化、ステータス コールバックはその特定の要求の状態をレポートのコンテキスト ID を使用します。 場合は、ユーザーが 2 つの異なるインターネット要求のステータス情報を返す処理を伴う`OnStatusCallback`コンテキスト識別子を使用して、対応する要求の状態を返します。 その結果、すべてのステータス コールバック操作コンテキスト識別子が使用され、セッションが終了するまで、セッションに関連付けられています。

非同期操作の詳細については、記事を参照してください。[インターネットの最初の手順。WinInet](../../mfc/wininet-basics.md)します。

## <a name="getcookie"></a>  CInternetSession::GetCookie

このメンバー関数は、Win32 関数の動作を実装[InternetGetCookie](/windows/desktop/api/wininet/nf-wininet-internetgetcookiea)」の説明に従って、Windows SDK。

```cpp
static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPTSTR pstrCookieData,
    DWORD dwBufLen);

static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    CString& strCookieData);
```

### <a name="parameters"></a>パラメーター

*pstrUrl*<br/>
URL を含む文字列へのポインター。

*pstrCookieName*<br/>
指定した URL を取得するクッキーの名前を含む文字列へのポインター。

*pstrCookieData*<br/>
最初のオーバー ロードで、cookie のデータを受信するバッファーのアドレスを含む文字列へのポインター。 この値は NULL を指定できます。 2 番目のオーバー ロードへの参照では、 [CString](../../atl-mfc-shared/reference/cstringt-class.md) cookie のデータを受信するオブジェクト。

*dwBufLen*<br/>
サイズを指定する変数、 *pstrCookieData*バッファー。 バッファーにコピーされたデータの量を受け取る関数が成功した場合、 *pstrCookieData*バッファー。 場合*pstrCookieData*が null の場合、このパラメーターは、すべての cookie データをコピーするために必要なバッファーのサイズを指定する値を受け取ります。

### <a name="return-value"></a>戻り値

それ以外の場合、成功した場合、TRUE または FALSE を返します。 呼び出しに失敗した場合は、Win32 関数を呼び出す[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定します。 次のエラー値が適用されます。

- ERROR_NO_MORE_ITEMS は指定された URL の cookie とそのすべての親です。

- 渡された値 ERROR_INSUFFICIENT_BUFFER *dwBufLen* cookie のすべてのデータをコピーするには不十分です。 戻り値*dwBufLen*バッファーのサイズは、すべてのデータを取得するために必要です。

### <a name="remarks"></a>Remarks

2 番目のオーバー ロードでは、MFC は、指定されたに cookie のデータを取得します`CString`オブジェクト。

## <a name="getcookielength"></a>  CInternetSession::GetCookieLength

バッファーに格納されているクッキーの長さを取得するには、このメンバー関数を呼び出します。

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>パラメーター

*pstrUrl*<br/>
URL を含む文字列へのポインター

*pstrCookieName*<br/>
Cookie の名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

Cookie の長さを示す DWORD 値は、バッファーに格納します。 によって示される名前の cookie なしの場合は 0 *pstrCookieName*存在します。

### <a name="remarks"></a>Remarks

この値がによって使用[GetCookie](#getcookie)します。

## <a name="getftpconnection"></a>  CInternetSession::GetFtpConnection

FTP 接続を確立し、ポインターを取得するには、このメンバー関数を呼び出して、`CFtpConnection`オブジェクト。

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>パラメーター

*pstrServer*<br/>
FTP サーバーの名前を含む文字列へのポインター。

*pstrUserName*<br/>
ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 NULL の場合、既定値は匿名です。

*pstrPassword*<br/>
ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方*pstrPassword*と*pstrUserName*匿名の既定のパスワードはユーザーの電子メール名が NULL の場合。 場合*pstrPassword*が NULL (または空の文字列) が、 *pstrUserName*が NULL でない空白のパスワードを使用します。 次の表の 4 種類の設定の動作は、 *pstrUserName*と*pstrPassword*:

| *pstrUserName*  | *pstrPassword*  | FTP サーバーに送信されるユーザー名 | FTP サーバーに送信されたパスワード |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   NULL または""   |   NULL または""   |         「匿名」         |      ユーザーの電子メール名      |
| NULL 以外の文字列 |   NULL または""   |       *pstrUserName*        |             " "             |
|      NULL       | NULL 以外の文字列 |            ERROR            |            ERROR            |
| NULL 以外の文字列 | NULL 以外の文字列 |       *pstrUserName*        |       *pstrPassword*        |

*ポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

*bPassive*<br/>
この FTP セッションをパッシブまたはアクティブ モードを指定します。 かどうかは TRUE に設定すると、設定、Win32 API `dwFlag` INTERNET_FLAG_PASSIVE にします。

### <a name="return-value"></a>戻り値

ポインターを[CFtpConnection](../../mfc/reference/cftpconnection-class.md)オブジェクト。 呼び出しに失敗した場合は、スローされたエラーの原因を特定[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

`GetFtpConnection` FTP サーバーに接続を作成してへのポインターを返します、`CFTPConnection`オブジェクト。 サーバー上の特定の操作を行うことはできません。 ファイルに対する読み取りまたは書き込みする場合は、たとえば、別の手順としてこれらの操作を実行する必要があります。 クラスを参照してください。 [CFtpConnection](../../mfc/reference/cftpconnection-class.md)と[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)ファイルの検索方法の詳細については、開く、ファイルの読み取りやファイルへの書き込み。 記事をご覧ください[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)FTP 接続の一般的なタスクを実行する手順について。

### <a name="example"></a>例

例をご覧ください[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)します。

## <a name="getgopherconnection"></a>  代わり

Gopher の新しい接続を確立し、ポインターを取得するには、このメンバー関数を呼び出して、`CGopherConnection`オブジェクト。

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>パラメーター

*pstrServer*<br/>
Gopher サーバー名を含む文字列へのポインター。

*pstrUserName*<br/>
ユーザー名を含む文字列へのポインター。

*pstrPassword*<br/>
アクセスのパスワードを含む文字列へのポインター。

*ポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

### <a name="return-value"></a>戻り値

ポインターを[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)オブジェクト。 呼び出しに失敗した場合は、スローされたエラーの原因を特定[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

`GetGopherConnection` gopher サーバーに接続し、作成してへのポインターを返します、`CGopherConnection`オブジェクト。 サーバー上の特定の操作を行うことはできません。 読み取りまたは書き込みする場合は、たとえば、別の手順としてこれらの操作を実行する必要があります。 クラスを参照してください。 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)、 [CGopherFile](../../mfc/reference/cgopherfile-class.md)、および[CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)ファイルの検索方法の詳細については、開く、ファイルの読み取りやファイルへの書き込み。 FTP サイトの参照については、メンバー関数を参照してください。 [OpenURL](#openurl)します。 記事をご覧ください[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)gopher 接続の一般的なタスクを実行する手順について。

## <a name="gethttpconnection"></a>  代わりに

HTTP 接続を確立し、ポインターを取得するには、このメンバー関数を呼び出して、`CHttpConnection`オブジェクト。

```cpp
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);

CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);
```

### <a name="parameters"></a>パラメーター

*pstrServer*<br/>
HTTP サーバー名を含む文字列へのポインター。

*ポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

*pstrUserName*<br/>
ユーザー名を含む文字列へのポインター。

*pstrPassword*<br/>
アクセスのパスワードを含む文字列へのポインター。

*dwflags*<br/>
任意の組み合わせ、`INTERNET_FLAG_*`フラグ。 表を参照して、**解説**の[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)の説明については*dwFlags*値。

### <a name="return-value"></a>戻り値

ポインターを[CHttpConnection](../../mfc/reference/chttpconnection-class.md)オブジェクト。 呼び出しに失敗した場合は、スローされたエラーの原因を特定[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

`GetHttpConnection` HTTP サーバーに接続して作成してへのポインターを返します、`CHttpConnection`オブジェクト。 サーバー上の特定の操作を行うことはできません。 HTTP ヘッダーを照会する場合は、たとえば、別のステップとしてこの操作を実行する必要があります。 クラスを参照してください。 [CHttpConnection](../../mfc/reference/chttpconnection-class.md)と[CHttpFile](../../mfc/reference/chttpfile-class.md)操作については、HTTP サーバーへの接続を使用して行うことができます。 HTTP サイトをブラウズする方法の詳細については、メンバー関数を参照してください。 [OpenURL](#openurl)します。 記事をご覧ください[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)HTTP 接続の一般的なタスクを実行する手順について。

## <a name="onstatuscallback"></a>  代入できます。

このメンバー関数は、ステータス コールバックが有効にし、操作が保留中の状態を更新するためにフレームワークによって呼び出されます。

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>パラメーター

*独自*<br/>
アプリケーションによって提供されるコンテキストの値です。

*dwInternetStatus*<br/>
コールバックが行われている理由を示す状態コード。 参照してください**解説**使用可能な値の一覧についてはします。

*lpvStatusInformation*<br/>
このコールバックに関連する情報を格納するバッファーへのポインター。

*dwStatusInformationLength*<br/>
サイズ*lpvStatusInformation*します。

### <a name="remarks"></a>Remarks

最初に呼び出す必要がある[使用](#enablestatuscallback)ステータス コールバックを活用するためにします。

*DwInternetStatus*パラメーターは、実行中の操作を示すし、の内容を決定します*lpvStatusInformation*になります。 *dwStatusInformationLength*に含まれるデータの長さを示す*lpvStatusInformation*します。 次の状態の値を*dwInternetStatus*次のように定義されます。

|[値]|説明|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|含まれる名の IP アドレスを調べる*lpvStatusInformation*します。|
|INTERNET_STATUS_NAME_RESOLVED|含まれる名の IP アドレスを正常に見つかった*lpvStatusInformation*します。|
|INTERNET_STATUS_CONNECTING_TO_SERVER|ソケット アドレスへの接続 ([SOCKADDR](/windows/desktop/winsock/sockaddr-2)) によって示される*lpvStatusInformation*します。|
|INTERNET_STATUS_CONNECTED_TO_SERVER|によって示されるソケット アドレス (SOCKADDR) に正常に接続されている*lpvStatusInformation*します。|
|INTERNET_STATUS_SENDING_REQUEST|サーバーに要求を送信します。 *LpvStatusInformation*パラメーターが NULL です。|
|INTERNET_STATUS_ REQUEST_SENT|サーバーに情報の要求が正常に送信します。 *LpvStatusInformation*パラメーターが NULL です。|
|INTERNET_STATUS_RECEIVING_RESPONSE|サーバー要求に応答を待機しています。 *LpvStatusInformation*パラメーターが NULL です。|
|INTERNET_STATUS_RESPONSE_RECEIVED|サーバーから応答を受信しました。 *LpvStatusInformation*パラメーターが NULL です。|
|INTERNET_STATUS_CLOSING_CONNECTION|サーバーへの接続を終了しています。 *LpvStatusInformation*パラメーターが NULL です。|
|INTERNET_STATUS_CONNECTION_CLOSED|サーバーへの接続が正常に閉じられます。 *LpvStatusInformation*パラメーターが NULL です。|
|INTERNET_STATUS_HANDLE_CREATED|Win32 API 関数で使用される[InternetConnect](/windows/desktop/api/wininet/nf-wininet-internetconnecta)を新しいハンドルが作成されたことを示します。 これにより、アプリケーションの呼び出し、Win32 関数[InternetCloseHandle](/windows/desktop/api/wininet/nf-wininet-internetclosehandle)接続の時間がかかりすぎる場合、別のスレッドから。 これらの関数の詳細について Windows SDKfor を参照してください。|
|INTERNET_STATUS_HANDLE_CLOSING|このハンドルの値が正常に終了します。|

ステータス コールバック ルーチンを実行する前に、何らかのアクションを要求するには、このメンバー関数をオーバーライドします。

> [!NOTE]
> ステータス コールバックには、スレッド状態の保護が必要があります。 MFC の共有ライブラリを使用している場合は、オーバーライドの先頭に次の行を追加します。

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

非同期操作の詳細については、記事を参照してください。[インターネットの最初の手順。WinInet](../../mfc/wininet-basics.md)します。

## <a name="openurl"></a>  できます

HTTP サーバーを指定された要求を送信し、MIME 追加 RFC822 を指定するクライアントを許可するには、関数、または、要求と共に送信する HTTP ヘッダーは、このメンバーを呼び出します。

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>パラメーター

*pstrURL*<br/>
読み取りの開始 URL の名前へのポインター。 Url のみファイルで始まる: ftp: gopher: または http: はサポートされています。 場合アサート*pstrURL*は NULL です。

*独自*<br/>
コールバックに返されるハンドルを使用して、アプリケーション定義の値が渡されます。

*dwFlags*<br/>
この接続を処理する方法を記述するフラグ。 参照してください**解説**で有効なフラグの詳細について。 有効なフラグは次のとおりです。

- INTERNET_FLAG_TRANSFER_ASCII 既定値。 ASCII テキストとしてファイルを転送します。

- INTERNET_FLAG_TRANSFER_BINARY は、バイナリ ファイルとしてファイルを転送します。

- INTERNET_FLAG_RELOAD は、ローカルにキャッシュされている場合でも、ネットワークからデータを取得します。

- ローカル、またはすべてのゲートウェイでは、データをキャッシュ INTERNET_FLAG_DONT_CACHE しません。

- INTERNET_FLAG_SECURE このフラグは、HTTP 要求のみに適用されます。 Secure Sockets Layer の割合と、ネットワーク上でセキュリティで保護されたトランザクションを要求します。

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT 可能な場合は、サーバーによって生成された新しい要求を既存の接続を再利用`OpenUrl`接続要求ごとに新しいセッションを作成する代わりにします。

- INTERNET_FLAG_PASSIVE は、FTP サイトに使用されます。 パッシブ FTP を使用します。 併用[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)の`OpenURL`します。

*pstrHeaders*<br/>
HTTP サーバーに送信するヘッダーを含む文字列へのポインター。

*dwHeadersLength*<br/>
追加のヘッダーの文字の長さ。 この場合は-1 L と*pstrHeaders*が NULL 以外の場合、 *pstrHeaders*を 0 にするには、終了し、長さは、計算と見なされます。

### <a name="return-value"></a>戻り値

FTP、GOPHER、HTTP、およびファイルの種類のインターネット サービスのみのファイル ハンドルを返します。 解析が成功した場合は、NULL を返します。

ポインターを`OpenURL`返しますによって異なります*pstrURL*のサービスの種類。 次の表は、可能なポインターを示しています。`OpenURL`返すことができます。

|URL の種類|戻り値|
|--------------|-------------|
|file://|`CStdioFile*`|
|http://|`CHttpFile*`|
|gopher://|`CGopherFile*`|
|ftp://|`CInternetFile*`|

### <a name="remarks"></a>Remarks

パラメーター *dwFlags* INTERNET_FLAG_TRANSFER_ASCII または INTERNET_FLAG_TRANSFER_BINARY の両方ではなくいずれかに含める必要があります。 その他のフラグをビットごとに結合できます**または**演算子 ( **&#124;**)。

`OpenURL`、Win32 関数をラップする`InternetOpenURL`、唯一のダウンロード、取得、およびインターネット サーバーからのデータの読み取りを許可します。 `OpenURL` 必要のないように、リモートの場所でのファイル操作できることはありません[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)オブジェクト。

特定の接続を使用する (つまり、プロトコル固有) 関数、ファイルへの書き込みなどする必要がありますセッションを開く特定の種類の接続を開くを選択し、目的のモードでファイルを開くには、その接続を使用します。 参照してください`CInternetConnection`接続固有の関数の詳細について。

## <a name="operator_hinternet"></a>  CInternetSession::operator HINTERNET

この演算子を使用して、現在のインターネット セッションの Windows ハンドルを取得します。

```cpp
operator HINTERNET() const;
```

## <a name="setcookie"></a>  CInternetSession::SetCookie

指定された URL の cookie を設定します。

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>パラメーター

*pstrUrl*<br/>
Cookie を設定する URL を指定する null で終わる文字列へのポインター。

*pstrCookieName*<br/>
Cookie の名前を含む文字列へのポインター。

*pstrCookieData*<br/>
URL に関連付けるを実際の文字列データを含む文字列へのポインター。

### <a name="return-value"></a>戻り値

それ以外の場合、成功した場合、TRUE または FALSE を返します。 特定のエラー コードを取得します。 `GetLastError.`

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[InternetSetCookie](/windows/desktop/api/wininet/nf-wininet-internetsetcookiea)」の説明に従って、Windows SDK。

## <a name="setoption"></a>  CInternetSession::SetOption

インターネット セッションのオプションを設定するには、このメンバー関数を呼び出します。

```cpp
BOOL SetOption(
    DWORD dwOption,
    LPVOID lpBuffer,
    DWORD dwBufferLength,
    DWORD dwFlags = 0);

BOOL SetOption(
    DWORD dwOption,
    DWORD dwValue,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>パラメーター

*dwOption*<br/>
インターネット オプションを設定します。 参照してください[オプション フラグ](/windows/desktop/WinInet/option-flags)Windows SDKfor 使用可能なオプションの一覧にします。

*lpBuffer*<br/>
オプションの設定を格納するバッファー。

*dwBufferLength*<br/>
長さ*lpBuffer*のサイズまたは*dwValue*します。

*dwValue*<br/>
オプションの設定を格納する DWORD です。

*dwFlags*<br/>
さまざまなキャッシュ オプションを示します。 既定値は 0 に設定されます。 使用可能な値は次のとおりです。

- ローカルまたはゲートウェイ サーバーでは、データをキャッシュ INTERNET_FLAG_DONT_CACHE しません。

- INTERNET_FLAG_OFFLINE ダウンロード操作は、により、永続的なキャッシュにのみ満たされます。 項目がキャッシュに存在しない場合は、適切なエラー コードが返されます。 このフラグは、ビットごとに組み合わせることができます**または**( **&#124;**) 演算子。

### <a name="return-value"></a>戻り値

操作が成功した場合は、値 TRUE が返されます。 エラーが発生した場合、値は FALSE が返されます。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)<br/>
[CFtpConnection クラス](../../mfc/reference/cftpconnection-class.md)<br/>
[CGopherConnection クラス](../../mfc/reference/cgopherconnection-class.md)
