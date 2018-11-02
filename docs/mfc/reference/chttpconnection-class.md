---
title: CHttpConnection クラス
ms.date: 11/04/2016
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
ms.openlocfilehash: 7d11420ca48bfcecbd2534123a36364314b9651c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611004"
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
|[CHttpConnection::CHttpConnection](#chttpconnection)|`CHttpConnection` オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[しないで](#openrequest)|HTTP 要求を開きます。|

## <a name="remarks"></a>Remarks

HTTP では、MFC WinInet クラスによって実装される 3 つのインターネット サーバー プロトコルの 1 つです。

クラスは、`CHttpConnection`コンス トラクターと 1 つのメンバー関数を含む[OpenRequest](#openrequest)、HTTP プロトコルを使って、サーバーへの接続を管理します。

HTTP サーバーを通信するのインスタンスを作成する必要がありますまず[CInternetSession](../../mfc/reference/cinternetsession-class.md)、し、作成、 [CHttpConnection](#_mfc_chttpconnection)オブジェクト。 作成することはありません、`CHttpConnection`オブジェクトに直接; 呼び出しではなく、[代わりに](../../mfc/reference/cinternetsession-class.md#gethttpconnection)、作成し、`CHttpConnection`オブジェクトし、ポインターを返します。

方法の詳細については、`CHttpConnection`クラスでは、その他の MFC インターネット機能は、記事をご覧ください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。 他の 2 つを使用してサーバーへの接続の詳細については、インターネット プロトコル、gopher、FTP サポートされている、クラスを参照してください。 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)と[CFtpConnection](../../mfc/reference/cftpconnection-class.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

##  <a name="chttpconnection"></a>  CHttpConnection::CHttpConnection

このメンバー関数が構築すると呼ばれる、`CHttpConnection`オブジェクト。

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

*pSession*<br/>
ポインターを[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。

*hConnected*<br/>
インターネット接続へのハンドル。

*pstrServer*<br/>
サーバー名を含む文字列へのポインター。

*独自*<br/>
コンテキスト識別子を`CInternetConnection`オブジェクト。 参照してください**解説**の詳細については*独自*します。

*ポート*<br/>
この接続のインターネットのポートを識別する番号。

*pstrUserName*<br/>
ログインするユーザーの名前を指定する null で終わる文字列へのポインター。 NULL の場合、既定値は匿名です。

*pstrPassword*<br/>
ログインに使用するパスワードを指定する null で終わる文字列へのポインター。 両方*pstrPassword*と*pstrUserName*匿名の既定のパスワードはユーザーの電子メール名が NULL の場合。 場合*pstrPassword*が NULL (または空の文字列) が、 *pstrUserName*が NULL でない空白のパスワードを使用します。 次の表の 4 種類の設定の動作は、 *pstrUserName*と*pstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP サーバーに送信されるユーザー名|FTP サーバーに送信されたパスワード|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL または""|NULL または""|「匿名」|ユーザーの電子メール名|
|NULL 以外の文字列|NULL または""|*pstrUserName*|" "|
|NULL 以外の文字列が NULL|ERROR|ERROR||
|NULL 以外の文字列|NULL 以外の文字列|*pstrUserName*|*pstrPassword*|

*dwFlags*<br/>
任意の組み合わせ、`INTERNET_FLAG_*`フラグ。 表を参照して、**解説**の[しないで](#openrequest)の説明については*dwFlags*値。

### <a name="remarks"></a>Remarks

作成することはありません、`CHttpConnection`直接します。 呼び出してオブジェクトを作成する代わりに、[代わりに](../../mfc/reference/cinternetsession-class.md#gethttpconnection)します。

##  <a name="openrequest"></a>  しないで

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

*pstrVerb*<br/>
要求で使用する動詞を含む文字列へのポインター。 NULL の場合は、"GET"が使用されます。

*pstrObjectName*<br/>
指定した動詞のターゲット オブジェクトを含む文字列へのポインター。 これは一般的に、ファイル名、実行可能モジュール、または検索指定子です。

*pstrReferer*<br/>
元のドキュメントのアドレス (URL) を指定する文字列へのポインター、要求内の URL ( *pstrObjectName*) が取得されました。 NULL の場合、HTTP ヘッダーを指定しません。

*独自*<br/>
`OpenRequest` 操作のコンテキスト識別子。 に関する詳細については、「解説」を参照してください*独自*します。

*ppstrAcceptTypes*<br/>
クライアントが受け入れるコンテンツ タイプを示す文字列への null で終わる配列へのポインター。 場合*ppstrAcceptTypes*が null の場合、クライアントでは型のドキュメントのみを受け入れる、サーバーは解釈"テキスト/*"(つまり、テキスト ドキュメントのみとしない画像または他のバイナリ ファイル)。 コンテンツ タイプは CGI 変数 CONTENT_TYPE と同等です。HTTP POST や PUT など情報が添付されるクエリのデータの形式を識別します。

*pstrVersion*<br/>
HTTP バージョンを定義する文字列へのポインター。 NULL の場合は、"http/1.0"が使用されます。

*dwFlags*<br/>
INTERNET_ FLAG_* フラグの任意の組み合わせ。 可能な限りの説明については、「解説」を参照してください。 *dwFlags*値。

*nVerb*<br/>
HTTP 要求の種類に関連付けられた番号。 次のいずれかの値を指定します。

|HTTP 要求の種類|*nVerb*値|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>戻り値

ポインター、 [CHttpFile](../../mfc/reference/chttpfile-class.md)要求オブジェクト。

### <a name="remarks"></a>Remarks

*dwFlags*次のいずれかを指定できます。

|インターネット フラグ|説明|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|要求されたファイル、オブジェクト、またはディレクトリ リストをキャッシュからではなく元のサーバーからダウンロードします。|
|INTERNET_FLAG_DONT_CACHE|返されたエンティティをキャッシュに追加しません。|
|INTERNET_FLAG_MAKE_PERSISTENT|返されたエンティティを永続エンティティとしてキャッシュに追加します。 つまり、標準的なキャッシュのクリーンアップ、整合性チェック、またはガベージ コレクションでは、キャッシュからこの項目を削除することはできません。|
|INTERNET_FLAG_SECURE|安全なトランザクション セマンティクスを使用します。 これは、SSL/PCT を使用するように変換され、HTTP 要求でのみ意味があります。|
|INTERNET_FLAG_NO_AUTO_REDIRECT|HTTP でのみ使用、リダイレクトする必要がありますいない処理されるように指定自動的で[chttpfile::sendrequest](../../mfc/reference/chttpfile-class.md#sendrequest)します。|

`dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子にこの特定の操作に関連付けられて、`CHttpConnection`によって作成されたオブジェクトの[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクト。 値が返される[対応](../../mfc/reference/cinternetsession-class.md#onstatuscallback)が識別される操作の状態を提供します。 記事をご覧ください[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md)コンテキスト識別子の詳細についてはします。

この関数では例外がスローされる場合があります。

## <a name="see-also"></a>関連項目

[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpFile クラス](../../mfc/reference/chttpfile-class.md)
