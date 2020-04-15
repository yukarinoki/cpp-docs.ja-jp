---
title: CHttpConnection クラス
ms.date: 03/27/2019
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
ms.openlocfilehash: af402b532b3aba28bdfefea5afa67331765db4c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351823"
---
# <a name="chttpconnection-class"></a>CHttpConnection クラス

HTTP サーバーへの接続を管理します。

## <a name="syntax"></a>構文

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[接続::CHttp接続](#chttpconnection)|`CHttpConnection` オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHttpConnection::OpenRequest](#openrequest)|HTTP 要求を開きます。|

## <a name="remarks"></a>解説

HTTP は、MFC WinInet クラスによって実装される 3 つのインターネット サーバー プロトコルの 1 つです。

このクラス`CHttpConnection`には、HTTP プロトコルを使用してサーバーへの接続を管理するコンストラクターと 1 つのメンバー関数[OpenRequest](#openrequest)が含まれています。

HTTP サーバーと通信するには、まず[CInternetSession](../../mfc/reference/cinternetsession-class.md)のインスタンスを作成してから[、CHttpConnection](#chttpconnection)オブジェクトを作成する必要があります。 オブジェクトを`CHttpConnection`直接作成することはありません。むしろ、オブジェクトを作成してポインタを`CHttpConnection`返す[CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)を呼び出します。

他の MFC`CHttpConnection`インターネット クラスとの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。 サポートされている他の 2 つのインターネット プロトコルを使用してサーバーに接続する方法の詳細については、[クラス CGopherConnection](../../mfc/reference/cgopherconnection-class.md)と[CFtpConnection](../../mfc/reference/cftpconnection-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="chttpconnectionchttpconnection"></a><a name="chttpconnection"></a>接続::CHttp接続

このメンバー関数は、`CHttpConnection`オブジェクトを構築するために呼び出されます。

```
CHttpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>パラメーター

*セッション*<br/>
[オブジェクト](../../mfc/reference/cinternetsession-class.md)へのポインター。

*hコネクテッド*<br/>
インターネット接続へのハンドル。

*を行う*<br/>
サーバー名を含む文字列へのポインター。

*dw コンテキスト*<br/>
`CInternetConnection`オブジェクトのコンテキスト識別子。 *dwContext*の詳細については、「**解説」** を参照してください。

*nポート*<br/>
この接続のインターネット ポートを識別する番号。

*ユーザー名*<br/>
サインインするユーザーの名前を指定する、NULL で終わる文字列へのポインター。 NULL の場合、デフォルトは匿名です。

*パスワード*<br/>
サインインに使用するパスワードを指定する、null で終わる文字列へのポインター。 *pstrPassword*と*pstrUserName*の両方が NULL の場合、既定の匿名パスワードはユーザーの電子メール名です。 *場合は、pstrPassword*は NULL または空の文字列が *、pstrUserName*は NULL ではない場合は、空白のパスワードが使用されます。 次の表は、4 つの設定の*pstrUserName*と*pstrPassword*の動作を示しています。

|*ユーザー名*|*パスワード*|FTP サーバーに送信されたユーザー名|FTP サーバーに送信されるパスワード|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL または " "|NULL または " "|「匿名」|ユーザーの電子メール名|
|NULL 以外の文字列|NULL または " "|*ユーザー名*|" "|
|NULL |NULL 以外の文字列|ERROR|ERROR|
|NULL 以外の文字列|NULL 以外の文字列|*ユーザー名*|*パスワード*|

*dwFlags*<br/>
フラグの`INTERNET_FLAG_*`任意の組み合わせ。 *dwFlags*値の説明については[、CHttpConnection::OpenRequest](#openrequest)の**解説**セクションの表を参照してください。

### <a name="remarks"></a>解説

`CHttpConnection`直接作成することはありません。 代わりに、オブジェクトを作成するには[、CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)を呼び出します。

## <a name="chttpconnectionopenrequest"></a><a name="openrequest"></a>をクリックします。

このメンバー関数を呼び出して HTTP 接続を開きます。

```
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

CHttpFile* OpenRequest(
    int nVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
要求で使用する動詞を含む文字列へのポインター。 NULL の場合は、"GET" が使用されます。

*名前*<br/>
指定した動詞のターゲット オブジェクトを含む文字列へのポインター。 この文字列は、通常、ファイル名、実行可能モジュール、または検索指定子です。

*プストレッサー*<br/>
要求内の URL が取得されたドキュメントのアドレス (URL) を指定する文字列へのポインター (*pstrObjectName*) 。 NULL の場合、HTTP ヘッダーは指定されません。

*dw コンテキスト*<br/>
`OpenRequest` 操作のコンテキスト識別子。 *dwContext*の詳細については、「解説」を参照してください。

*型指定の種類*<br/>
クライアントが受け入れるコンテンツ タイプを示す文字列への LPCTSTR ポインターの NULL で終わる配列へのポインター。 *ppstrAcceptTypes*が NULL の場合、サーバーは、クライアントが "text/*" 型のドキュメント (テキスト ドキュメントのみで、画像やその他のバイナリ ファイルは受け入れない) と解釈します。 コンテンツ タイプは CGI 変数 CONTENT_TYPE と同等です。HTTP POST や PUT など情報が添付されるクエリのデータの形式を識別します。

*をクリックします。*<br/>
HTTP バージョンを定義する文字列へのポインター。 NULL の場合は、"HTTP/1.0" が使用されます。

*dwFlags*<br/>
INTERNET_ FLAG_* フラグの任意の組み合わせ。 可能な*dwFlags*値の説明については、「解説」を参照してください。

*nVerb*<br/>
HTTP 要求の種類に関連付けられた番号。 以下のいずれかを指定できます。

|HTTP 要求の種類|*nVerb 値*|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>戻り値

要求された[CHttpFile](../../mfc/reference/chttpfile-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

*dwFlags は*、次のいずれかになります。

|インターネット フラグ|説明|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|要求されたファイル、オブジェクト、またはディレクトリ リストをキャッシュからではなく元のサーバーからダウンロードします。|
|INTERNET_FLAG_DONT_CACHE|返されたエンティティをキャッシュに追加しません。|
|INTERNET_FLAG_MAKE_PERSISTENT|返されたエンティティを永続エンティティとしてキャッシュに追加します。 これは、標準のキャッシュ クリーンアップ、整合性チェック、またはガベージ コレクションは、キャッシュからこの項目を削除できないことを意味します。|
|INTERNET_FLAG_SECURE|安全なトランザクション セマンティクスを使用します。 これは、SSL/PCT を使用するように変換され、HTTP 要求でのみ意味があります。|
|INTERNET_FLAG_NO_AUTO_REDIRECT|HTTP でのみ使用され、リダイレクトを[CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest)で自動的に処理してはならないことを指定します。|

`dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子は、[その CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト`CHttpConnection`によって作成されたオブジェクトのこの特定の操作に関連付けられます。 値は、それが識別された操作の状態を提供するために[CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返されます。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet」](../../mfc/wininet-basics.md)を参照してください。

この関数では例外がスローされる場合があります。

## <a name="see-also"></a>関連項目

[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[クラス](../../mfc/reference/chttpfile-class.md)
