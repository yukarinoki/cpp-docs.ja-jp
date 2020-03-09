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
ms.openlocfilehash: 1941af1e16a897235dd90db509d6ed29c2d9a875
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890788"
---
# <a name="chttpconnection-class"></a>CHttpConnection クラス

HTTP サーバーへの接続を管理します。

## <a name="syntax"></a>構文

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CHttpConnection:: CHttpConnection](#chttpconnection)|`CHttpConnection` オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CHttpConnection:: OpenRequest](#openrequest)|HTTP 要求を開きます。|

## <a name="remarks"></a>コメント

HTTP は、MFC WinInet クラスによって実装される3つのインターネットサーバープロトコルのうちの1つです。

クラス `CHttpConnection` には、HTTP プロトコルを使用してサーバーへの接続を管理するコンストラクターと1つのメンバー関数[Openrequest](#openrequest)が含まれています。

HTTP サーバーと通信するには、まず[CInternetSession](../../mfc/reference/cinternetsession-class.md)のインスタンスを作成してから、 [CHttpConnection](#chttpconnection)オブジェクトを作成する必要があります。 `CHttpConnection` オブジェクトを直接作成することはありません。代わりに、 [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)を呼び出して、`CHttpConnection` オブジェクトを作成し、そのオブジェクトへのポインターを返します。

`CHttpConnection` が他の MFC インターネットクラスと連携する方法の詳細については、「 [WinInet を使用したインターネットプログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。 サポートされている2つのインターネットプロトコルである gopher と FTP を使用してサーバーに接続する方法の詳細については、 [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)と[CFtpConnection](../../mfc/reference/cftpconnection-class.md)の各クラスを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>要件

**ヘッダー:** afxinet.h

##  <a name="chttpconnection"></a>CHttpConnection:: CHttpConnection

このメンバー関数は、`CHttpConnection` オブジェクトを構築するために呼び出されます。

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
[CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトへのポインター。

*hConnected*<br/>
インターネット接続を処理するハンドル。

*pstrServer*<br/>
サーバー名を格納している文字列へのポインター。

*dwContext*<br/>
`CInternetConnection` オブジェクトのコンテキスト識別子。 *DwContext*の詳細については、「**解説**」を参照してください。

*nPort*<br/>
この接続のインターネットポートを識別する番号。

*pstrUserName*<br/>
サインインするユーザーの名前を指定する null で終わる文字列へのポインター。 NULL の場合、既定値は anonymous です。

*pstrPassword*<br/>
サインインに使用するパスワードを指定する、null で終わる文字列へのポインター。 *PstrPassword*と*pstrUserName*の両方が NULL の場合、既定の匿名パスワードはユーザーの電子メール名になります。 *PstrPassword*が null または空の文字列で、 *pstrUserName*が null でない場合は、空白のパスワードが使用されます。 次の表では、 *pstrUserName*と*pstrPassword*の4つの設定の動作について説明します。

|*pstrUserName*|*pstrPassword*|FTP サーバーに送信されたユーザー名|FTP サーバーに送信されるパスワード|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL または ""|NULL または ""|非同期|ユーザーの電子メール名|
|NULL 以外の文字列|NULL または ""|*pstrUserName*|" "|
|NULL |NULL 以外の文字列|ERROR|ERROR|
|NULL 以外の文字列|NULL 以外の文字列|*pstrUserName*|*pstrPassword*|

*dwFlags*<br/>
`INTERNET_FLAG_*` フラグの任意の組み合わせ。 *DwFlags*値の説明については、「 [CHttpConnection:: openrequest](#openrequest) 」の「**解説**」の表を参照してください。

### <a name="remarks"></a>コメント

`CHttpConnection` を直接作成することはありません。 代わりに、 [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)を呼び出してオブジェクトを作成します。

##  <a name="openrequest"></a>CHttpConnection:: OpenRequest

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
要求で使用する動詞を含む文字列へのポインター。 NULL の場合、"GET" が使用されます。

*pstrObjectName*<br/>
指定した動詞のターゲット オブジェクトを含む文字列へのポインター。 この文字列は、通常、ファイル名、実行可能モジュール、または検索指定子です。

*pstrReferer*<br/>
要求の URL (*pstrObjectName*) を取得したドキュメントのアドレス (url) を指定する文字列へのポインター。 NULL の場合、HTTP ヘッダーは指定されません。

*dwContext*<br/>
`OpenRequest` 操作のコンテキスト識別子。 *DwContext*の詳細については、「解説」を参照してください。

*ppstrAcceptTypes*<br/>
クライアントによって受け入れられるコンテンツの種類を示す文字列への LPCTSTR ポインターの null で終わる配列へのポインター。 *Ppstraccepttypes*が NULL の場合、サーバーは、クライアントが種類が "text/*" のドキュメントのみ (つまり、画像やその他のバイナリファイルではなくテキストドキュメントのみ) を受け入れると解釈します。 コンテンツ タイプは CGI 変数 CONTENT_TYPE と同等です。HTTP POST や PUT など情報が添付されるクエリのデータの形式を識別します。

*pstrVersion*<br/>
HTTP バージョンを定義する文字列へのポインター。 NULL の場合は、"HTTP/1.0" が使用されます。

*dwFlags*<br/>
INTERNET_ FLAG_* フラグの任意の組み合わせ。 使用可能な*dwFlags*値の説明については、「解説」を参照してください。

*nVerb*<br/>
HTTP 要求の種類に関連付けられた番号。 以下のいずれかを指定できます。

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

要求された[CHttpFile](../../mfc/reference/chttpfile-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>コメント

*dwFlags*には、次のいずれかを指定できます。

|インターネット フラグ|説明|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|要求されたファイル、オブジェクト、またはディレクトリ リストをキャッシュからではなく元のサーバーからダウンロードします。|
|INTERNET_FLAG_DONT_CACHE|返されたエンティティをキャッシュに追加しません。|
|INTERNET_FLAG_MAKE_PERSISTENT|返されたエンティティを永続エンティティとしてキャッシュに追加します。 これは、標準キャッシュのクリーンアップ、整合性チェック、またはガベージコレクションでは、キャッシュからこの項目を削除できないことを意味します。|
|INTERNET_FLAG_SECURE|安全なトランザクション セマンティクスを使用します。 SSL/PCT を使用するように変換され、HTTP 要求でのみ意味があります。|
|INTERNET_FLAG_NO_AUTO_REDIRECT|HTTP でのみ使用され、 [CHttpFile:: SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest)でリダイレクトを自動的に処理しないことを指定します。|

`dwContext` の既定値をオーバーライドして、コンテキスト識別子を独自の値に設定します。 コンテキスト識別子は、 [CInternetSession](../../mfc/reference/cinternetsession-class.md)オブジェクトによって作成された `CHttpConnection` オブジェクトのこの特定の操作に関連付けられます。 値は[CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)に返され、識別された操作の状態を提供します。 コンテキスト識別子の詳細については、「[インターネットの最初の手順: WinInet](../../mfc/wininet-basics.md) 」を参照してください。

この関数では例外がスローされる場合があります。

## <a name="see-also"></a>参照

[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection クラス](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpFile クラス](../../mfc/reference/chttpfile-class.md)
