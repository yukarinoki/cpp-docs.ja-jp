---
title: CTokenPrivileges クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
dev_langs:
- C++
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98fb1c50b6bdd46cc6cf0efe7739e8ada60f3274
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762636"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges クラス

このクラスは、のラッパー、`TOKEN_PRIVILEGES`構造体。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CTokenPrivileges
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|コンストラクターです。|
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTokenPrivileges::Add](#add)|1 つまたは複数の権限を追加、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::Delete](#delete)|特権を削除、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::DeleteAll](#deleteall)|すべての特権を削除、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::GetCount](#getcount)|特権のエントリの数を返します、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|取得しますに含まれる権限の名前を表示、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::GetLength](#getlength)|保持するために必要なバイトのバッファー サイズを返します、`TOKEN_PRIVILEGES`構造によって表されます、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|ローカル一意識別子 (Luid) とから属性フラグを取得、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|特権の名前と属性のフラグをから取得、`CTokenPrivileges`オブジェクト。|
|[CTokenPrivileges::GetPTOKEN_PRIVILEGES](#getptoken_privileges)|ポインターを返します、`TOKEN_PRIVILEGES`構造体。|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|指定した権限の名前に関連付けられた属性を取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CTokenPrivileges::operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|値へのポインターにキャスト、`TOKEN_PRIVILEGES`構造体。|
|[CTokenPrivileges::operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>Remarks

[アクセス トークン](/windows/desktop/SecAuthZ/access-tokens)プロセスまたはスレッドのセキュリティ コンテキストを示し、Windows システムにログオンしている各ユーザーに割り当てられているオブジェクトです。

アクセス トークンは、各ユーザーに与えられているさまざまなセキュリティ特権の記述に使用されます。 特権は、ローカルで一意な識別子と呼ばれる 64 ビットの数値で構成されています ( [LUID](/windows/desktop/api/winnt/ns-winnt-_luid)) と記述子の文字列。

`CTokenPrivileges`クラスは、のラッパー、 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)構造体し、0 または多くの権限が含まれています。 削除、または指定されたクラスのメソッドを使用して照会された特権を追加することができます。

Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity.h

##  <a name="add"></a>  CTokenPrivileges::Add

1 つまたは複数の権限を追加、`CTokenPrivileges`アクセス トークンのオブジェクト。

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);  
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*  
WINNT で定義されている、権限の名前を指定する null で終わる文字列へのポインター。H ヘッダー ファイルです。

*bEnable*  
True の場合、特権が有効にします。 False の場合、特権は無効です。

*rPrivileges*  
参照を[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)構造体。 特権と属性がこの構造体からコピーされに追加、`CTokenPrivileges`オブジェクト。

### <a name="return-value"></a>戻り値

このメソッドの最初のフォーム、特権が正常に追加された場合、false それ以外の場合は true を返します。

##  <a name="ctokenprivileges"></a>  CTokenPrivileges::CTokenPrivileges

コンストラクターです。

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );  
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*  
`CTokenPrivileges`新しいオブジェクトに割り当てるオブジェクト。

*rPrivileges*  
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)構造に割り当てる新しい`CTokenPrivileges`オブジェクト。

### <a name="remarks"></a>Remarks

`CTokenPrivileges`を使用してオブジェクトを作成することができます必要に応じて、`TOKEN_PRIVILEGES`構造体または以前に定義された`CTokenPrivileges`オブジェクト。

##  <a name="dtor"></a>  CTokenPrivileges:: ~ CTokenPrivileges

デストラクターです。

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>Remarks

デストラクターは、割り当てられているすべてのリソースを解放します。

##  <a name="delete"></a>  CTokenPrivileges::Delete

特権を削除、`CTokenPrivileges`アクセス トークンのオブジェクト。

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*  
WINNT で定義されている、権限の名前を指定する null で終わる文字列へのポインター。H ヘッダー ファイルです。 定数 SE_SECURITY_NAME、またはその対応する文字列、"SeSecurityPrivilege"たとえば、このパラメーターを指定可能性があります。

### <a name="return-value"></a>戻り値

場合は、特権が正常に削除された、false それ以外の場合は true を返します。

### <a name="remarks"></a>Remarks

このメソッドは、制限付きトークンを作成するためのツールとして役立ちます。

##  <a name="deleteall"></a>  CTokenPrivileges::DeleteAll

すべての特権を削除、`CTokenPrivileges`アクセス トークンのオブジェクト。

```
void DeleteAll() throw();
```

### <a name="remarks"></a>Remarks

含まれているすべての特権を削除、`CTokenPrivileges`アクセス トークンのオブジェクト。

##  <a name="getdisplaynames"></a>  CTokenPrivileges::GetDisplayNames

取得しますに含まれる権限の名前を表示、`CTokenPrivileges`アクセス トークンのオブジェクト。

```
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pDisplayNames*  
`CString` オブジェクトの配列へのポインター。 `CNames` typedef として定義されます:`CTokenPrivileges::CAtlArray<CString>`します。

### <a name="remarks"></a>Remarks

パラメーター`pDisplayNames`の配列へのポインターは、`CString`オブジェクトに含まれる権限に対応する表示名を受け取る、`CTokenPrivileges`オブジェクト。 このメソッドは、のみ WINNT の特権の定義で指定した権限の表示名を取得します。H.

このメソッドは、表示可能な名前を取得しますたとえば、属性名が SE_REMOTE_SHUTDOWN_NAME の場合は、表示可能な名前は、"強制シャット ダウン、リモート システムからです。"。 システム名を取得するには使用[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)します。

##  <a name="getcount"></a>  CTokenPrivileges::GetCount

特権のエントリの数を返します、`CTokenPrivileges`オブジェクト。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>戻り値

含まれる権限の数を返します、`CTokenPrivileges`オブジェクト。

##  <a name="getlength"></a>  CTokenPrivileges::GetLength

長さを返します、`CTokenPrivileges`オブジェクト。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

保持するために必要なバイト数を返します、`TOKEN_PRIVILEGES`構造によって表されます、`CTokenPrivileges`を含むすべての特権エントリが含まれているオブジェクト。

##  <a name="getluidsandattributes"></a>  CTokenPrivileges::GetLuidsAndAttributes

ローカル一意識別子 (Luid) とから属性フラグを取得、`CTokenPrivileges`オブジェクト。

```
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pPrivileges*  
配列を指すポインター [LUID](/windows/desktop/api/winnt/ns-winnt-_luid)オブジェクト。 `CLUIDArray` typedef 定義として`CAtlArray<LUID> CLUIDArray`します。

*pAttributes*  
DWORD オブジェクトの配列へのポインター。 このパラメーターが省略するか、NULL の場合は、属性は取得されません。 `CAttributes` typedef 定義として`CAtlArray <DWORD> CAttributes`します。

### <a name="remarks"></a>Remarks

このメソッドには、すべてに含まれる権限の列挙は、`CTokenPrivileges`トークンのオブジェクトにアクセスし、配列オブジェクトに、それぞれの Luid および (オプション) 属性フラグを配置します。

##  <a name="getnamesandattributes"></a>  CTokenPrivileges::GetNamesAndAttributes

名前と属性のフラグを取得、`CTokenPrivileges`オブジェクト。

```
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pNames*  
配列を指すポインター`CString`オブジェクト。 `CNames` typedef 定義として`CAtlArray <CString> CNames`します。

*pAttributes*  
DWORD オブジェクトの配列へのポインター。 このパラメーターが省略するか、NULL の場合は、属性は取得されません。 `CAttributes` typedef 定義として`CAtlArray <DWORD> CAttributes`します。

### <a name="remarks"></a>Remarks

このメソッドには、すべてに含まれる権限の列挙は、`CTokenPrivileges`オブジェクト、配列オブジェクトに名前と (必要に応じて) 属性フラグを配置することです。

このメソッドは、表示可能な名前ではなく、属性名を取得しますたとえば、属性名が SE_REMOTE_SHUTDOWN_NAME の場合は、システム名は、"を返します。"。 表示可能な名前を取得するメソッドを使用して[CTokenPrivileges::GetDisplayNames](#getdisplaynames)します。

##  <a name="getptoken_privileges"></a>  CTokenPrivileges::GetPTOKEN_PRIVILEGES

ポインターを返します、`TOKEN_PRIVILEGES`構造体。

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>戻り値

ポインターを返します、 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)構造体。

##  <a name="lookupprivilege"></a>  CTokenPrivileges::LookupPrivilege

指定した権限の名前に関連付けられた属性を取得します。

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*  
WINNT で定義されている、権限の名前を指定する null で終わる文字列へのポインター。H ヘッダー ファイルです。 定数 SE_SECURITY_NAME、またはその対応する文字列、"SeSecurityPrivilege"たとえば、このパラメーターを指定可能性があります。

*pdwAttributes*  
属性が格納される変数へのポインター。

### <a name="return-value"></a>戻り値

属性は正常に取得された、false をそれ以外の場合がある場合に true を返します。

##  <a name="operator_eq"></a>  CTokenPrivileges::operator =

代入演算子。

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);  
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rPrivileges*  
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)構造に割り当てる、`CTokenPrivileges`オブジェクト。

*rhs*  
`CTokenPrivileges`オブジェクトに割り当てるオブジェクト。

### <a name="return-value"></a>戻り値

更新された返します`CTokenPrivileges`オブジェクト。

##  <a name="operator_const_token_privileges__star"></a>  CTokenPrivileges::operator const TOKEN_PRIVILEGES \*

値へのポインターにキャスト、`TOKEN_PRIVILEGES`構造体。

```  
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>Remarks

値へのポインターにキャスト、 [TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)構造体。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../visual-cpp-samples.md)   
[TOKEN_PRIVILEGES](/windows/desktop/api/winnt/ns-winnt-_token_privileges)   
[LUID](/windows/desktop/api/winnt/ns-winnt-_luid)   
[LUID_AND_ATTRIBUTES](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes)   
[クラスの概要](../../atl/atl-class-overview.md)   
[セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
