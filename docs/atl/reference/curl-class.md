---
description: '詳細情報: CUrl クラス'
title: CUrl クラス
ms.date: 05/06/2019
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
ms.openlocfilehash: e8453c4dd1abbfdcb6d794b89fd55f37d7b3f286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140297"
---
# <a name="curl-class"></a>CUrl クラス

このクラスは、URL を表します。 これにより、既存の URL 文字列を解析するか、文字列をゼロから構築するかどうかに関係なく、URL の各要素を他のユーザーとは独立して操作できます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CUrl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CUrl:: CUrl](#curl)|コンストラクターです。|
|[CUrl:: ~ CUrl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CUrl:: 正規化](#canonicalize)|URL 文字列を正規の形式に変換するには、このメソッドを呼び出します。|
|[CUrl:: Clear](#clear)|すべての URL フィールドをクリアするには、このメソッドを呼び出します。|
|[CUrl:: CrackUrl](#crackurl)|URL をデコードして解析するには、このメソッドを呼び出します。|
|[CUrl:: CreateUrl](#createurl)|URL を作成するには、このメソッドを呼び出します。|
|[CUrl:: GetExtraInfo](#getextrainfo)|URL から追加情報 ( *テキスト* や # *text* など) を取得するには、このメソッドを呼び出します。|
|[CUrl:: GetExtraInfoLength](#getextrainfolength)|URL から取得する追加情報 ( *text* や # *text* など) の長さを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetHostName](#gethostname)|URL からホスト名を取得するには、このメソッドを呼び出します。|
|[CUrl:: GetHostNameLength](#gethostnamelength)|ホスト名の長さを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetPassword](#getpassword)|URL からパスワードを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetPasswordLength](#getpasswordlength)|パスワードの長さを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetPortNumber 番号](#getportnumber)|ATL_URL_PORT の観点からポート番号を取得するには、このメソッドを呼び出します。|
|[CUrl:: GetScheme](#getscheme)|URL スキームを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetSchemeName](#getschemename)|URL スキーム名を取得するには、このメソッドを呼び出します。|
|[CUrl:: GetSchemeNameLength](#getschemenamelength)|URL スキーム名の長さを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetUrlLength](#geturllength)|URL の長さを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetUrlPath](#geturlpath)|URL パスを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetUrlPathLength](#geturlpathlength)|URL パスの長さを取得するには、このメソッドを呼び出します。|
|[CUrl:: GetUserName](#getusername)|URL からユーザー名を取得するには、このメソッドを呼び出します。|
|[CUrl:: GetUserNameLength](#getusernamelength)|ユーザー名の長さを取得するには、このメソッドを呼び出します。|
|[CUrl:: SetExtraInfo](#setextrainfo)|URL の追加情報 ( *テキスト* や # *テキスト* など) を設定するには、このメソッドを呼び出します。|
|[CUrl:: SetHostName](#sethostname)|ホスト名を設定するには、このメソッドを呼び出します。|
|[CUrl:: SetPassword](#setpassword)|パスワードを設定するには、このメソッドを呼び出します。|
|[CUrl:: SetPortNumber 番号](#setportnumber)|ATL_URL_PORT の点でポート番号を設定するには、このメソッドを呼び出します。|
|[CUrl:: SetScheme](#setscheme)|URL スキームを設定するには、このメソッドを呼び出します。|
|[CUrl:: SetSchemeName](#setschemename)|URL スキーム名を設定するには、このメソッドを呼び出します。|
|[CUrl:: SetUrlPath](#seturlpath)|URL パスを設定するには、このメソッドを呼び出します。|
|[CUrl:: SetUserName](#setusername)|ユーザー名を設定するには、このメソッドを呼び出します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CUrl:: operator =](#operator_eq)|指定された `CUrl` オブジェクトを現在のオブジェクトに割り当て `CUrl` ます。|

## <a name="remarks"></a>解説

`CUrl` パスやポート番号などの URL のフィールドを操作できます。 `CUrl` は、次の形式の Url を認識します。

\<Scheme>://\<UserName>:\<Password>\@\<HostName>:\<PortNumber>/\<UrlPath>\<ExtraInfo>

(一部のフィールドは省略可能です)。たとえば、次の URL を考えてみます。

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[CUrl:: CrackUrl](#crackurl) は、次のように解析します。

- スキーム: "http" または [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- ユーザー名: "だれか"

- パスワード: "secret"

- ホスト名: " `www.microsoft.com` "

- ポート番号:80

- UrlPath: "visualc/stuff.htm"

- ExtraInfo: "#contents"

UrlPath フィールド (たとえば) を操作するには、 [Geturlpath](#geturlpath)、 [geturlpathlength](#geturlpathlength)、および [seturlpath](#seturlpath)を使用します。 [Createurl](#createurl)を使用して、完全な url 文字列を作成します。

## <a name="requirements"></a>要件

**ヘッダー:** atlutil. h

## <a name="curlcanonicalize"></a><a name="canonicalize"></a> CUrl:: 正規化

URL 文字列を正規の形式に変換するには、このメソッドを呼び出します。

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
正規化を制御するフラグ。 フラグが指定されていない場合 (*dwFlags* = 0)、メソッドは安全でないすべての文字とメタシーケンス ( \\ .、\...、 \\ ... など) をエスケープシーケンスに変換します。 *dwFlags* には、次のいずれかの値を指定できます。

- ATL_URL_BROWSER_MODE: は、"#" または "" の後の文字をエンコードまたはデコードしません。また、"" の後の空白は削除されません。 この値が指定されていない場合は、URL 全体がエンコードされ、末尾の空白が削除されます。

- ATL_URL _DECODE: URL が解析される前に、すべての% XX シーケンスをエスケープシーケンスを含む文字に変換します。

- ATL_URL _ENCODE_PERCENT: 検出されたパーセント記号をエンコードします。 既定では、パーセント記号はエンコードされません。

- ATL_URL _ENCODE_SPACES_ONLY: スペースのみをエンコードします。

- ATL_URL _NO_ENCODE: は安全でない文字をエスケープシーケンスに変換しません。

- ATL_URL _NO_META: は、URL からメタシーケンス ("." や ".." など) を削除しません。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

正規の形式に変換する場合は、安全でない文字とスペースをエスケープシーケンスに変換する必要があります。

## <a name="curlclear"></a><a name="clear"></a> CUrl:: Clear

すべての URL フィールドをクリアするには、このメソッドを呼び出します。

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a> CUrl:: CrackUrl

URL をデコードして解析するには、このメソッドを呼び出します。

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*lpszUrl*<br/>
URL。

*dwFlags*<br/>
ATL_URL_DECODE または ATL_URL_ESCAPE を指定して、の解析後に、 *Lpszurl* 内のすべてのエスケープ文字を実際の値に変換します。 (Visual C++ 2005 より前の ATL_URL_DECODE では、解析前にすべてのエスケープ文字が変換されました)。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="curlcreateurl"></a><a name="createurl"></a> CUrl:: CreateUrl

このメソッドは、CUrl オブジェクトのコンポーネントフィールドから URL 文字列を構築します。

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>パラメーター

*lpszUrl*<br/>
完全な URL 文字列を保持する文字列バッファー。

*pdwMaxLength*<br/>
*Lpszurl* 文字列バッファーの最大長。

*dwFlags*<br/>
*Lpszurl* のすべてのエスケープ文字を実際の値に変換するには、ATL_URL_ESCAPE を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、次の形式を使用して完全な URL 文字列を作成するために、個々のフィールドを追加します。

**\<scheme>://\<user>:\<pass>\@\<domain>:\<port>\<path>\<extra>**

このメソッドを呼び出す場合、 *pdwMaxLength* パラメーターには、最初に *lpszurl* パラメーターによって参照される文字列バッファーの最大長が含まれている必要があります。 *PdwMaxLength* パラメーターの値は、URL 文字列の実際の長さで更新されます。

### <a name="example"></a>例

このサンプルでは、CUrl オブジェクトを作成し、その URL 文字列を取得する方法を示します。

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a> CUrl:: CUrl

コンストラクターです。

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>パラメーター

*urlThat*<br/>
`CUrl`URL を作成するためにコピーするオブジェクト。

## <a name="curlcurl"></a><a name="dtor"></a> CUrl:: ~ CUrl

デストラクターです。

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a> CUrl:: GetExtraInfo

URL から追加情報 ( *テキスト* や # *text* など) を取得するには、このメソッドを呼び出します。

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>戻り値

追加情報を格納している文字列を返します。

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a> CUrl:: GetExtraInfoLength

URL から取得する追加情報 ( *text* や # *text* など) の長さを取得するには、このメソッドを呼び出します。

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>戻り値

追加情報を格納している文字列の長さを返します。

## <a name="curlgethostname"></a><a name="gethostname"></a> CUrl:: GetHostName

URL からホスト名を取得するには、このメソッドを呼び出します。

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>戻り値

ホスト名を返します。

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a> CUrl:: GetHostNameLength

ホスト名の長さを取得するには、このメソッドを呼び出します。

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>戻り値

ホスト名の長さを返します。

## <a name="curlgetpassword"></a><a name="getpassword"></a> CUrl:: GetPassword

URL からパスワードを取得するには、このメソッドを呼び出します。

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>戻り値

パスワードを返します。

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a> CUrl:: GetPasswordLength

パスワードの長さを取得するには、このメソッドを呼び出します。

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>戻り値

パスワードの長さを返します。

## <a name="curlgetportnumber"></a><a name="getportnumber"></a> CUrl:: GetPortNumber 番号

ポート番号を取得するには、このメソッドを呼び出します。

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>戻り値

ポート番号を返します。

## <a name="curlgetscheme"></a><a name="getscheme"></a> CUrl:: GetScheme

URL スキームを取得するには、このメソッドを呼び出します。

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>戻り値

URL のスキームを記述する [ATL_URL_SCHEME](atl-url-scheme-enum.md) 値を返します。

## <a name="curlgetschemename"></a><a name="getschemename"></a> CUrl:: GetSchemeName

URL スキーム名を取得するには、このメソッドを呼び出します。

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>戻り値

URL スキーム名 ("http" や "ftp" など) を返します。

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a> CUrl:: GetSchemeNameLength

URL スキーム名の長さを取得するには、このメソッドを呼び出します。

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>戻り値

URL スキーム名の長さを返します。

## <a name="curlgeturllength"></a><a name="geturllength"></a> CUrl:: GetUrlLength

URL の長さを取得するには、このメソッドを呼び出します。

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>戻り値

URL の長さを返します。

## <a name="curlgeturlpath"></a><a name="geturlpath"></a> CUrl:: GetUrlPath

URL パスを取得するには、このメソッドを呼び出します。

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>戻り値

URL パスを返します。

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a> CUrl:: GetUrlPathLength

URL パスの長さを取得するには、このメソッドを呼び出します。

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>戻り値

URL パスの長さを返します。

## <a name="curlgetusername"></a><a name="getusername"></a> CUrl:: GetUserName

URL からユーザー名を取得するには、このメソッドを呼び出します。

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>戻り値

ユーザー名を返します。

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a> CUrl:: GetUserNameLength

ユーザー名の長さを取得するには、このメソッドを呼び出します。

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>戻り値

ユーザー名の長さを返します。

## <a name="curloperator-"></a><a name="operator_eq"></a> CUrl:: operator =

指定された `CUrl` オブジェクトを現在のオブジェクトに割り当て `CUrl` ます。

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>パラメーター

*urlThat*<br/>
`CUrl`現在のオブジェクトにコピーするオブジェクト。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照を返します。

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a> CUrl:: SetExtraInfo

URL の追加情報 ( *テキスト* や # *テキスト* など) を設定するには、このメソッドを呼び出します。

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>パラメーター

*lpszInfo*<br/>
URL に含める追加情報を格納している文字列。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="curlsethostname"></a><a name="sethostname"></a> CUrl:: SetHostName

ホスト名を設定するには、このメソッドを呼び出します。

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>パラメーター

*lpszHost*<br/>
ホスト名です。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="curlsetpassword"></a><a name="setpassword"></a> CUrl:: SetPassword

パスワードを設定するには、このメソッドを呼び出します。

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>パラメーター

*lpszPass*<br/>
パスワード。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="curlsetportnumber"></a><a name="setportnumber"></a> CUrl:: SetPortNumber 番号

ポート番号を設定するには、このメソッドを呼び出します。

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>パラメーター

*nPrt*<br/>
ポート番号。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="curlsetscheme"></a><a name="setscheme"></a> CUrl:: SetScheme

URL スキームを設定するには、このメソッドを呼び出します。

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>パラメーター

*nScheme*<br/>
スキームの [ATL_URL_SCHEME](atl-url-scheme-enum.md) 値の1つ。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

また、スキームを名前で設定することもできます (「 [CUrl:: SetSchemeName](#setschemename)」を参照してください)。

## <a name="curlsetschemename"></a><a name="setschemename"></a> CUrl:: SetSchemeName

URL スキーム名を設定するには、このメソッドを呼び出します。

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>パラメーター

*Lpsz・ m*<br/>
URL スキーム名。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

[ATL_URL_SCHEME](atl-url-scheme-enum.md)定数を使用してスキームを設定することもできます (「 [CUrl:: setscheme](#setscheme)」を参照してください)。

## <a name="curlseturlpath"></a><a name="seturlpath"></a> CUrl:: SetUrlPath

URL パスを設定するには、このメソッドを呼び出します。

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>パラメーター

*lpszPath*<br/>
URL パス。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="curlsetusername"></a><a name="setusername"></a> CUrl:: SetUserName

ユーザー名を設定するには、このメソッドを呼び出します。

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>パラメーター

*lpszUser*<br/>
ユーザー名です。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)
