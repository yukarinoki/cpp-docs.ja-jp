---
title: グローバルおよびヘルパーのインターネット URL 解析
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 742b381ecb55c433d0f384174b7612fcc21e9716
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356618"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>グローバルおよびヘルパーのインターネット URL 解析

クライアントがインターネット サーバーにクエリを送信する場合、グローバル解析の URL のいずれかを使用して、クライアントに関する情報を抽出できます。 ヘルパー関数は、他のインターネット機能を提供します。

## <a name="internet-url-parsing-globals"></a>インターネット URL 解析用グローバル関数

|||
|-|-|
|[AfxParseURL](#afxparseurl)|URL 文字列を解析し、サービスの種類とそのコンポーネントを返します。|
|[AfxParseURLEx](#afxparseurlex)|URL 文字列を解析し、サービスの種類とそのコンポーネントを返します。|

## <a name="other-internet-helpers"></a>その他のインターネット ヘルパー

|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|インターネット接続に関連する例外をスローします。|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|インターネット ハンドルの種類を決定します。|

## <a name="afxparseurl"></a><a name="afxparseurl"></a>アfxパースURL

このグローバルは[、Cインターネットセッションで使用されます::オープンURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
解析対象の URL を含む文字列へのポインター。

*サービスタイプ*<br/>
インターネット サービスの種類を示します。 使用できる値は次のとおりです。

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*サーバー*<br/>
サービスの種類に続く URL の最初のセグメント。

*strオブジェクト*<br/>
URL が参照するオブジェクト (空の場合があります)。

*nポート*<br/>
どちらかが存在する場合は、URL のサーバーまたはオブジェクトの部分から判別されます。

### <a name="return-value"></a>戻り値

URL が正常に解析された場合は 0 以外の値を返します。それ以外の場合は、0 が空であるか、既知のインターネット サービスの種類が含まれていない場合。

### <a name="remarks"></a>解説

URL 文字列を解析し、サービスの種類とそのコンポーネントを返します。

たとえば、`AfxParseURL`フォームの URL を*解析service://server/dir/dir/object.ext:port*し、次のように格納されているコンポーネントを返します。

*サーバー* == "サーバー"

*オブジェクト*== "/dir/dir/オブジェクト/オブジェクト.ext"

*nポート*== #port

*#service=*

> [!NOTE]
> この関数を呼び出すためには、プロジェクトに AFXINET が含まれている必要があります。H。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxinet.h

## <a name="afxparseurlex"></a><a name="afxparseurlex"></a>アックスパースURLEx

このグローバル関数は[AfxParseURL](#afxparseurl)の拡張バージョンであり[、C インターネットセッションで使用されます。](../../mfc/reference/cinternetsession-class.md#openurl)

```
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort,
    CString& strUsername,
    CString& strPassword,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
解析対象の URL を含む文字列へのポインター。

*サービスタイプ*<br/>
インターネット サービスの種類を示します。 使用できる値は次のとおりです。

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*サーバー*<br/>
サービスの種類に続く URL の最初のセグメント。

*strオブジェクト*<br/>
URL が参照するオブジェクト (空の場合があります)。

*nポート*<br/>
どちらかが存在する場合は、URL のサーバーまたはオブジェクトの部分から判別されます。

*ユーザー名*<br/>
ユーザーの名前を`CString`含むオブジェクトへの参照。

*スズパスワード*<br/>
ユーザーのパスワードを`CString`含むオブジェクトへの参照。

*dwFlags*<br/>
URL の解析方法を制御するフラグ。 次の値を組み合わせることができます。

|[値]|意味|
|-----------|-------------|
|ICU_DECODE|%XX エスケープ シーケンスを文字に変換します。|
|ICU_NO_ENCODE|安全でない文字をエスケープ シーケンスに変換しないでください。|
|ICU_NO_META|メタシーケンス ("\" など) は削除しないでください。 と"\ ."URL から取得します。|
|ICU_ENCODE_SPACES_ONLY|スペースのみをエンコードします。|
|ICU_BROWSER_MODE|'#' または '' の後の文字をエンコードまたはデコードしないでください。 この値を指定しない場合、URL 全体がエンコードされ、末尾の空白が削除されます。|

MFC の既定値 (フラグなし) を使用すると、関数は、安全でないすべての文字とメタ シーケンス\\(.、\ ..、.)\\をエスケープ シーケンスに変換します。

### <a name="return-value"></a>戻り値

URL が正常に解析された場合は 0 以外の値を返します。それ以外の場合は、0 が空であるか、既知のインターネット サービスの種類が含まれていない場合。

### <a name="remarks"></a>解説

URL 文字列を解析し、サービスの種類とそのコンポーネントを返し、ユーザーの名前とパスワードを指定します。 フラグは、安全でない文字の処理方法を示します。

> [!NOTE]
> この関数を呼び出すためには、プロジェクトに AFXINET が含まれている必要があります。H。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxinet.h

## <a name="afxgetinternethandletype"></a><a name="afxgetinternethandletype"></a>型指定

このグローバル関数を使用して、インターネット ハンドルの種類を確認します。

### <a name="syntax"></a>構文

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>パラメーター

*hクエリ*<br/>
インターネット クエリへのハンドル。

### <a name="return-value"></a>戻り値

WININET によって定義されたインターネット サービスの種類。H。 これらのインターネット サービスの一覧については、「解説」を参照してください。 ハンドルが NULL であるか認識されない場合、関数はAFX_INET_SERVICE_UNKを返します。

### <a name="remarks"></a>解説

で返される可能性のあるインターネットの種類を`AfxGetInternetHandleType`次に示します。

- INTERNET_HANDLE_TYPE_INTERNET

- INTERNET_HANDLE_TYPE_CONNECT_FTP

- INTERNET_HANDLE_TYPE_CONNECT_GOPHER

- INTERNET_HANDLE_TYPE_CONNECT_HTTP

- INTERNET_HANDLE_TYPE_FTP_FIND

- INTERNET_HANDLE_TYPE_FTP_FIND_HTML

- INTERNET_HANDLE_TYPE_FTP_FILE

- INTERNET_HANDLE_TYPE_FTP_FILE_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FIND

- INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FILE

- INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML

- INTERNET_HANDLE_TYPE_HTTP_REQUEST

> [!NOTE]
> この関数を呼び出すためには、プロジェクトに AFXINET が含まれている必要があります。H。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="afxthrowinternetexception"></a><a name="afxthrowinternetexception"></a>アfxスローインターネット例外

インターネット例外をスローします。

### <a name="syntax"></a>構文

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>パラメーター

*dw コンテキスト*<br/>
エラーの原因となった操作のコンテキスト識別子。 *dwContext*の既定値は、もともと[CInternetSession](cinternetsession-class.md)で指定され[、C インターネット接続](cinternetconnection-class.md)クラスと[C インターネットファイル](cinternetfile-class.md)派生クラスに渡されます。 接続またはファイルに対して実行される特定の操作の場合、通常は、独自の*dwContext*を使用してデフォルトをオーバーライドします。 この値は、特定の操作の状態を識別するために[CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback)に返されます。

*エラー*<br/>
例外の原因となったエラー。

### <a name="remarks"></a>解説

オペレーティング システムのエラー コードに基づいて原因を特定する必要があります。

> [!NOTE]
> この関数を呼び出すためには、プロジェクトに AFXINET が含まれている必要があります。H。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CInternetException クラス](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
