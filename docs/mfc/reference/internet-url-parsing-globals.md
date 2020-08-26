---
title: インターネット URL 解析のグローバルとヘルパー
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: c7ce6eeee6deb4537d09e102b925a742ada04650
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837165"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>インターネット URL 解析のグローバルとヘルパー

クライアントがインターネットサーバーにクエリを送信するときに、URL 解析グローバルのいずれかを使用して、クライアントに関する情報を抽出できます。 ヘルパー関数は、他のインターネット機能を提供します。

## <a name="internet-url-parsing-globals"></a>インターネット URL 解析用グローバル関数

|名前|説明|
|-|-|
|[AfxParseURL](#afxparseurl)|URL 文字列を解析し、サービスとそのコンポーネントの型を返します。|
|[AfxParseURLEx](#afxparseurlex)|URL 文字列を解析し、サービスとそのコンポーネントの種類、およびユーザー名とパスワードを指定して返します。|

## <a name="other-internet-helpers"></a>その他のインターネットヘルパー

|名前|説明|
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|インターネット接続に関連する例外をスローします。|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|インターネットハンドルの種類を決定します。|

## <a name="afxparseurl"></a><a name="afxparseurl"></a> AfxParseURL

このグローバルは [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)で使用されます。

```
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort);
```

### <a name="parameters"></a>パラメーター

*pstrURL*<br/>
解析する URL を格納している文字列へのポインター。

*dwServiceType*<br/>
インターネットサービスの種類を示します。 使用できる値は次のとおりです。

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

*strServer*<br/>
サービスの種類に続く URL の最初のセグメント。

*strObject*<br/>
URL が参照するオブジェクト (空の場合もあります)。

*nPort*<br/>
URL のサーバー部分またはオブジェクト部分 (存在する場合) のいずれかによって決定されます。

### <a name="return-value"></a>戻り値

URL が正常に解析された場合は0以外の。それ以外の場合は、空であるか、または既知のインターネットサービスの種類が含まれていない場合は0です。

### <a name="remarks"></a>解説

URL 文字列を解析し、サービスとそのコンポーネントの型を返します。

たとえば、は `AfxParseURL` *service://server/dir/dir/object.ext:port* という形式の url を解析し、次のように格納されているコンポーネントを返します。

*Strserver* = = "server"

*strObject* = = "/dir/dir/object"

*Nport* = = #port

*Dwservicetype* = = #service

> [!NOTE]
> この関数を呼び出すには、プロジェクトに AFXINET.H を含める必要があります。始め.

### <a name="requirements"></a>必要条件

  **ヘッダー** afxinet.h

## <a name="afxparseurlex"></a><a name="afxparseurlex"></a> AfxParseURLEx

このグローバル関数は、 [AfxParseURL](#afxparseurl) の拡張バージョンであり、 [CInternetSession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)で使用されます。

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

*pstrURL*<br/>
解析する URL を格納している文字列へのポインター。

*dwServiceType*<br/>
インターネットサービスの種類を示します。 使用できる値は次のとおりです。

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

*strServer*<br/>
サービスの種類に続く URL の最初のセグメント。

*strObject*<br/>
URL が参照するオブジェクト (空の場合もあります)。

*nPort*<br/>
URL のサーバー部分またはオブジェクト部分 (存在する場合) のいずれかによって決定されます。

*strUsername*<br/>
`CString`ユーザーの名前を格納しているオブジェクトへの参照。

*strPassword*<br/>
`CString`ユーザーのパスワードを格納しているオブジェクトへの参照。

*dwFlags*<br/>
URL の解析方法を制御するフラグ。 は、次の値の組み合わせにすることができます。

|値|意味|
|-----------|-------------|
|ICU_DECODE|% XX エスケープシーケンスを文字に変換します。|
|ICU_NO_ENCODE|安全でない文字をエスケープシーケンスに変換しないでください。|
|ICU_NO_META|メタシーケンス ("\." など) を削除しないでください。 and "\..")URL から。|
|ICU_ENCODE_SPACES_ONLY|エンコードスペースのみ。|
|ICU_BROWSER_MODE|' # ' または ' ' の後に文字をエンコードまたはデコードしないでください。 ' ' の後には、末尾の空白を削除しないでください。 この値が指定されていない場合は、URL 全体がエンコードされ、末尾の空白が削除されます。|

MFC の既定値であるフラグを使用しない場合、関数は、すべての安全でない文字とメタシーケンス ( \\ .、\...、 \\ ... など) をエスケープシーケンスに変換します。

### <a name="return-value"></a>戻り値

URL が正常に解析された場合は0以外の。それ以外の場合は、空であるか、または既知のインターネットサービスの種類が含まれていない場合は0です。

### <a name="remarks"></a>解説

このメソッドは、URL 文字列を解析し、サービスとそのコンポーネントの種類、およびユーザーの名前とパスワードを提供します。 フラグは、安全でない文字の処理方法を示します。

> [!NOTE]
> この関数を呼び出すには、プロジェクトに AFXINET.H を含める必要があります。始め.

### <a name="requirements"></a>必要条件

  **ヘッダー** afxinet.h

## <a name="afxgetinternethandletype"></a><a name="afxgetinternethandletype"></a> AfxGetInternetHandleType

このグローバル関数を使用して、インターネットハンドルの種類を決定します。

### <a name="syntax"></a>構文

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>パラメーター

*hQuery*<br/>
インターネットクエリを処理するハンドル。

### <a name="return-value"></a>戻り値

WININET によって定義されたインターネットサービスの種類のいずれか。始め. これらのインターネットサービスの一覧については、「解説」を参照してください。 ハンドルが NULL であるか認識されない場合、関数は AFX_INET_SERVICE_UNK を返します。

### <a name="remarks"></a>解説

次の一覧は、によって返される可能性のあるインターネットの種類を示してい `AfxGetInternetHandleType` ます。

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
> この関数を呼び出すには、プロジェクトに AFXINET.H を含める必要があります。始め.

### <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="afxthrowinternetexception"></a><a name="afxthrowinternetexception"></a> AfxThrowInternetException

インターネット例外をスローします。

### <a name="syntax"></a>構文

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>パラメーター

*dwContext*<br/>
エラーの原因となった操作のコンテキスト識別子。 *DwContext*の既定値は、最初は[CInternetSession](cinternetsession-class.md)で指定され、 [CInternetConnection](cinternetconnection-class.md)および[CInternetFile](cinternetfile-class.md)の派生クラスに渡されます。 接続またはファイルに対して実行される特定の操作については、通常、独自の *dwContext* を使用して既定値をオーバーライドします。 この値は、特定の操作の状態を識別するために [CInternetSession:: OnStatusCallback](cinternetsession-class.md#onstatuscallback) に返されます。

*dwError*<br/>
例外の原因となったエラー。

### <a name="remarks"></a>解説

オペレーティングシステムのエラーコードに基づいて、原因を特定する責任があります。

> [!NOTE]
> この関数を呼び出すには、プロジェクトに AFXINET.H を含める必要があります。始め.

### <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CInternetException クラス](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
