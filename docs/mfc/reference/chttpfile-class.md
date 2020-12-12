---
description: '詳細情報: CHttpFile クラス'
title: CHttpFile クラス
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
ms.openlocfilehash: 95beff477e19ef15235ceb7235aa0240ec07ff65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209972"
---
# <a name="chttpfile-class"></a>CHttpFile クラス

HTTP サーバー上のファイルを要求し、読み込む機能が用意されています。

## <a name="syntax"></a>構文

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CHttpFile:: CHttpFile](#chttpfile)|`CHttpFile` オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHttpFile:: AddRequestHeaders](#addrequestheaders)|HTTP サーバーに送信される要求にヘッダーを追加します。|
|[CHttpFile:: EndRequest](#endrequest)|[Sendrequestex](#sendrequestex)メンバー関数を使用して HTTP サーバーに送信される要求を終了します。|
|[CHttpFile:: GetFileURL](#getfileurl)|指定されたファイルの URL を取得します。|
|[CHttpFile:: GetObject](#getobject)|HTTP サーバーへの要求に含まれる動詞のターゲットオブジェクトを取得します。|
|[CHttpFile:: GetVerb](#getverb)|HTTP サーバーへの要求で使用された動詞を取得します。|
|[CHttpFile:: QueryInfo](#queryinfo)|HTTP サーバーから応答ヘッダーまたは要求ヘッダーを返します。|
|[CHttpFile:: QueryInfoStatusCode](#queryinfostatuscode)|HTTP 要求に関連付けられているステータスコードを取得し、指定されたパラメーターに格納し `dwStatusCode` ます。|
|[CHttpFile:: SendRequest](#sendrequest)|HTTP サーバーに要求を送信します。|
|[CHttpFile:: SendRequestEx](#sendrequestex)|の [Write](../../mfc/reference/cinternetfile-class.md#write) メソッドまたは [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) メソッドを使用して、HTTP サーバーに要求を送信し `CInternetFile` ます。|

## <a name="remarks"></a>解説

インターネットセッションが HTTP サーバーからデータを読み取る場合は、のインスタンスを作成する必要があり `CHttpFile` ます。

が他の MFC インターネットクラスと連携する方法の詳細については `CHttpFile` 、「 [WinInet を使用したインターネットプログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>要件

**ヘッダー:** afxinet.h

## <a name="chttpfileaddrequestheaders"></a><a name="addrequestheaders"></a> CHttpFile:: AddRequestHeaders

HTTP 要求ハンドルに1つ以上の HTTP 要求ヘッダーを追加するには、このメンバー関数を呼び出します。

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

*pstrHeaders*<br/>
要求に追加するヘッダーまたはヘッダーを格納している文字列へのポインター。 各ヘッダーは、CR/LF ペアで終了する必要があります。

*dwFlags*<br/>
新しいヘッダーのセマンティクスを変更します。 以下のいずれかを指定できます。

- HTTP_ADDREQ_FLAG_COALESCE 同じ名前のヘッダーをマージします。フラグを使用して、後続のヘッダーに見つかった最初のヘッダーを追加します。 たとえば、"accept: text/ \* " の後に「accept: audio/」と入力すると、 \* 1 つのヘッダー "accept: text/ \* , audio/" が形成され \* ます。 結合されたまたは別個のヘッダーで送信された要求によって受信されたデータに対して、まとまりのあるスキームを保証するのは、呼び出し元のアプリケーションによって異なります。

- HTTP_ADDREQ_FLAG_REPLACE によって remove と add が実行され、現在のヘッダーが置き換えられます。 ヘッダー名は、現在のヘッダーを削除するために使用され、完全な値は新しいヘッダーを追加するために使用されます。 ヘッダー値が空で、ヘッダーが見つかった場合は、削除されます。 空でない場合は、ヘッダー値が置き換えられます。

- ヘッダーがまだ存在しない場合にのみ、HTTP_ADDREQ_FLAG_ADD_IF_NEW によって追加されます。 存在する場合は、エラーが返されます。

- REPLACE と共に使用 HTTP_ADDREQ_FLAG_ADD ます。 ヘッダーが存在しない場合は、追加します。

*dwHeadersLen*<br/>
*PstrHeaders* の長さ (文字数)。 この値が-1L の場合、 *pstrHeaders* はゼロで終了し、長さが計算されると見なされます。

*str*<br/>
追加する要求ヘッダーまたはヘッダーを格納している [CString](../../atl-mfc-shared/reference/cstringt-class.md) オブジェクトへの参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) を呼び出してエラーの原因を特定することができます。

### <a name="remarks"></a>解説

`AddRequestHeaders` HTTP 要求ハンドルに追加の自由形式ヘッダーを追加します。 これは、HTTP サーバーに送信される正確な要求を詳細に制御する必要がある高度なクライアントによって使用されることを意図しています。

> [!NOTE]
> アプリケーションでは、HTTP_ADDREQ_FLAG_ADD または HTTP_ADDREQ_FLAG_ADD_IF_NEW を使用した呼び出しに対して、 *pstrHeaders* または *str* に複数のヘッダーを渡すことができ `AddRequestHeaders` ます。 アプリケーションで HTTP_ADDREQ_FLAG_REMOVE または HTTP_ADDREQ_FLAG_REPLACE を使用してヘッダーを削除または置換しようとすると、 *lpszheaders* で1つのヘッダーのみを指定できます。

## <a name="chttpfilechttpfile"></a><a name="chttpfile"></a> CHttpFile:: CHttpFile

このメンバー関数は、オブジェクトを構築するために呼び出され `CHttpFile` ます。

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

*hFile*<br/>
インターネットファイルへのハンドル。

*hSession*<br/>
インターネットセッションを処理するハンドル。

*pstrObject*<br/>
オブジェクトを格納している文字列へのポインター `CHttpFile` 。

*pstrServer*<br/>
サーバーの名前を格納している文字列へのポインター。

*pstrVerb*<br/>
要求を送信するときに使用するメソッドを格納している文字列へのポインター。 POST、HEAD、または GET を指定できます。

*dwContext*<br/>
オブジェクトのコンテキスト識別子 `CHttpFile` 。 このパラメーターの詳細については、「 **解説** 」を参照してください。

*pConnection*<br/>
[CHttpConnection](../../mfc/reference/chttpconnection-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

オブジェクトを直接構築することはありません。 `CHttpFile` 代わりに、 [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) または [CHttpConnection:: openrequest](../../mfc/reference/chttpconnection-class.md#openrequest) を呼び出してください。

の既定値 `dwContext` は、 `CHttpFile` オブジェクトを作成した [CInternetSession](../../mfc/reference/cinternetsession-class.md) オブジェクトからオブジェクトに、MFC によって送信され `CHttpFile` ます。 `CInternetSession::OpenURL`オブジェクトを構築するためにまたはを呼び出す場合は、 `CHttpConnection` `CHttpFile` 既定値をオーバーライドして、コンテキスト識別子を任意の値に設定できます。 コンテキスト識別子は、 [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) に返され、識別されたオブジェクトの状態を提供します。 コンテキスト識別子の詳細については、「 [インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md) 」を参照してください。

## <a name="chttpfileendrequest"></a><a name="endrequest"></a> CHttpFile:: EndRequest

このメンバー関数を呼び出して、 [Sendrequestex](#sendrequestex) メンバー関数を使用して HTTP サーバーに送信される要求を終了します。

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
操作を記述するフラグ。 適切なフラグの一覧については、Windows SDK の「 [HttpEndRequest](/windows/win32/api/wininet/nf-wininet-httpendrequestw) 」を参照してください。

*lpBuffIn*<br/>
操作に使用する入力バッファーを記述する、初期化された [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) へのポインター。

*dwContext*<br/>
`CHttpFile` 操作のコンテキスト識別子。 このパラメーターの詳細については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、スローされた [CInternetException](../../mfc/reference/cinternetexception-class.md) オブジェクトを調べて、エラーの原因を特定します。

### <a name="remarks"></a>解説

*DwContext* の既定値は、 `CHttpFile` オブジェクトを作成した [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトからオブジェクトに、MFC によって送信され `CHttpFile` ます。 [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)または[CHttpConnection](../../mfc/reference/chttpconnection-class.md)を呼び出してオブジェクトを構築する場合は、 `CHttpFile` 既定値をオーバーライドして、コンテキスト識別子を任意の値に設定できます。 コンテキスト識別子は、 [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) に返され、識別されたオブジェクトの状態を提供します。 コンテキスト識別子の詳細については、「 [インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md) 」を参照してください。

## <a name="chttpfilegetfileurl"></a><a name="getfileurl"></a> CHttpFile:: GetFileURL

URL として HTTP ファイルの名前を取得するには、このメンバー関数を呼び出します。

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>戻り値

このファイルに関連付けられているリソースを参照している URL を格納している [CString](../../atl-mfc-shared/reference/cstringt-class.md) オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は、 [Sendrequest](#sendrequest) の呼び出しが成功した後、または `CHttpFile` [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用してください。

## <a name="chttpfilegetobject"></a><a name="getobject"></a> CHttpFile:: GetObject

このメンバー関数を呼び出して、このに関連付けられているオブジェクトの名前を取得し `CHttpFile` ます。

```
CString GetObject() const;
```

### <a name="return-value"></a>戻り値

オブジェクトの名前を格納している [CString](../../atl-mfc-shared/reference/cstringt-class.md) オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は、 [Sendrequest](#sendrequest) の呼び出しが成功した後、または `CHttpFile` [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用してください。

## <a name="chttpfilegetverb"></a><a name="getverb"></a> CHttpFile:: GetVerb

このメンバー関数を呼び出して、このに関連付けられている HTTP 動詞 (またはメソッド) を取得し `CHttpFile` ます。

```
CString GetVerb() const;
```

### <a name="return-value"></a>戻り値

HTTP 動詞 (またはメソッド) の名前を格納している [CString](../../atl-mfc-shared/reference/cstringt-class.md) オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は、 [Sendrequest](#sendrequest) の呼び出しが成功した後、または `CHttpFile` [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用してください。

## <a name="chttpfilequeryinfo"></a><a name="queryinfo"></a> CHttpFile:: QueryInfo

HTTP 要求から応答ヘッダーまたは要求ヘッダーを返すには、このメンバー関数を呼び出します。

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

*dwInfoLevel*<br/>
クエリする属性と、要求された情報の種類を指定する次のフラグの組み合わせ。

- HTTP_QUERY_CUSTOM は、ヘッダー名を検索し、出力時にこの値を *Lpvbuffer* に返します。 ヘッダーが見つからない場合、HTTP_QUERY_CUSTOM はアサーションをスローします。

- HTTP_QUERY_FLAG_REQUEST_HEADERS 通常、アプリケーションは応答ヘッダーを照会しますが、アプリケーションはこのフラグを使用して要求ヘッダーを照会することもできます。

- 値が日付/時刻文字列 ("最終更新時刻" など) であるヘッダーの HTTP_QUERY_FLAG_SYSTEMTIME このフラグは、アプリケーションがデータを解析する必要がない標準の Win32 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 構造体としてヘッダー値を返します。 このフラグを使用する場合は、関数のオーバーライドを使用することをお勧めし `SYSTEMTIME` ます。

- ステータスコードなど、値が数値であるヘッダーの HTTP_QUERY_FLAG_NUMBER、このフラグはデータを32ビットの数値として返します。

使用可能な値の一覧については、「 **解説** 」を参照してください。

*lpvBuffer*<br/>
情報を受け取るバッファーへのポインター。

*lpdwBufferLength*<br/>
入力時には、データバッファーの長さ (文字数またはバイト数) を格納している値を指します。 このパラメーターの詳細については、「 **解説** 」を参照してください。

*lpdwIndex*<br/>
0から始まるヘッダーインデックスへのポインター。 NULL にすることができます。 同じ名前の複数のヘッダーを列挙するには、このフラグを使用します。 入力時、 *lpdwIndex* は、指定されたヘッダーが返される位置を示します。 出力では、 *lpdwIndex* は次のヘッダーのインデックスを示します。 次のインデックスが見つからない場合は、ERROR_HTTP_HEADER_NOT_FOUND が返されます。

*str*<br/>
返された情報を受け取る [CString](../../atl-mfc-shared/reference/cstringt-class.md) オブジェクトへの参照。

*dwIndex*<br/>
インデックス値。 「 *LpdwIndex*」を参照してください。

*pSysTime*<br/>
Win32 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) 構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) を呼び出してエラーの原因を特定することができます。

### <a name="remarks"></a>解説

このメンバー関数は、 [Sendrequest](#sendrequest) の呼び出しが成功した後、または `CHttpFile` [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用してください。

から、次の種類のデータを取得でき `QueryInfo` ます。

- 文字列 (既定値)

- `SYSTEMTIME` ("データ:" "有効期限:" など)。

- DWORD (STATUS_CODE、CONTENT_LENGTH など)

文字列がバッファーに書き込まれ、メンバー関数が成功すると、では、 `lpdwBufferLength` 文字列の長さが文字数から1を引いた NULL 文字が含まれます。

使用できる *dwInfoLevel* の値は次のとおりです。

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

## <a name="chttpfilequeryinfostatuscode"></a><a name="queryinfostatuscode"></a> CHttpFile:: QueryInfoStatusCode

このメンバー関数を呼び出して、HTTP 要求に関連付けられているステータスコードを取得し、指定した *Dwstatuscode* パラメーターに配置します。

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>パラメーター

*dwStatusCode*<br/>
ステータスコードへの参照。 状態コードは、要求されたイベントが成功したか失敗したかを示します。 ステータスコードの説明の選択については、「 **解説** 」を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) を呼び出してエラーの原因を特定することができます。

### <a name="remarks"></a>解説

このメンバー関数は、 [Sendrequest](#sendrequest) の呼び出しが成功した後、または `CHttpFile` [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)によって正常に作成されたオブジェクトに対してのみ使用してください。

HTTP 状態コードは、要求が成功したか失敗したかを示すグループに分類されます。 次の表に、ステータスコードグループと最も一般的な HTTP 状態コードの概要を示します。

|グループ|説明|
|-----------|-------------|
|200 から 299|Success|
|300 から 399|情報|
|400-499|要求エラー|
|500-599|サーバーエラー|

一般的な HTTP 状態コード:

|状態コード|意味|
|-----------------|-------------|
|200|URL があり、転送後|
|400|判読不能の要求|
|404|要求された URL が見つかりません|
|405|サーバーは要求されたメソッドをサポートしていません|
|500|不明なサーバーエラー|
|503|サーバーの容量に達しました|

## <a name="chttpfilesendrequest"></a><a name="sendrequest"></a> CHttpFile:: SendRequest

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

*pstrHeaders*<br/>
送信するヘッダーの名前を格納している文字列へのポインター。

*dwHeadersLen*<br/>
*PstrHeaders* によって識別されるヘッダーの長さ。

*その他*<br/>
要求ヘッダーの直後に送信する任意の省略可能なデータ。 これは、通常、POST および PUT 操作に使用されます。 送信する省略可能なデータがない場合は NULL を指定できます。

*dwOptionalLen*<br/>
*Lpoptional* 長さ。

*strHeaders*<br/>
送信される要求のヘッダーの名前を格納している文字列。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、スローされた [CInternetException](../../mfc/reference/cinternetexception-class.md) オブジェクトを調べて、エラーの原因を特定します。

## <a name="chttpfilesendrequestex"></a><a name="sendrequestex"></a> CHttpFile:: SendRequestEx

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

*dwTotalLen*<br/>
要求で送信されるバイト数。

*dwFlags*<br/>
操作を記述するフラグ。 適切なフラグの一覧については、Windows SDK の「 [HttpSendRequestEx](/windows/win32/api/wininet/nf-wininet-httpsendrequestexw) 」を参照してください。

*dwContext*<br/>
`CHttpFile` 操作のコンテキスト識別子。 このパラメーターの詳細については、「解説」を参照してください。

*lpBuffIn*<br/>
操作に使用する入力バッファーを記述する、初期化された [INTERNET_BUFFERS](/windows/win32/api/wininet/ns-wininet-internet_buffersw) へのポインター。

*lpBuffOut*<br/>
操作に使用される出力バッファーを記述する初期化された INTERNET_BUFFERS へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は0以外の。 呼び出しが失敗した場合は、スローされた [CInternetException](../../mfc/reference/cinternetexception-class.md) オブジェクトを調べて、エラーの原因を特定します。

### <a name="remarks"></a>解説

この関数を使用すると、アプリケーションはの [Write](../../mfc/reference/cinternetfile-class.md#write) メソッドと [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) メソッドを使用してデータを送信でき `CInternetFile` ます。 この関数のいずれかのオーバーライドを呼び出す前に、送信するデータの長さを把握しておく必要があります。 最初の上書きでは、送信するデータの長さを指定できます。 2番目のオーバーライドは INTERNET_BUFFERS 構造体へのポインターを受け入れます。これを使用すると、バッファーを詳細に記述できます。

ファイルにコンテンツが書き込まれたら、 [EndRequest](#endrequest) を呼び出して操作を終了します。

*DwContext* の既定値は、 `CHttpFile` オブジェクトを作成した [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトからオブジェクトに、MFC によって送信され `CHttpFile` ます。 [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)または[CHttpConnection](../../mfc/reference/chttpconnection-class.md)を呼び出してオブジェクトを構築する場合は、 `CHttpFile` 既定値をオーバーライドして、コンテキスト識別子を任意の値に設定できます。 コンテキスト識別子は、 [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) に返され、識別されたオブジェクトの状態を提供します。 コンテキスト識別子の詳細については、「 [インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md) 」を参照してください。

### <a name="example"></a>例

このコード片では、文字列の内容が LOCALHOST サーバー上の MFCISAPI.DLL という名前の DLL に送信されます。 この例では、の呼び出しを1回だけ使用し `WriteString` ていますが、複数の呼び出しを使用してブロック内のデータを送信することも可能です。

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>関連項目

[CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)
