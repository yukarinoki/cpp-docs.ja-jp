---
title: CHttpFile クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a7fbdb3baff7531aa4e391e5d7e936c39e38fc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372620"
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
|[CHttpFile::CHttpFile](#chttpfile)|
          `CHttpFile` オブジェクトを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|HTTP サーバーに送信される要求にヘッダーを追加します。|  
|[CHttpFile::EndRequest](#endrequest)|HTTP サーバーに送信される要求の終了、 [SendRequestEx](#sendrequestex)メンバー関数。|  
|[CHttpFile::GetFileURL](#getfileurl)|指定されたファイルの URL を取得します。|  
|[CHttpFile::GetObject](#getobject)|HTTP サーバーへの要求で動詞のターゲット オブジェクトを取得します。|  
|[CHttpFile::GetVerb](#getverb)|HTTP サーバーへの要求で使用されている動詞を取得します。|  
|[CHttpFile::QueryInfo](#queryinfo)|HTTP サーバーから、応答または要求ヘッダーを返します。|  
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|HTTP 要求に関連付けられている状態コードを取得し、提供された配置`dwStatusCode`パラメーター。|  
|[Chttpfile::sendrequest](#sendrequest)|HTTP サーバーに要求を送信します。|  
|[CHttpFile::SendRequestEx](#sendrequestex)|HTTP サーバーを使用して、要求を送信、[書き込み](../../mfc/reference/cinternetfile-class.md#write)または[WriteString](../../mfc/reference/cinternetfile-class.md#writestring)のメソッド`CInternetFile`です。|  
  
## <a name="remarks"></a>コメント  
 インスタンスを作成する必要がある場合は、インターネット セッションは、HTTP サーバーからデータを読み取り、`CHttpFile`です。  
  
 方法の詳細について`CHttpFile`クラスでは、その他の MFC インターネット機能が、記事を参照して[wininet の基礎を使用したプログラミング インターネット](../../mfc/win32-internet-extensions-wininet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxinet.h  
  
##  <a name="addrequestheaders"></a>  CHttpFile::AddRequestHeaders  
 1 つを追加するには、このメンバー関数を呼び出すか、HTTP 要求に複数の HTTP 要求ヘッダーを処理します。  
  
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
 `pstrHeaders`  
 ヘッダーまたは要求に追加するヘッダーを含む文字列へのポインター。 各ヘッダーは、CR/LF の組み合わせで終わる必要があります。  
  
 `dwFlags`  
 新しいヘッダーのセマンティクスを変更します。 次のいずれかの値を指定します。  
  
- `HTTP_ADDREQ_FLAG_COALESCE` 後続のヘッダーに見つかった最初のヘッダーを追加するフラグを使用して、同じ名前のヘッダーをマージします。 たとえば、"Accept: テキスト/*"続けて"Accept: オーディオ/\*"1 つのヘッダーの形成に"Accept: テキスト/\*、オーディオ/\*"です。 まとめられた、または別のヘッダーと共に送信される要求が受信するデータに対して結合方式のように、呼び出し元のアプリケーションの責任です。  
  
- `HTTP_ADDREQ_FLAG_REPLACE` 削除を実行し、現在のヘッダーを置換するを追加します。 ヘッダー名は、現在のヘッダーを削除するために使用され、新しいヘッダーを追加するすべての値が使用されます。 ヘッダー値が空で、ヘッダーが見つかった場合は削除されます。 指定しない場合、空で、ヘッダー値が置き換えられます。  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW` 既に存在しない場合、ヘッダーを追加します。 1 つ存在する場合、エラーが返されます。  
  
- `HTTP_ADDREQ_FLAG_ADD` With REPLACE を使用します。 存在しない場合は、ヘッダーを追加します。  
  
 `dwHeadersLen`  
 文字の長さの`pstrHeaders`します。 場合は-1 L をし、これは`pstrHeaders`0 で終了すると想定し、長さが計算されます。  
  
 `str`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)要求ヘッダーまたは追加するヘッダーを含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 `AddRequestHeaders` HTTP 要求のハンドルを自由形式の追加のヘッダーを追加します。 HTTP サーバーに送信される正確な要求の詳細に制御を必要とするクライアントによって目的が使用されます。  
  
> [!NOTE]
>  アプリケーションで複数のヘッダーを渡すことができます`pstrHeaders`または`str`の`AddRequestHeaders`を使用して呼び出す`HTTP_ADDREQ_FLAG_ADD`または`HTTP_ADDREQ_FLAG_ADD_IF_NEW`です。 アプリケーションが削除または置換を使用してヘッダーを試むかどうか**HTTP_ADDREQ_FLAG_REMOVE**または`HTTP_ADDREQ_FLAG_REPLACE`、のみ 1 つのヘッダーを指定する`lpszHeaders`です。  
  
##  <a name="chttpfile"></a>  CHttpFile::CHttpFile  
 このメンバー関数は構築するために、`CHttpFile`オブジェクト。  
  
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
 `hFile`  
 インターネット ファイルへのハンドル。  
  
 `hSession`  
 インターネット セッションへのハンドル。  
  
 *pstrObject*  
 含む文字列へのポインター、`CHttpFile`オブジェクト。  
  
 `pstrServer`  
 サーバーの名前を含む文字列へのポインター。  
  
 `pstrVerb`  
 要求を送信するときに使用されるメソッドを含む文字列へのポインター。 指定できます**POST**、**ヘッド**、または`GET`です。  
  
 独自  
 コンテキスト識別子、`CHttpFile`オブジェクト。 参照してください**解説**このパラメーターの詳細についてはします。  
  
 `pConnection`  
 ポインター、 [CHttpConnection](../../mfc/reference/chttpconnection-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 構築することはありません、`CHttpFile`オブジェクトに直接以外の呼び出しではなく[できます](../../mfc/reference/cinternetsession-class.md#openurl)または[しないで](../../mfc/reference/chttpconnection-class.md#openrequest)代わりにします。  
  
 既定値`dwContext`に MFC によって送信される、`CHttpFile`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CHttpFile`オブジェクト。 呼び出すと`CInternetSession::OpenURL`または`CHttpConnection`構築するために、`CHttpFile`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子に返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)いる識別されるオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="endrequest"></a>  CHttpFile::EndRequest  
 HTTP サーバーに送信される要求を終了するには、このメンバー関数を呼び出す、 [SendRequestEx](#sendrequestex)メンバー関数。  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 操作を記述するフラグ。 適切なフラグの一覧は、次を参照してください。 [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230) Windows SDK に含まれています。  
  
 `lpBuffIn`  
 初期化されたへのポインター[記述](http://msdn.microsoft.com/library/windows/desktop/aa385132)操作に使用する入力バッファーを説明します。  
  
 `dwContext`  
 `CHttpFile` 操作のコンテキスト識別子。 このパラメーターの詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しに失敗した場合は、スローされたエラーの原因を判断[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 既定値`dwContext`に MFC によって送信される、`CHttpFile`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CHttpFile`オブジェクト。 呼び出すと[できます](../../mfc/reference/cinternetsession-class.md#openurl)または[CHttpConnection](../../mfc/reference/chttpconnection-class.md)構築するために、`CHttpFile`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子に返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)いる識別されるオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
##  <a name="getfileurl"></a>  CHttpFile::GetFileURL  
 URL として HTTP ファイルの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)このファイルに関連付けられているリソースを参照する URL を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出しに成功した場合にのみ、このメンバー関数を使用して[SendRequest](#sendrequest)または、`CHttpFile`で正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)です。  
  
##  <a name="getobject"></a>  CHttpFile::GetObject  
 これに関連付けられているオブジェクトの名前を取得するには、このメンバー関数を呼び出す`CHttpFile`です。  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトの名前を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出しに成功した場合にのみ、このメンバー関数を使用して[SendRequest](#sendrequest)または、`CHttpFile`で正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)です。  
  
##  <a name="getverb"></a>  CHttpFile::GetVerb  
 これに関連付けられている HTTP 動詞 (またはメソッド) を取得するには、このメンバー関数を呼び出す`CHttpFile`です。  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) HTTP 動詞 (またはメソッド) の名前を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 呼び出しに成功した場合にのみ、このメンバー関数を使用して[SendRequest](#sendrequest)または、`CHttpFile`で正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)です。  
  
##  <a name="queryinfo"></a>  CHttpFile::QueryInfo  
 応答を返すか、HTTP 要求からヘッダーを要求するには、このメンバー関数を呼び出します。  
  
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
 `dwInfoLevel`  
 属性をクエリし、次の要求された情報の種類を指定するフラグの組み合わせです。  
  
- **ヘッダーが**ヘッダー名を検索し、この値を返します`lpvBuffer`出力します。 **ヘッダーが**ヘッダーが見つからない場合にアサーションをスローします。  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS**通常、応答ヘッダーに対してクエリを実行しますが、アプリケーションは、このフラグを使用して要求ヘッダーをクエリもできます。  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME**値がある「最終更新時刻、」などの日付/時刻の文字列のヘッダーの場合は、このフラグは標準の Win32 とヘッダーの値を返します[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造を必要としない、。データを解析するアプリケーション。 このフラグを使用する場合は、使用する可能性がある、`SYSTEMTIME`関数のオーバーライドします。  
  
- **HTTP_QUERY_FLAG_NUMBER**ヘッダー値を持つはステータス コードなどの数字の場合は、このフラグは 32 ビットの数値としてデータを返します。  
  
 参照してください、**解説**有効な値の一覧のセクションでします。  
  
 `lpvBuffer`  
 情報を受け取るバッファーへのポインター。  
  
 `lpdwBufferLength`  
 項目で、これは文字またはバイト数で、データ バッファーの長さを表す値を指します。 参照してください、**解説**セクションは、このパラメーターの詳細情報。  
  
 `lpdwIndex`  
 ヘッダーの 0 から始まるインデックスへのポインター。 指定できます**NULL**です。 同じ名前の複数のヘッダーを列挙するのにには、このフラグを使用します。 入力で`lpdwIndex`を返す指定したヘッダーのインデックスを示します。 出力では、`lpdwIndex`次のヘッダーのインデックスを示します。 次のインデックスが見つからない場合**見つからない**が返されます。  
  
 `str`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)返される情報を受信するオブジェクト。  
  
 `dwIndex`  
 インデックス値。 「`lpdwIndex`」を参照してください。  
  
 *pSysTime*  
 Win32 へのポインター [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 呼び出しに成功した場合にのみ、このメンバー関数を使用して[SendRequest](#sendrequest)または、`CHttpFile`で正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)です。  
  
 データの次の種類を取得する`QueryInfo`:  
  
-   文字列 (既定)  
  
- `SYSTEMTIME` (の"データ:""有効期限:"など、ヘッダー)  
  
- `DWORD` (の**STATUS_CODE**、**多く**, などです)。  
  
 文字列がバッファーに書き込まれ、メンバー関数が成功したときに`lpdwBufferLength`マイナス、終了するための 1 文字の文字列の長さを含む**NULL**文字です。  
  
 考えられる`dwInfoLevel`値が含まれます。  
  
- **HTTP_QUERY_MIME_VERSION**  
  
- **HTTP_QUERY_CONTENT_TYPE**  
  
- **HTTP_QUERY_CONTENT_TRANSFER_ENCODING**  
  
- **HTTP_QUERY_CONTENT_ID**  
  
- **HTTP_QUERY_CONTENT_DESCRIPTION**  
  
- **HTTP_QUERY_CONTENT_LENGTH**  
  
- **HTTP_QUERY_ALLOWED_METHODS**  
  
- **HTTP_QUERY_PUBLIC_METHODS**  
  
- **HTTP_QUERY_DATE**  
  
- **HTTP_QUERY_EXPIRES**  
  
- **HTTP_QUERY_LAST_MODIFIED**  
  
- **HTTP_QUERY_MESSAGE_ID**  
  
- **HTTP_QUERY_URI**  
  
- **HTTP_QUERY_DERIVED_FROM**  
  
- **HTTP_QUERY_LANGUAGE**  
  
- **HTTP_QUERY_COST**  
  
- **HTTP_QUERY_WWW_LINK**  
  
- **HTTP_QUERY_PRAGMA**  
  
- **HTTP_QUERY_VERSION**  
  
- **HTTP_QUERY_STATUS_CODE**  
  
- **HTTP_QUERY_STATUS_TEXT**  
  
- **HTTP_QUERY_RAW_HEADERS**  
  
- **HTTP_QUERY_RAW_HEADERS_CRLF**  
  
##  <a name="queryinfostatuscode"></a>  CHttpFile::QueryInfoStatusCode  
 HTTP 要求に関連付けられている状態コードを取得するには、このメンバー関数を呼び出すし、指定されたに配置`dwStatusCode`パラメーター。  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStatusCode`  
 状態コードへの参照。 状態コードは、要求されたイベントの成否を示します。 参照してください**解説**のステータス コードの説明を選択するためです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するのに呼び出せる可能性があります。  
  
### <a name="remarks"></a>コメント  
 呼び出しに成功した場合にのみ、このメンバー関数を使用して[SendRequest](#sendrequest)または、`CHttpFile`で正常に作成されたオブジェクト[OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)です。  
  
 HTTP 状態コードは、成功または要求の失敗を示すグループに分類されます。 次の表は、ステータス コード グループと最も一般的な HTTP ステータス コードを示しています。  
  
|グループ化|説明|  
|-----------|-------------|  
|200-299|成功|  
|300-399|情報|  
|400-499|要求エラー|  
|500-599|サーバー エラー|  
  
 一般的な HTTP ステータス コード:  
  
|状態コード|説明|  
|-----------------|-------------|  
|200|ある URL、伝送に従います。|  
|400|解釈できない要求|  
|404|要求された URL が見つかりません。|  
|405|サーバーが要求されたメソッドをサポートしていません|  
|500|不明なサーバー エラー|  
|503|サーバーの容量に達しました|  
  
##  <a name="sendrequest"></a>  Chttpfile::sendrequest  
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
 `pstrHeaders`  
 送信するヘッダーの名前を含む文字列へのポインター。  
  
 `dwHeadersLen`  
 によって識別されるヘッダーの長さ`pstrHeaders`です。  
  
 `lpOptional`  
 要求ヘッダーの直後に送信する省略可能なデータです。 これは通常、使用**POST**と**PUT**操作します。 これは、 **NULL**送信する省略可能なデータがない場合。  
  
 *dwOptionalLen*  
 `lpOptional` の長さ。  
  
 `strHeaders`  
 送信される要求のヘッダーの名前を含む文字列。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しに失敗した場合は、スローされたエラーの原因を判断[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクト。  
  
##  <a name="sendrequestex"></a>  CHttpFile::SendRequestEx  
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
 *dwTotalLen*  
 要求で送信されるバイト数。  
  
 `dwFlags`  
 操作を記述するフラグ。 適切なフラグの一覧は、次を参照してください。 [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) Windows SDK に含まれています。  
  
 `dwContext`  
 `CHttpFile` 操作のコンテキスト識別子。 このパラメーターの詳細については、「解説」を参照してください。  
  
 `lpBuffIn`  
 初期化されたへのポインター[記述](http://msdn.microsoft.com/library/windows/desktop/aa385132)操作に使用する入力バッファーを説明します。  
  
 *lpBuffOut*  
 初期化されたへのポインター**記述**操作に使用される出力バッファーを説明します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外。 します。 呼び出しに失敗した場合は、スローされたエラーの原因を判断[CInternetException](../../mfc/reference/cinternetexception-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 この機能により、アプリケーションを使用してデータを送信する、[書き込み](../../mfc/reference/cinternetfile-class.md#write)と[WriteString](../../mfc/reference/cinternetfile-class.md#writestring)のメソッド`CInternetFile`です。 この関数のいずれかのオーバーライドを呼び出す前に送信するデータの長さを知る必要があります。 最初のオーバーライドでは、送信するデータの長さを指定することができます。 2 番目のオーバーライドがへのポインターを受け付ける**記述**構造体は、詳しくバッファーを記述するために使用できます。  
  
 コンテンツがファイルに書き込まれると、呼び出す[EndRequest](#endrequest)操作を終了します。  
  
 既定値`dwContext`に MFC によって送信される、`CHttpFile`オブジェクトから、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトの作成、`CHttpFile`オブジェクト。 呼び出すと[できます](../../mfc/reference/cinternetsession-class.md#openurl)または[CHttpConnection](../../mfc/reference/chttpconnection-class.md)構築するために、`CHttpFile`オブジェクトのコンテキスト識別子を独自の値に設定する既定値をオーバーライドすることができます。 コンテキスト識別子に返される[:onstatuscallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)いる識別されるオブジェクトの状態をします。 記事を参照して[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)詳細については、コンテキスト識別子。  
  
### <a name="example"></a>例  
 次のコード片は、文字列の内容を MFCISAPI をという名前の DLL に送信します。ローカル ホスト サーバー上の DLL です。 この例で使用する 1 つだけの呼び出し中に`WriteString`がブロックでデータを送信する複数の呼び出しを使用します。  
  
 [!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile クラス](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection クラス](../../mfc/reference/chttpconnection-class.md)
