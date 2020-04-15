---
title: クラス
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
ms.openlocfilehash: 3468e17b031d0a72bc56d915c689fbe4c78859e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330480"
---
# <a name="curl-class"></a>クラス

このクラスは URL を表します。 既存の URL 文字列を解析するか、最初から文字列を構築するかにかかわらず、URL の各要素を他の要素とは別に操作できます。

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
|[CUrl::CUrl](#curl)|コンストラクターです。|
|[Url::~CUrl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CUrl::正規化](#canonicalize)|URL 文字列を正規形式に変換します。|
|[クール::クリア](#clear)|すべての URL フィールドをクリアします。|
|[クール::クラックUrl](#crackurl)|URL をデコードして解析します。|
|[Url::Url を作成します。](#createurl)|URL を作成します。|
|[ソース情報を取得します。](#getextrainfo)|URL から追加情報 (*テキスト*や # *text*など) を取得します。|
|[を使用します。](#getextrainfolength)|URL から取得する追加情報 (*テキスト*や # *text*など) の長さを取得します。|
|[ホスト名を取得します。](#gethostname)|URL からホスト名を取得します。|
|[を使用します。](#gethostnamelength)|ホスト名の長さを取得します。|
|[Url::ゲットパスワード](#getpassword)|URL からパスワードを取得します。|
|[パスワードの長さを取得します。](#getpasswordlength)|パスワードの長さを取得します。|
|[ポート番号を取得します。](#getportnumber)|ATL_URL_PORTのポート番号を取得します。|
|[CUrl::ゲットスキーム](#getscheme)|URL スキームを取得します。|
|[ページ名を取得します。](#getschemename)|URL スキーム名を取得します。|
|[を使用します。](#getschemenamelength)|URL スキーム名の長さを取得します。|
|[を見る](#geturllength)|URL の長さを取得します。|
|[ページパス](#geturlpath)|URL パスを取得します。|
|[を見る](#geturlpathlength)|URL パスの長さを取得します。|
|[ユーザー名を取得します。](#getusername)|URL からユーザー名を取得します。|
|[ユーザー名の長さを取得します。](#getusernamelength)|ユーザー名の長さを取得します。|
|[ソース情報を設定します。](#setextrainfo)|URL の追加情報 (テキストや # *text*など*text*) を設定します。|
|[サービス名を設定します。](#sethostname)|ホスト名を設定します。|
|[セットパスワード](#setpassword)|パスワードを設定します。|
|[セットポート番号](#setportnumber)|ATL_URL_PORTの観点からポート番号を設定します。|
|[CUrl::セットスキーム](#setscheme)|URL スキームを設定します。|
|[セット::セットスキーム名](#setschemename)|URL スキーム名を設定します。|
|[Url::セットパス](#seturlpath)|URL パスを設定します。|
|[ユーザー名を設定します。](#setusername)|ユーザー名を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CUrl::演算子 =](#operator_eq)|指定した`CUrl`オブジェクトを現在`CUrl`のオブジェクトに割り当てます。|

## <a name="remarks"></a>解説

`CUrl`では、パスやポート番号など、URL のフィールドを操作できます。 `CUrl`は、次の形式の URL を認識します。

\<スキーム>://\<ユーザー名\<>: パスワード>\@\<ホスト名\<>:\<\<ポート番号>/ UrlPath>エクストラ情報>

(一部のフィールドはオプションです。たとえば、次の URL を考えてみます。

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[次](#crackurl)のように解析します。

- スキーム: "http" または[ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- ユーザー名: "誰か"

- パスワード: "秘密"

- ホスト名:`www.microsoft.com`" "

- ポートナンバー: 80

- UrlPath: "visualc/stuff.htm"

- エクストラ情報: "#contents"

たとえば、UrlPath フィールドを操作するには[、GetUrlPath](#geturlpath) [、GetUrlPathLength、](#geturlpathlength)および[SetUrlPath](#seturlpath)を使用します。 完全な URL 文字列を作成するには[CreateUrl](#createurl)を使用します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="curlcanonicalize"></a><a name="canonicalize"></a>CUrl::正規化

URL 文字列を正規形式に変換します。

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
正規化を制御するフラグ。 フラグが指定されていない場合 (*dwFlags* = 0)、メソッドは、安全でないすべての文字と\\メタ シーケンス (.,\ \\.,、.. など) をエスケープ シーケンスに変換します。 *dwFlags は*、次のいずれかの値を指定できます。

- ATL_URL_BROWSER_MODE: "#" または "" の後の文字をエンコードまたはデコードせず、"" の後ろの空白を削除しません。 この値を指定しない場合、URL 全体がエンコードされ、末尾の空白が削除されます。

- ATL_URL _DECODE: URL が解析される前に、すべての %XX シーケンスをエスケープ シーケンスを含む文字に変換します。

- ATL_URL _ENCODE_PERCENT: 検出されたパーセント記号をエンコードします。 デフォルトでは、パーセント記号はエンコードされません。

- ATL_URL_ENCODE_SPACES_ONLY: スペースのみをエンコードします。

- ATL_URL_NO_ENCODE: 安全でない文字をエスケープ シーケンスに変換しません。

- ATL_URL_NO_META: URL からメタシーケンス ("." "." や "."など) を削除しません。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

正規形式への変換には、安全でない文字とスペースをエスケープシーケンスに変換する必要があります。

## <a name="curlclear"></a><a name="clear"></a>クール::クリア

すべての URL フィールドをクリアします。

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a>クール::クラックUrl

URL をデコードして解析します。

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
URL。

*dwFlags*<br/>
解析後に*lpszUrl*のすべてのエスケープ文字を実際の値に変換するには、ATL_URL_DECODEまたはATL_URL_ESCAPEを指定します。 (Visual C++ 2005 より前の場合、ATL_URL_DECODE解析前にすべてのエスケープ文字が変換されました。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="curlcreateurl"></a><a name="createurl"></a>Url::Url を作成します。

このメソッドは、CUrl オブジェクトのコンポーネント フィールドから URL 文字列を作成します。

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
完全な URL 文字列を保持する文字列バッファー。

*長さを持つ*<br/>
*文字列バッファーの最大*長。

*dwFlags*<br/>
ATL_URL_ESCAPE指定すると *、lpszUrl*のすべてのエスケープ文字が実際の値に変換されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、次の形式を使用して完全な URL 文字列を構築するために、個々のフィールドを追加します。

**\<スキーム\<>:// ユーザー\<>: ドメイン\@\<>>渡す:\<ポート>\<パス>\<追加の>**

このメソッドを呼び出すとき *、pdwMaxLength*パラメーターは、最初に*lpszUrl*パラメーターによって参照される文字列バッファーの最大長を含める必要があります。 *pdwMaxLength*パラメーターの値は、URL 文字列の実際の長さで更新されます。

### <a name="example"></a>例

このサンプルでは、CUrl オブジェクトの作成とその URL 文字列の取得方法を示します。

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a>CUrl::CUrl

コンストラクターです。

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>パラメーター

*url*<br/>
URL`CUrl`を作成するためにコピーするオブジェクト。

## <a name="curlcurl"></a><a name="dtor"></a>Url::~CUrl

デストラクターです。

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a>ソース情報を取得します。

URL から追加情報 (*テキスト*や # *text*など) を取得します。

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>戻り値

追加情報を含む文字列を返します。

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a>を使用します。

URL から取得する追加情報 (*テキスト*や # *text*など) の長さを取得します。

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>戻り値

追加情報を含む文字列の長さを返します。

## <a name="curlgethostname"></a><a name="gethostname"></a>ホスト名を取得します。

URL からホスト名を取得します。

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>戻り値

ホスト名を返します。

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a>を使用します。

ホスト名の長さを取得します。

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>戻り値

ホスト名の長さを返します。

## <a name="curlgetpassword"></a><a name="getpassword"></a>Url::ゲットパスワード

URL からパスワードを取得します。

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>戻り値

パスワードを返します。

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a>パスワードの長さを取得します。

パスワードの長さを取得します。

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>戻り値

パスワードの長さを返します。

## <a name="curlgetportnumber"></a><a name="getportnumber"></a>ポート番号を取得します。

ポート番号を取得します。

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>戻り値

ポート番号を返します。

## <a name="curlgetscheme"></a><a name="getscheme"></a>CUrl::ゲットスキーム

URL スキームを取得します。

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>戻り値

URL のスキームを記述する[ATL_URL_SCHEME](atl-url-scheme-enum.md)値を返します。

## <a name="curlgetschemename"></a><a name="getschemename"></a>ページ名を取得します。

URL スキーム名を取得します。

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>戻り値

URL スキーム名 ("http" や "ftp" など) を返します。

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a>を使用します。

URL スキーム名の長さを取得します。

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>戻り値

URL スキーム名の長さを返します。

## <a name="curlgeturllength"></a><a name="geturllength"></a>を見る

URL の長さを取得します。

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>戻り値

URL の長さを返します。

## <a name="curlgeturlpath"></a><a name="geturlpath"></a>ページパス

URL パスを取得します。

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>戻り値

URL パスを返します。

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a>を見る

URL パスの長さを取得します。

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>戻り値

URL パスの長さを返します。

## <a name="curlgetusername"></a><a name="getusername"></a>ユーザー名を取得します。

URL からユーザー名を取得します。

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>戻り値

ユーザー名を返します。

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a>ユーザー名の長さを取得します。

ユーザー名の長さを取得します。

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>戻り値

ユーザー名の長さを返します。

## <a name="curloperator-"></a><a name="operator_eq"></a>CUrl::演算子 =

指定した`CUrl`オブジェクトを現在`CUrl`のオブジェクトに割り当てます。

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>パラメーター

*url*<br/>
現在`CUrl`のオブジェクトにコピーするオブジェクト。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照を返します。

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a>ソース情報を設定します。

URL の追加情報 (テキストや # *text*など*text*) を設定します。

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>パラメーター

*情報を提供します。*<br/>
URL に含める追加情報を含む文字列。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="curlsethostname"></a><a name="sethostname"></a>サービス名を設定します。

ホスト名を設定します。

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>パラメーター

*ホスト*<br/>
ホスト名です。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="curlsetpassword"></a><a name="setpassword"></a>セットパスワード

パスワードを設定します。

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>パラメーター

*lpszパス*<br/>
パスワード。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="curlsetportnumber"></a><a name="setportnumber"></a>セットポート番号

ポート番号を設定します。

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>パラメーター

*nPrt*<br/>
ポート番号。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="curlsetscheme"></a><a name="setscheme"></a>CUrl::セットスキーム

URL スキームを設定します。

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>パラメーター

*nスキーム*<br/>
スキームの[ATL_URL_SCHEME](atl-url-scheme-enum.md)値の 1 つ。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

スキームを名前で設定することもできます[(CUrl::SetSchemeName を参照](#setschemename))。

## <a name="curlsetschemename"></a><a name="setschemename"></a>セット::セットスキーム名

URL スキーム名を設定します。

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>パラメーター

*lpszSchm*<br/>
URL スキーム名。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

ATL_URL_SCHEME[定数を](atl-url-scheme-enum.md)使用してスキームを設定することもできます[(CUrl::SetScheme](#setscheme)を参照)。

## <a name="curlseturlpath"></a><a name="seturlpath"></a>Url::セットパス

URL パスを設定します。

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
URL パス。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="curlsetusername"></a><a name="setusername"></a>ユーザー名を設定します。

ユーザー名を設定します。

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>パラメーター

*おおむつお*<br/>
ユーザー名です。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)
