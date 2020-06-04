---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
helpviewer_keywords:
- CHttpFile [MFC], CHttpFile
- CHttpFile [MFC], AddRequestHeaders
- CHttpFile [MFC], EndRequest
- CHttpFile [MFC], GetFileURL
- CHttpFile [MFC], GetObject
- CHttpFile [MFC], GetVerb
- CHttpFile [MFC], QueryInfo
- CHttpFile [MFC], QueryInfoStatusCode
- CHttpFile [MFC], SendRequest
- CHttpFile [MFC], SendRequestEx
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
ms.openlocfilehash: cba3ba7d86577703de2bf5709d66bbd5e0298863
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368389"
---
# <a name="chttpfile-class"></a>クラス

HTTP サーバー上のファイルを要求し、読み込む機能が用意されています。

## <a name="syntax"></a>構文

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイル::CHttpファイル](#chttpfile)|`CHttpFile` オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次のファイル:要求ヘッダーを追加します。](#addrequestheaders)|HTTP サーバーに送信される要求にヘッダーを追加します。|
|[要求を終了します。](#endrequest)|[メンバー](#sendrequestex)関数を使用して HTTP サーバーに送信された要求を終了します。|
|[ファイルを取得します。](#getfileurl)|指定したファイルの URL を取得します。|
|[ファイルを取得します。](#getobject)|HTTP サーバーへの要求内の動詞のターゲット オブジェクトを取得します。|
|[ファイルを取得します。](#getverb)|HTTP サーバーへの要求で使用された動詞を取得します。|
|[次のクエリ情報](#queryinfo)|HTTP サーバーから応答ヘッダーまたは要求ヘッダーを返します。|
|[を指定します。](#queryinfostatuscode)|HTTP 要求に関連付けられている状態コードを取得し、指定された`dwStatusCode`パラメーターに配置します。|
|[次のファイル::送信要求](#sendrequest)|HTTP サーバーに要求を送信します。|
|[ファイル::要求の呼び出し](#sendrequestex)|の Write メソッドまたは`CInternetFile`[WriteString](../../mfc/reference/cinternetfile-class.md#write)メソッド[WriteString](../../mfc/reference/cinternetfile-class.md#writestring)を使用して、HTTP サーバーに要求を送信します。|

## <a name="remarks"></a>解説

インターネット セッションが HTTP サーバーからデータを読み取る場合は`CHttpFile`、 のインスタンスを作成する必要があります。

他の MFC`CHttpFile`インターネット クラスとの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="chttpfileaddrequestheaders"></a><a name="addrequestheaders"></a>次のファイル:要求ヘッダーを追加します。

HTTP 要求ハンドルに 1 つ以上の HTTP 要求ヘッダーを追加します。

```
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,
    int dwHeadersLen = -1);

BOOL AddRequestHeaders(
    CString& str,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```

### <a name="parameters"></a>パラメーター

*ヘッダー*<br/>
要求に追加するヘッダーを含む文字列へのポインター。 各ヘッダーは CR/LF ペアで終了する必要があります。

*dwFlags*<br/>
新しいヘッダーのセマンティクスを変更します。 以下のいずれかを指定できます。

- HTTP_ADDREQ_FLAG_COALESCE同じ名前のヘッダーをマージし、フラグを使用して、見つかった最初のヘッダーを後続のヘッダーに追加します。 たとえば、"Accept: text/\*" に続いて "Accept: audio/\*" というヘッダーが作成され、\*単一の\*ヘッダー "Accept: text/ ,audio/ " という結果が得られます。 結合されたヘッダーまたは個別のヘッダーで送信された要求によって受信されたデータに関して、まとまりのあるスキームを確保するのは、呼び出し元のアプリケーション次第です。

- HTTP_ADDREQ_FLAG_REPLACE 現在のヘッダーを置き換えるために削除と追加を実行します。 ヘッダー名は現在のヘッダーを削除するために使用され、完全な値は新しいヘッダーを追加するために使用されます。 ヘッダー値が空で、ヘッダーが見つかった場合は、それが削除されます。 空でない場合は、ヘッダー値が置き換えられます。

- HTTP_ADDREQ_FLAG_ADD_IF_NEW ヘッダーが存在しない場合にのみ追加されます。 存在する場合は、エラーが返されます。

- HTTP_ADDREQ_FLAG_ADD REPLACE と共に使用されます。 ヘッダーが存在しない場合は、ヘッダーを追加します。

*ドウヘッダーレン*<br/>
*pstrHeader*の長さ (文字) です。 これが -1L の場合 *、pstrHeaders*はゼロ終端であると見なされ、長さが計算されます。

*Str*<br/>
追加する要求ヘッダーを含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

`AddRequestHeaders`は、HTTP 要求ハンドルにフリーフォーマットのヘッダーを追加します。 HTTP サーバーに送信される要求を詳細に制御する必要がある高度なクライアントが使用することを目的としています。

> [!NOTE]
> アプリケーションは、HTTP_ADDREQ_FLAG_ADDまたはHTTP_ADDREQ_FLAG_ADD_IF_NEWを使用して、呼び出*str*しの`AddRequestHeaders`*pstrHeaders*または str で複数のヘッダーを渡すことができます。 アプリケーションがHTTP_ADDREQ_FLAG_REMOVEまたはHTTP_ADDREQ_FLAG_REPLACEを使用してヘッダーを削除または置換しようとすると *、lpszHeaders*に指定できるヘッダーは 1 つだけです。

## <a name="chttpfilechttpfile"></a><a name="chttpfile"></a>ファイル::CHttpファイル

このメンバー関数は、`CHttpFile`オブジェクトを構築するために呼び出されます。

```
CHttpFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrObject,
    LPCTSTR pstrServer,
    LPCTSTR pstrVerb,
    DWORD_PTR dwContext);

CHttpFile(
    HINTERNET hFile,
    LPCTSTR pstrVerb,
    LPCTSTR pstrObject,
    CHttpConnection* pConnection);
```

### <a name="parameters"></a>パラメーター

*hファイル*<br/>
インターネット ファイルへのハンドル。

*hセッション*<br/>
インターネット セッションへのハンドル。

*オブジェクト*<br/>
`CHttpFile`オブジェクトを含む文字列へのポインター。

*を行う*<br/>
サーバーの名前を含む文字列へのポインター。

*をクリックします。*<br/>
要求の送信時に使用されるメソッドを含む文字列へのポインター。 ポスト、ヘッド、または取得できます。

*dw コンテキスト*<br/>
`CHttpFile`オブジェクトのコンテキスト識別子。 このパラメータの詳細については **、「解説」** を参照してください。

*pConnection*<br/>
[オブジェクトへの](../../mfc/reference/chttpconnection-class.md)ポインター。

### <a name="remarks"></a>解説

オブジェクトを`CHttpFile`直接構築することは決してありません。代わりに[、C インターネットセッション::オープンURL](../../mfc/reference/cinternetsession-class.md#openurl)または[CHttp 接続::オープンリクエストを](../../mfc/reference/chttpconnection-class.md#openrequest)呼び出します。

既定値は`dwContext`、オブジェクトを作成した`CHttpFile` [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトから MFC によってオブジェクトに`CHttpFile`送信されます。 オブジェクトを呼`CInternetSession::OpenURL`び`CHttpConnection`出したり、`CHttpFile`オブジェクトを構築するときに、デフォルトをオーバーライドして、コンテキスト識別子を選択した値に設定できます。 コンテキスト識別子は、識別されるオブジェクトのステータスを提供するために[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="chttpfileendrequest"></a><a name="endrequest"></a>要求を終了します。

このメンバー関数を呼び出して、HTTP サーバーに送信された要求を[、メンバー](#sendrequestex)関数で終了します。

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
操作を説明するフラグ。 適切なフラグの一覧については、Windows SDK の[「HttpEndRequest」](/windows/win32/api/wininet/nf-wininet-httpendrequestw)を参照してください。

*lpBuffIn*<br/>
操作に使用される入力バッファーを記述する、初期化された[INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw)へのポインター。

*dw コンテキスト*<br/>
`CHttpFile` 操作のコンテキスト識別子。 このパラメータの詳細については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、スローされた[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトを調べることによって、失敗の原因を特定します。

### <a name="remarks"></a>解説

*dwContext*の既定値は、オブジェクトを作成した`CHttpFile` [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトからオブジェクトに MFC`CHttpFile`によって送信されます。 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)または[CHttpConnection](../../mfc/reference/chttpconnection-class.md)を呼び`CHttpFile`出してオブジェクトを構築する場合、デフォルトをオーバーライドしてコンテキスト識別子を選択した値に設定できます。 コンテキスト識別子は、識別されるオブジェクトのステータスを提供するために[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

## <a name="chttpfilegetfileurl"></a><a name="getfileurl"></a>ファイルを取得します。

HTTP ファイルの名前を URL として取得します。

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>戻り値

このファイルに関連付けられているリソースを参照する URL を含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は[、SendRequest](#sendrequest)への呼び出しが成功`CHttpFile`した後、または[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用します。

## <a name="chttpfilegetobject"></a><a name="getobject"></a>ファイルを取得します。

このメンバー関数を呼び出して、この`CHttpFile`オブジェクトに関連付けられたオブジェクトの名前を取得します。

```
CString GetObject() const;
```

### <a name="return-value"></a>戻り値

オブジェクトの名前を含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は[、SendRequest](#sendrequest)への呼び出しが成功`CHttpFile`した後、または[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用します。

## <a name="chttpfilegetverb"></a><a name="getverb"></a>ファイルを取得します。

このメンバー関数を呼び出して、この`CHttpFile`に関連付けられた HTTP 動詞 (またはメソッド) を取得します。

```
CString GetVerb() const;
```

### <a name="return-value"></a>戻り値

HTTP 動詞 (またはメソッド) の名前を含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は[、SendRequest](#sendrequest)への呼び出しが成功`CHttpFile`した後、または[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用します。

## <a name="chttpfilequeryinfo"></a><a name="queryinfo"></a>次のクエリ情報

HTTP 要求から応答ヘッダーまたは要求ヘッダーを返します。

```
BOOL QueryInfo(
    DWORD dwInfoLevel,
    LPVOID lpvBuffer,
    LPDWORD lpdwBufferLength,
    LPDWORD lpdwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    CString& str,
    LPDWORD dwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    SYSTEMTIME* pSysTime,
    LPDWORD dwIndex = NULL) const;
```

### <a name="parameters"></a>パラメーター

*を選択します。*<br/>
照会する属性と、要求された情報のタイプを指定する以下のフラグの組み合わせ。

- HTTP_QUERY_CUSTOM ヘッダー名を検索し、出力時にこの値を*lpvBuffer*で返します。 HTTP_QUERY_CUSTOMは、ヘッダーが見つからない場合にアサーションをスローします。

- HTTP_QUERY_FLAG_REQUEST_HEADERS通常、アプリケーションは応答ヘッダーを照会しますが、アプリケーションはこのフラグを使用して要求ヘッダーを照会することもできます。

- HTTP_QUERY_FLAG_SYSTEMTIME値が日付/時刻文字列であるヘッダー ("Last-Modified-Time" など) の場合、このフラグは、アプリケーションがデータを解析する必要がない標準の Win32 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体としてヘッダー値を返します。 このフラグを使用する場合は、関数のオーバーライドを`SYSTEMTIME`使用できます。

- HTTP_QUERY_FLAG_NUMBER値が数値であるヘッダー (ステータス コードなど) の場合、このフラグはデータを 32 ビットの数値として返します。

使用可能な値のリストについては **、「解説**」を参照してください。

*バッファ*<br/>
情報を受け取るバッファーへのポインター。

*バッファ長*<br/>
エントリ時に、これはデータ バッファの長さを文字数またはバイト数で示す値を指します。 このパラメータの詳細については **、「解説」** を参照してください。

*インデックスを指定します。*<br/>
0 から始まるヘッダー インデックスへのポインター。 NULL にすることができます。 このフラグは、同じ名前の複数のヘッダーを列挙するために使用します。 入力時に *、lpdwIndex*は返す指定されたヘッダーのインデックスを示します。 出力時に *、lpdwIndex*は次のヘッダーのインデックスを示します。 次のインデックスが見つからない場合は、ERROR_HTTP_HEADER_NOT_FOUNDが返されます。

*Str*<br/>
返された情報を受け取る[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

*インデックス*<br/>
インデックス値。 *lpdw インデックス*を参照してください。

*時間*<br/>
Win32[システムタイム](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

このメンバー関数は[、SendRequest](#sendrequest)への呼び出しが成功`CHttpFile`した後、または[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用します。

から`QueryInfo`次の種類のデータを取得できます。

- 文字列 (既定)

- `SYSTEMTIME`(「データ:」「有効期限:」など、ヘッダーの場合)

- DWORD(STATUS_CODE、CONTENT_LENGTHなど)

文字列がバッファーに書き込まれ、メンバー関数が成功すると、`lpdwBufferLength`末尾の NULL 文字の文字列の長さが 1 から 1 を引いた文字列が格納されます。

指定できる*dwInfoLevel*値には、次のものがあります。

- HTTP_QUERY_MIME_VERSION

- HTTP_QUERY_CONTENT_TYPE

- HTTP_QUERY_CONTENT_TRANSFER_ENCODING

- HTTP_QUERY_CONTENT_ID

- HTTP_QUERY_CONTENT_DESCRIPTION

- HTTP_QUERY_CONTENT_LENGTH

- HTTP_QUERY_ALLOWED_METHODS

- HTTP_QUERY_PUBLIC_METHODS

- HTTP_QUERY_DATE

- HTTP_QUERY_EXPIRES

- HTTP_QUERY_LAST_MODIFIED

- HTTP_QUERY_MESSAGE_ID

- HTTP_QUERY_URI

- HTTP_QUERY_DERIVED_FROM

- HTTP_QUERY_LANGUAGE

- HTTP_QUERY_COST

- HTTP_QUERY_WWW_LINK

- HTTP_QUERY_PRAGMA

- HTTP_QUERY_VERSION

- HTTP_QUERY_STATUS_CODE

- HTTP_QUERY_STATUS_TEXT

- HTTP_QUERY_RAW_HEADERS

- HTTP_QUERY_RAW_HEADERS_CRLF

## <a name="chttpfilequeryinfostatuscode"></a><a name="queryinfostatuscode"></a>を指定します。

HTTP 要求に関連付けられている状態コードを取得し、指定された*dwStatusCode*パラメーターに配置します。

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
ステータス コードへの参照。 ステータス コードは、要求されたイベントの成功または失敗を示します。 ステータス コードの説明については **、「解説」** を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

このメンバー関数は[、SendRequest](#sendrequest)への呼び出しが成功`CHttpFile`した後、または[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用します。

HTTP ステータス コードは、要求の成功または失敗を示すグループに分類されます。 次の表に、ステータス コード グループと最も一般的な HTTP ステータス コードの概要を示します。

|グループ|意味|
|-----------|-------------|
|200 から 299|Success|
|300 から 399|Information|
|400-499|要求エラー|
|500-599|サーバー エラー|

一般的な HTTP ステータス コード:

|status code|意味|
|-----------------|-------------|
|200|URL が見つかり、送信は以下の通りです|
|400|理解できない要求|
|404|要求された URL が見つかりません|
|405|サーバーは要求されたメソッドをサポートしていません|
|500|不明なサーバー エラー|
|503|サーバーの容量に達しました|

## <a name="chttpfilesendrequest"></a><a name="sendrequest"></a>次のファイル::送信要求

HTTP サーバーに要求を送信するには、このメンバー関数を呼び出します。

```
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLen = 0,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);

BOOL SendRequest(
    CString& strHeaders,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);
```

### <a name="parameters"></a>パラメーター

*ヘッダー*<br/>
送信するヘッダーの名前を含む文字列へのポインター。

*ドウヘッダーレン*<br/>
によって識別されるヘッダーの長*さ*。

*lpオプション*<br/>
要求ヘッダーの直後に送信する任意のデータ。 これは一般に POST および PUT 操作に使用されます。 送信するオプションのデータがない場合は NULL になります。

*dw オプションレン*<br/>
*lpOptional*の長さ。

*str ヘッダー*<br/>
送信される要求のヘッダーの名前を含む文字列。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、スローされた[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトを調べることによって、失敗の原因を特定します。

## <a name="chttpfilesendrequestex"></a><a name="sendrequestex"></a>ファイル::要求の呼び出し

HTTP サーバーに要求を送信するには、このメンバー関数を呼び出します。

```
BOOL SendRequestEx(
    DWORD dwTotalLen,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);

BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,
    LPINTERNET_BUFFERS lpBuffOut,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*ドウトータルレン*<br/>
要求で送信されるバイト数。

*dwFlags*<br/>
操作を説明するフラグ。 適切なフラグの一覧については、Windows SDK[の「HttpSendRequestEx」](/windows/win32/api/wininet/nf-wininet-httpsendrequestexw)を参照してください。

*dw コンテキスト*<br/>
`CHttpFile` 操作のコンテキスト識別子。 このパラメータの詳細については、「解説」を参照してください。

*lpBuffIn*<br/>
操作に使用される入力バッファーを記述する、初期化された[INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw)へのポインター。

*lpBuffOut*<br/>
操作に使用される出力バッファーを記述する初期化されたINTERNET_BUFFERSへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。 呼び出しが失敗した場合は、スローされた[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクトを調べることによって、失敗の原因を特定します。

### <a name="remarks"></a>解説

この関数を使用すると、アプリケーションは の[Write](../../mfc/reference/cinternetfile-class.md#write)メソッドと`CInternetFile`[WriteString](../../mfc/reference/cinternetfile-class.md#writestring)メソッドを使用してデータを送信できます。 この関数のオーバーライドを呼び出す前に、送信するデータの長さを知っている必要があります。 最初の上書きでは、送信するデータの長さを指定できます。 2 番目のオーバーライドは、バッファーを詳細に記述するために使用できる構造体INTERNET_BUFFERSへのポインターを受け入れます。

コンテンツがファイルに書き込まれた後[、EndRequest を](#endrequest)呼び出して操作を終了します。

*dwContext*の既定値は、オブジェクトを作成した`CHttpFile` [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトからオブジェクトに MFC`CHttpFile`によって送信されます。 [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)または[CHttpConnection](../../mfc/reference/chttpconnection-class.md)を呼び`CHttpFile`出してオブジェクトを構築する場合、デフォルトをオーバーライドしてコンテキスト識別子を選択した値に設定できます。 コンテキスト識別子は、識別されるオブジェクトのステータスを提供するために[、CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

### <a name="example"></a>例

このコードは、MFCISAPI という名前の DLL に文字列の内容を送信します。ローカル ホスト サーバー上の DLL。 この例では、 に対して`WriteString`1 回の呼び出しのみを使用してブロック内のデータを送信する場合は、使用できます。

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)
