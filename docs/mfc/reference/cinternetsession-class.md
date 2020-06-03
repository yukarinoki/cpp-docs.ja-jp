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
ms.openlocfilehash: ddd7ca6676805e6de1b7afb5ebc77733701dfef9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372381"
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
|[次のサービスを実行します。](#cinternetsession)|`CInternetSession` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[インターネットセッション::閉じる](#close)|インターネット セッションが終了すると、インターネット接続を閉じます。|
|[を有効にします。](#enablestatuscallback)|ステータス コールバック ルーチンを確立します。|
|[次のコンテキストを取得します。](#getcontext)|インターネット セッションが終了すると、インターネット接続を閉じます。|
|[インターネットセッション::ゲットクッキー](#getcookie)|指定した URL とそのすべての親 URL の Cookie を返します。|
|[をクリックします。](#getcookielength)|バッファーに格納されている Cookie の長さを指定する変数を取得します。|
|[インターネットセッション::ゲットFtp接続](#getftpconnection)|サーバーとの FTP セッションを開きます。 ユーザーにログオンします。|
|[インターネットセッション::ゲットゴファーコネクション](#getgopherconnection)|接続を開こうとしているアプリケーションの gopher サーバーを開きます。|
|[インターネットセッション::取得Http接続](#gethttpconnection)|接続を開こうとしているアプリケーションの HTTP サーバーを開きます。|
|[を設定します。](#onstatuscallback)|状態のコールバックが有効な場合に、操作の状態を更新します。|
|[インターネットセッション::オープンURL](#openurl)|URL を解析して開きます。|
|[を設定します。](#setcookie)|指定した URL のクッキーを設定します。|
|[インターネットセッション::セットオプション](#setoption)|インターネット セッションのオプションを設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[インターネットセッション::オペレーターHインターネット](#operator_hinternet)|現在のインターネット セッションへのハンドル。|

## <a name="remarks"></a>解説

アプリケーションの存続期間にインターネット接続を維持する必要がある場合は、 `CInternetSession` [CWinApp](../../mfc/reference/cwinapp-class.md)クラスのメンバーを作成できます。

インターネット セッションを確立したら[、OpenURL](#openurl)を呼び出すことができます。 `CInternetSession`次に、グローバル関数[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)を呼び出して URL を解析します。 プロトコルの種類に関係なく`CInternetSession`、URL を解釈して管理します。 URL リソース 「file://」 で識別されるローカルファイルの要求を処理できます。 `OpenURL`渡した名前がローカルファイルの場合は[、CStdioFile](../../mfc/reference/cstdiofile-class.md)オブジェクトへのポインタを返します。

を使用して`OpenURL`インターネット サーバー上の URL を開くと、サイトから情報を読み取ることができます。 サーバー上にあるファイルに対してサービス固有のアクション (HTTP、FTP、gopher など) を実行する場合は、そのサーバーとの適切な接続を確立する必要があります。 特定のサービスに対して特定の種類の接続を直接開くには、次のいずれかのメンバー関数を使用します。

- ゴファー サービスへの接続を開く接続を[取得](#getgopherconnection)します。

- HTTP サービスへの接続を開くには、Http[接続を取得](#gethttpconnection)します。

- FTP サービスへの接続を開くには、Ftp[接続を取得](#getftpconnection)します。

[SetOption](#setoption)を使用すると、タイムアウト値や再試行回数などのセッションのクエリ オプションを設定できます。

`CInternetSession`メンバー関数[SetCookie](#setcookie) [、GetCookie](#getcookie)、および[GetCookieLength](#getcookielength)は、サーバーとスクリプトがクライアント ワークステーションに関する状態情報を保持する Win32 クッキー データベースを管理する手段を提供します。

インターネット プログラミングの基本的な作業の詳細については、「[インターネットの最初の手順 : WinInet](../../mfc/wininet-basics.md)」を参照してください。 MFC WinInet クラスの使用方法の一般的な情報については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

> [!NOTE]
> `CInternetSession`サポートされていないサービスの種類に対して[AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)をスローします。 FTP、HTTP、gopher、およびファイルのサービスタイプのみが現在サポートされています。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cinternetsessioncinternetsession"></a><a name="cinternetsession"></a>次のサービスを実行します。

このメンバー関数は、オブジェクトが`CInternetSession`作成されるときに呼び出されます。

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

*をクリックします。*<br/>
インターネット関数を呼び出しているアプリケーションまたはエンティティの名前を識別する文字列へのポインター (たとえば、"Microsoft インターネット ブラウザー" )。 *pstrAgent*が NULL (既定値) の場合、フレームワークはグローバル関数[AfxGetAppName](application-information-and-management.md#afxgetappname)を呼び出し、アプリケーション名を含む null で終わる文字列を返します。 一部のプロトコルでは、この文字列を使用して、サーバーに対するアプリケーションを識別します。

*dw コンテキスト*<br/>
操作のコンテキスト識別子。 *dwContext*は[、CInternetSession::OnStatusCallback](#onstatuscallback)によって返される操作の状態情報を識別します。 デフォルトは 1 に設定されています。ただし、操作に対して特定のコンテキスト ID を明示的に割り当てることができます。 オブジェクトとオブジェクトが行うすべての作業は、そのコンテキスト ID に関連付けられます。

*アクセスタイプ*<br/>
必要なアクセスの種類。 次の有効な値は、いずれか 1 つだけ指定できます。

- INTERNET_OPEN_TYPE_PRECONFIG レジストリで構成済みの設定を使用して接続します。 このアクセスタイプはデフォルトとして設定されます。 TIS プロキシ経由で接続するには *、dwAccessType*をこの値に設定します。その後、レジストリを適切に設定します。

- INTERNET_OPEN_TYPE_DIRECT インターネットに直接接続します。

- INTERNET_OPEN_TYPE_PROXY CERN プロキシ経由で接続します。

さまざまな種類のプロキシとの接続については、「標準 FTP[クライアント アプリケーションの手順](../../mfc/steps-in-a-typical-ftp-client-application.md)」を参照してください。

*プロキシ名*<br/>
*dwAccessType*がINTERNET_OPEN_TYPE_PROXYとして設定されている場合は、優先 CERN プロキシの名前。 既定値は NULL です。

*プロキシ バイパス*<br/>
オプションのサーバー アドレスの一覧を含む文字列へのポインター。 プロキシ アクセスを使用する場合、これらのアドレスはバイパスされる可能性があります。 NULL 値が指定されている場合、バイパス リストはレジストリから読み取られます。 このパラメーターは *、dwAccessType*が INTERNET_OPEN_TYPE_PROXY に設定されている場合にのみ意味があります。

*dwFlags*<br/>
さまざまなキャッシュ オプションを示します。 デフォルトは 0 に設定されています。 指定できる値は次のとおりです。

- INTERNET_FLAG_DONT_CACHE ローカルまたはゲートウェイ サーバーにデータをキャッシュしません。

- INTERNET_FLAG_OFFLINE ダウンロード操作は、永続キャッシュを介してのみ実行されます。 アイテムがキャッシュに存在しない場合は、適切なエラー コードが返されます。 このフラグは、ビットごとの**OR** ( **&#124;**) 演算子と組み合わせられます。

### <a name="remarks"></a>解説

`CInternetSession`は、アプリケーションによって呼び出される最初のインターネット関数です。 内部データ構造体を初期化し、アプリケーションからの今後の呼び出しに備えます。

インターネット接続を開くことができれば`CInternetSession`[、AfxThrowインターネット例外](internet-url-parsing-globals.md#afxthrowinternetexception)をスローします。

### <a name="example"></a>例

[「CFtp ファイルの検索](../../mfc/reference/cftpfilefind-class.md)」の例を参照してください。

## <a name="cinternetsessionclose"></a><a name="close"></a>インターネットセッション::閉じる

アプリケーションがオブジェクトの使用を終了したら、このメンバー`CInternetSession`関数を呼び出します。

```cpp
virtual void Close();
```

### <a name="example"></a>例

[「CFtp ファイルの検索](../../mfc/reference/cftpfilefind-class.md)」の例を参照してください。

## <a name="cinternetsessionenablestatuscallback"></a><a name="enablestatuscallback"></a>を有効にします。

ステータス コールバックを有効にするには、このメンバー関数を呼び出します。

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
コールバックを有効にするか無効にするかを指定します。 デフォルトは TRUE です。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、スローされた[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトを調べることによって、失敗の原因を特定します。

### <a name="remarks"></a>解説

ステータス コールバックを処理する場合、アプリケーションのステータス バーに、操作の進行状況 (名前の解決、サーバーへの接続など) のステータスを指定できます。 長時間の操作では、操作状況の表示が特に望ましい。

要求の処理中にコールバックが発生するため、アプリケーションは、ネットワークへのデータ スループットの低下を防ぐために、コールバックにできるだけ時間を費やす必要があります。 たとえば、コールバックにダイアログ ボックスを配置すると、サーバーが要求を終了するような時間がかかる場合があります。

いずれかのコールバックが保留中である限り、ステータス コールバックは削除できません。

非同期的に操作を処理するには、独自のスレッドを作成するか、MFC を使用せずに WinInet 関数を使用する必要があります。

## <a name="cinternetsessiongetcontext"></a><a name="getcontext"></a>次のコンテキストを取得します。

特定のアプリケーション セッションのコンテキスト値を取得します。

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>戻り値

アプリケーション定義のコンテキスト識別子。

### <a name="remarks"></a>解説

[OnStatusCallback](#onstatuscallback)は、返されるコンテキスト`GetContext`ID を使用して、特定のアプリケーションの状態を報告します。 たとえば、ステータス情報を返すインターネット要求をユーザーがアクティブにした場合、ステータス コールバックはコンテキスト ID を使用して、特定の要求のステータスを報告します。 ユーザーが、両方ともステータス情報を返す 2 つの個別の`OnStatusCallback`インターネット要求をアクティブにした場合は、コンテキスト識別子を使用して、対応する要求に関する状態を返します。 したがって、コンテキスト識別子はすべてのステータス コールバック操作に使用され、セッションが終了するまでセッションに関連付けられます。

非同期操作の詳細については、「[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)」を参照してください。

## <a name="cinternetsessiongetcookie"></a><a name="getcookie"></a>インターネットセッション::ゲットクッキー

このメンバー関数は、Windows SDK で説明されているように、Win32 関数[の](/windows/win32/api/wininet/nf-wininet-internetgetcookiew)動作を実装します。

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

*をクリックします。*<br/>
URL を含む文字列へのポインター。

*クッキー名*<br/>
指定した URL に対して取得する Cookie の名前を含む文字列へのポインター。

*データ*<br/>
最初のオーバーロードでは、Cookie データを受け取るバッファーのアドレスを含む文字列へのポインター。 この値は NULL にできます。 2 番目のオーバーロードでは、Cookie データを受け取る[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

*ドブビューレン*<br/>
*バッファーの*サイズを指定する変数。 関数が成功すると、バッファーは *、pstrCookieData*バッファーにコピーされたデータの量を受け取ります。 *pstrCookieData*が NULL の場合、このパラメーターは、すべての Cookie データをコピーするために必要なバッファーのサイズを指定する値を受け取ります。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、そうでない場合は FALSE を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)を呼び出してエラーの原因を特定します。 次のエラー値が適用されます。

- ERROR_NO_MORE_ITEMS 指定した URL とそのすべての親に対するクッキーはありません。

- ERROR_INSUFFICIENT_BUFFER *dwBufLen*で渡された値は、すべてのクッキー データをコピーするのに十分ではありません。 *dwBufLen*で返される値は、すべてのデータを取得するために必要なバッファーのサイズです。

### <a name="remarks"></a>解説

2 番目のオーバーロードでは、MFC は、指定された`CString`オブジェクトに Cookie データを取得します。

## <a name="cinternetsessiongetcookielength"></a><a name="getcookielength"></a>をクリックします。

バッファーに格納されている Cookie の長さを取得します。

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
URL を含む文字列へのポインター

*クッキー名*<br/>
Cookie の名前を含む文字列へのポインター。

### <a name="return-value"></a>戻り値

バッファに格納されている Cookie の長さを示す DWORD 値。 *pstrCookieName*で示された名前のクッキーが存在しない場合は 0。

### <a name="remarks"></a>解説

この値は[GetCookie](#getcookie)によって使用されます。

## <a name="cinternetsessiongetftpconnection"></a><a name="getftpconnection"></a>インターネットセッション::ゲットFtp接続

FTP 接続を確立し、オブジェクトへのポインターを取得するには、この`CFtpConnection`メンバー関数を呼び出します。

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
FTP サーバー名を含む文字列へのポインター。

*ユーザー名*<br/>
ログインするユーザーの名前を指定する、NULL で終わる文字列へのポインター。 NULL の場合、デフォルトは匿名です。

*パスワード*<br/>
ログインに使用するパスワードを指定する、null で終わる文字列へのポインター。 *pstrPassword*と*pstrUserName*の両方が NULL の場合、既定の匿名パスワードはユーザーの電子メール名です。 *pstrPassword*が NULL (または空の文字列) で *、pstrUserName*が NULL でない場合は、空白のパスワードが使用されます。 次の表は、4 つの設定の*pstrUserName*と*pstrPassword*の動作を示しています。

| *ユーザー名*  | *パスワード*  | FTP サーバーに送信されたユーザー名 | FTP サーバーに送信されるパスワード |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   NULL または " "   |   NULL または " "   |         「匿名」         |      ユーザーの電子メール名      |
| NULL 以外の文字列 |   NULL または " "   |       *ユーザー名*        |             " "             |
|      NULL       | NULL 以外の文字列 |            ERROR            |            ERROR            |
| NULL 以外の文字列 | NULL 以外の文字列 |       *ユーザー名*        |       *パスワード*        |

*nポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

*bパッシブ*<br/>
この FTP セッションのパッシブ モードまたはアクティブ モードを指定します。 TRUE に設定すると、Win32 API`dwFlag`がINTERNET_FLAG_PASSIVEに設定されます。

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/cftpconnection-class.md)へのポインター。 呼び出しが失敗した場合は、スローされた[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトを調べることによって、失敗の原因を特定します。

### <a name="remarks"></a>解説

`GetFtpConnection`は、FTP サーバーに接続し、`CFTPConnection`オブジェクトへのポインターを作成して返します。 サーバー上で特定の操作を実行しません。 たとえば、ファイルの読み取りまたは書き込みを行う場合は、これらの操作を別の手順として実行する必要があります。 ファイルの検索、ファイルのオープン、ファイルの読み取りまたは書き込みの詳細については[、CFtpConnection](../../mfc/reference/cftpconnection-class.md)クラスと[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)を参照してください。 一般的な FTP 接続タスクの実行手順については[、WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)の記事を参照してください。

### <a name="example"></a>例

[「CFtp ファイルの検索](../../mfc/reference/cftpfilefind-class.md)」の例を参照してください。

## <a name="cinternetsessiongetgopherconnection"></a><a name="getgopherconnection"></a>インターネットセッション::ゲットゴファーコネクション

新しい gopher 接続を確立し、オブジェクトへのポインターを取得するには`CGopherConnection`、このメンバー関数を呼び出します。

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
gopher サーバー名を含む文字列へのポインター。

*ユーザー名*<br/>
ユーザー名を含む文字列へのポインター。

*パスワード*<br/>
アクセス パスワードを含む文字列へのポインター。

*nポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/cgopherconnection-class.md)へのポインター。 呼び出しが失敗した場合は、スローされた[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトを調べることによって、失敗の原因を特定します。

### <a name="remarks"></a>解説

`GetGopherConnection`が gopher サーバーに接続し、`CGopherConnection`オブジェクトへのポインターを作成して返します。 サーバー上で特定の操作を実行しません。 たとえば、データの読み取りまたは書き込みを行う場合は、これらの操作を別の手順として実行する必要があります。 ファイルの検索、ファイルのオープン、ファイルの読み取りまたは書き込みの詳細については[、CGopherConnection](../../mfc/reference/cgopherconnection-class.md)クラス[、CGopherFile](../../mfc/reference/cgopherfile-class.md)、および[CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)を参照してください。 FTP サイトの参照については、メンバー関数[OpenURL](#openurl)を参照してください。 一般的な gopher 接続タスクの実行手順については[、WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)の記事を参照してください。

## <a name="cinternetsessiongethttpconnection"></a><a name="gethttpconnection"></a>インターネットセッション::取得Http接続

HTTP 接続を確立し、オブジェクトへのポインターを取得するには、この`CHttpConnection`メンバー関数を呼び出します。

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

*を行う*<br/>
HTTP サーバー名を含む文字列へのポインター。

*nポート*<br/>
サーバーで使用する TCP/IP ポートを識別する番号。

*ユーザー名*<br/>
ユーザー名を含む文字列へのポインター。

*パスワード*<br/>
アクセス パスワードを含む文字列へのポインター。

*Dwflags*<br/>
フラグの`INTERNET_FLAG_*`任意の組み合わせ。 *dwFlags*値の説明については[、CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)の**解説**セクションの表を参照してください。

### <a name="return-value"></a>戻り値

[オブジェクトへの](../../mfc/reference/chttpconnection-class.md)ポインター。 呼び出しが失敗した場合は、スローされた[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトを調べることによって、失敗の原因を特定します。

### <a name="remarks"></a>解説

`GetHttpConnection`は HTTP サーバーに接続し、`CHttpConnection`オブジェクトへのポインタを作成して返します。 サーバー上で特定の操作を実行しません。 たとえば、HTTP ヘッダーを照会する場合は、この操作を別の手順として実行する必要があります。 HTTP サーバーへの接続を使用して実行できる操作については、[クラス CHttpConnection](../../mfc/reference/chttpconnection-class.md)および[CHttpFile](../../mfc/reference/chttpfile-class.md)を参照してください。 HTTP サイトの参照については、メンバー関数[OpenURL](#openurl)を参照してください。 一般的な HTTP 接続タスクの実行手順については[、記事「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="cinternetsessiononstatuscallback"></a><a name="onstatuscallback"></a>を設定します。

このメンバー関数は、ステータス コールバックが有効で、操作が保留されているときに、状態を更新するためにフレームワークによって呼び出されます。

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>パラメーター

*dw コンテキスト*<br/>
アプリケーションによって提供されるコンテキスト値。

*ステータス*<br/>
コールバックが行われる理由を示すステータスコード。 使用可能な値の表については **、「解説」** を参照してください。

*情報*<br/>
このコールバックに関連する情報を格納しているバッファーへのポインター。

*長さ*<br/>
*のサイズです*。

### <a name="remarks"></a>解説

状態のコールバックを利用するには、まず[EnableStatusCallback](#enablestatuscallback)を呼び出す必要があります。

*dwInternetStatus*パラメーターは、実行される操作を示し *、lpvStatus 情報*の内容を決定します。 *に*含まれるデータの長さを*示します。* *dwInternetStatus*の以下の状況値は、次のように定義されます。

|[値]|意味|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|に含まれる名前の IP アドレス*を検索します*。|
|INTERNET_STATUS_NAME_RESOLVED|*lpvStatusInformation*に含まれる名前の IP アドレスが正常に見つかりました。|
|INTERNET_STATUS_CONNECTING_TO_SERVER|*lpvStatusInformation*が指すソケット アドレス ([SOCKADDR](/windows/win32/winsock/sockaddr-2)) に接続しています。|
|INTERNET_STATUS_CONNECTED_TO_SERVER|*lpvStatusInformation*が指すソケット アドレス (SOCKADDR) に正常に接続されました。|
|INTERNET_STATUS_SENDING_REQUEST|サーバーに情報要求を送信します。 パラメーター*は*NULL です。|
|INTERNET_STATUS_REQUEST_SENT|サーバーに情報要求を送信しました。 パラメーター*は*NULL です。|
|INTERNET_STATUS_RECEIVING_RESPONSE|サーバーが要求に応答するのを待機しています。 パラメーター*は*NULL です。|
|INTERNET_STATUS_RESPONSE_RECEIVED|サーバーからの応答を正常に受信しました。 パラメーター*は*NULL です。|
|INTERNET_STATUS_CLOSING_CONNECTION|サーバーへの接続を閉じます。 パラメーター*は*NULL です。|
|INTERNET_STATUS_CONNECTION_CLOSED|サーバーへの接続を正常に閉じました。 パラメーター*は*NULL です。|
|INTERNET_STATUS_HANDLE_CREATED|Win32 API 関数[InternetConnect](/windows/win32/api/wininet/nf-wininet-internetconnectw)で使用され、新しいハンドルが作成されたことを示します。 これにより、アプリケーションは、接続に時間がかかりすぎる場合に、別のスレッドから Win32 関数[InternetCloseHandle](/windows/win32/api/wininet/nf-wininet-internetclosehandle)を呼び出すことができます。 これらの関数の詳細については、Windows SDK を参照してください。|
|INTERNET_STATUS_HANDLE_CLOSING|このハンドル値を正常に終了しました。|

ステータス コールバック ルーチンを実行する前に何らかのアクションを必要とするように、このメンバー関数をオーバーライドします。

> [!NOTE]
> 状態のコールバックにはスレッド状態の保護が必要です。 共有ライブラリで MFC を使用している場合は、オーバーライドの先頭に次の行を追加します。

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

非同期操作の詳細については、「[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)」を参照してください。

## <a name="cinternetsessionopenurl"></a><a name="openurl"></a>インターネットセッション::オープンURL

指定した要求を HTTP サーバーに送信し、クライアントが要求と共に送信する追加の RFC822、MIME、または HTTP ヘッダーを指定できるようにする場合は、このメンバー関数を呼び出します。

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
読み取りを開始する URL の名前へのポインター。 ファイルで始まる URL のみ:、ftp:、gopher:、または http: がサポートされています。 *pstrURL*が NULL の場合にアサートします。

*dw コンテキスト*<br/>
コールバックで返されたハンドルで渡されるアプリケーション定義の値。

*dwFlags*<br/>
この接続の処理方法を説明するフラグ。 有効なフラグの詳細については **、「解説」** を参照してください。 有効なフラグは次のとおりです。

- INTERNET_FLAG_TRANSFER_ASCII 既定値。 ファイルを ASCII テキストとして転送します。

- INTERNET_FLAG_TRANSFER_BINARY ファイルをバイナリ ファイルとして転送します。

- INTERNET_FLAG_RELOAD ローカルにキャッシュされている場合でも、ワイヤからデータを取得します。

- INTERNET_FLAG_DONT_CACHE ローカルまたはゲートウェイにデータをキャッシュしません。

- INTERNET_FLAG_SECURE このフラグは HTTP 要求にのみ適用されます。 セキュア ソケット レイヤまたは PCT を使用して、ネットワーク上のセキュア なトランザクションを要求します。

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT 可能であれば、接続要求ごとに新しいセッションを作成するのではなく、サーバーへの`OpenUrl`既存の接続を再利用して、新しい要求を生成します。

- INTERNET_FLAG_PASSIVE FTP サイトに使用されます。 パッシブ FTP セマンティクスを使用します。 [のインターネット接続](../../mfc/reference/cinternetconnection-class.md)で使用`OpenURL`されます。

*ヘッダー*<br/>
HTTP サーバーに送信されるヘッダーを含む文字列へのポインター。

*長さを持つ*<br/>
追加ヘッダーの長さ (文字数)。 これが -1L で *、pstrHeader が*NULL 以外の場合 *、pstrHeaders*はゼロで終了したものと見なされ、長さが計算されます。

### <a name="return-value"></a>戻り値

FTP、GOPHER、HTTP、および FILE タイプのインターネット サービスのみのファイル ハンドルを返します。 解析が失敗した場合は NULL を返します。

返される`OpenURL`ポインターは *、pstrURL*のサービスの種類によって異なります。 次の表は、返すことができるポインタを`OpenURL`示しています。

|URL タイプ|戻り値|
|--------------|-------------|
|`file://`|`CStdioFile*`|
|`http://`|`CHttpFile*`|
|`gopher://`|`CGopherFile*`|
|`ftp://`|`CInternetFile*`|

### <a name="remarks"></a>解説

パラメーター *dwFlags*には、INTERNET_FLAG_TRANSFER_ASCIIまたはINTERNET_FLAG_TRANSFER_BINARYのどちらかを含める必要がありますが、両方を含める必要があります。 残りのフラグはビットごとの**OR**演算子 ( **&#124;**) と組み合わせることができます。

`OpenURL`Win32 関数`InternetOpenURL`をラップするは、インターネット サーバーからのデータのダウンロード、取得、および読み取りのみが許可されます。 `OpenURL`リモートの場所でのファイル操作は許可されません。 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

接続固有の (つまり、プロトコル固有の) 機能 (ファイルへの書き込みなど) を使用するには、セッションを開いて特定の種類の接続を開き、その接続を使用して目的のモードでファイルを開く必要があります。 接続`CInternetConnection`固有の機能の詳細については、「」を参照してください。

## <a name="cinternetsessionoperator-hinternet"></a><a name="operator_hinternet"></a>インターネットセッション::オペレーターHインターネット

この演算子を使用して、現在のインターネット セッションの Windows ハンドルを取得します。

```cpp
operator HINTERNET() const;
```

## <a name="cinternetsessionsetcookie"></a><a name="setcookie"></a>を設定します。

指定した URL のクッキーを設定します。

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
Cookie を設定する URL を指定する、null で終わる文字列へのポインター。

*クッキー名*<br/>
Cookie の名前を含む文字列へのポインター。

*データ*<br/>
URL に関連付ける実際の文字列データを含む文字列へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、そうでない場合は FALSE を返します。 特定のエラー コードを取得するには、`GetLastError.`

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[の動作](/windows/win32/api/wininet/nf-wininet-internetsetcookiew)を実装します。

## <a name="cinternetsessionsetoption"></a><a name="setoption"></a>インターネットセッション::セットオプション

インターネット セッションのオプションを設定します。

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

*dw オプション*<br/>
設定するインターネット オプション。 使用可能なオプションの一覧については、Windows SDK のオプション[フラグ](/windows/win32/WinInet/option-flags)を参照してください。

*バッファバッファ*<br/>
オプション設定を含むバッファー。

*長さ*<br/>
*の*長さまたは*dwValue*のサイズ。

*値*<br/>
オプション設定を含む DWORD。

*dwFlags*<br/>
さまざまなキャッシュ オプションを示します。 デフォルトは 0 に設定されています。 指定できる値は次のとおりです。

- INTERNET_FLAG_DONT_CACHE ローカルまたはゲートウェイ サーバーにデータをキャッシュしません。

- INTERNET_FLAG_OFFLINE ダウンロード操作は、永続キャッシュを介してのみ実行されます。 アイテムがキャッシュに存在しない場合は、適切なエラー コードが返されます。 このフラグは、ビットごとの**OR** ( **&#124;**) 演算子と組み合わせられます。

### <a name="return-value"></a>戻り値

操作が成功した場合は、TRUE の値が返されます。 エラーが発生した場合は、値 FALSE が返されます。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)<br/>
[クラス](../../mfc/reference/cftpconnection-class.md)<br/>
[CGopherConnection クラス](../../mfc/reference/cgopherconnection-class.md)
