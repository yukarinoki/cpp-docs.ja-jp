---
title: クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 75c09f723860540aa54cf3744cde7e61d9202f79
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747362"
---
# <a name="ctokenprivileges-class"></a>クラス

このクラスは構造体のラッパー`TOKEN_PRIVILEGES`です。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CTokenPrivileges
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次のサービス::C トークンの特権](#ctokenprivileges)|コンストラクターです。|
|[次のサービス::~Cトークン特典](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の項目を追加します。](#add)|オブジェクトに 1 つ以上`CTokenPrivileges`の特権を追加します。|
|[Cトークン特典::D](#delete)|オブジェクトから特権を`CTokenPrivileges`削除します。|
|[:Dエレテオール](#deleteall)|オブジェクトからすべての特権を`CTokenPrivileges`削除します。|
|[を取得します。](#getcount)|オブジェクト内の特権エントリの数を`CTokenPrivileges`返します。|
|[を取得します。](#getdisplaynames)|オブジェクトに含まれる特権の表示名を`CTokenPrivileges`取得します。|
|[を取得します。](#getlength)|オブジェクトによって表される構造体を保持するために必要な`TOKEN_PRIVILEGES`バッファー サイズをバイト単位で返します。 `CTokenPrivileges`|
|[次の属性を取得します。](#getluidsandattributes)|`CTokenPrivileges`ローカル一意識別子 (LUID) と属性フラグをオブジェクトから取得します。|
|[次の要素を取得します。](#getnamesandattributes)|オブジェクトから特権名と属性フラグを`CTokenPrivileges`取得します。|
|[GetPTOKEN_PRIVILEGES](#getptoken_privileges)|構造体へのポインターを`TOKEN_PRIVILEGES`返します。|
|[次の特権を取得します。](#lookupprivilege)|指定された特権名に関連付けられた属性を取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[TOKEN_PRIVILEGES演算子の定数を指定します。](#operator_const_token_privileges__star)|構造体へのポインターに値をキャストします`TOKEN_PRIVILEGES`。|
|[次の操作を行います。](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

[アクセス トークン](/windows/win32/SecAuthZ/access-tokens)は、プロセスまたはスレッドのセキュリティ コンテキストを記述するオブジェクトで、Windows システムにログオンしている各ユーザーに割り当てられます。

アクセス トークンは、各ユーザーに付与されるさまざまなセキュリティ特権を記述するために使用されます。 特権は、ローカル一意識別子 ( [LUID](/windows/win32/api/winnt/ns-winnt-luid)) と呼ばれる 64 ビットの数値と記述子文字列で構成されます。

この`CTokenPrivileges`クラスは[、TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)構造体のラッパーであり、0 以上の特権を含みます。 指定されたクラス メソッドを使用して、特権を追加、削除、または照会できます。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="ctokenprivilegesadd"></a><a name="add"></a>次の項目を追加します。

アクセス トークン オブジェクトに`CTokenPrivileges`1 つ以上の特権を追加します。

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>パラメーター

*プリビレッジ*<br/>
特権の名前を指定する、WINNT で定義されている NULL で終わる文字列へのポインター。H ヘッダー ファイル。

*b 有効にする*<br/>
true の場合、特権は有効になります。 false の場合、特権は無効になります。

*r特典*<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)構造体への参照。 特権と属性は、この構造体からコピーされ、オブジェクトに追加`CTokenPrivileges`されます。

### <a name="return-value"></a>戻り値

このメソッドの最初の形式は、特権が正常に追加された場合は true を返し、それ以外の場合は false を返します。

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a>次のサービス::C トークンの特権

コンストラクターです。

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
新`CTokenPrivileges`しいオブジェクトに割り当てるオブジェクト。

*r特典*<br/>
新[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)しい`CTokenPrivileges`オブジェクトに割り当てるTOKEN_PRIVILEGES構造。

### <a name="remarks"></a>解説

オブジェクト`CTokenPrivileges`は、必要に応じて、構造体`TOKEN_PRIVILEGES`または定義済みの`CTokenPrivileges`オブジェクトを使用して作成できます。

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a>次のサービス::~Cトークン特典

デストラクターです。

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>解説

デストラクタは、割り当てられたすべてのリソースを解放します。

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a>Cトークン特典::D

アクセス トークン オブジェクトから`CTokenPrivileges`特権を削除します。

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>パラメーター

*プリビレッジ*<br/>
特権の名前を指定する、WINNT で定義されている NULL で終わる文字列へのポインター。H ヘッダー ファイル。 たとえば、このパラメーターでは、定数SE_SECURITY_NAME、または対応する文字列 "SeSecurityPrivilege" を指定できます。

### <a name="return-value"></a>戻り値

特権が正常に削除された場合は true を返し、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

このメソッドは、制限付きトークンを作成するためのツールとして役立ちます。

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a>:Dエレテオール

アクセス トークン オブジェクトから`CTokenPrivileges`すべての特権を削除します。

```cpp
void DeleteAll() throw();
```

### <a name="remarks"></a>解説

アクセス トークン オブジェクトに含`CTokenPrivileges`まれるすべての特権を削除します。

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a>を取得します。

アクセス トークン オブジェクトに含まれる特権の`CTokenPrivileges`表示名を取得します。

```cpp
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>パラメーター

*表示名*<br/>
`CString` オブジェクトの配列へのポインター。 `CNames`は、タイプ定義として定義されます`CTokenPrivileges::CAtlArray<CString>`。

### <a name="remarks"></a>解説

パラメーター`pDisplayNames`は、オブジェクトに`CString`含まれる特権に対応する表示名を受け取るオブジェクトの配列へのポインターです`CTokenPrivileges`。 このメソッドは、WINNT の 「定義された特権」セクションで指定された特権のみの表示名を取得します。H。

このメソッドは、表示可能な名前を取得 SE_REMOTE_SHUTDOWN_NAMEします。 システム名を取得するには、[次の値](#getnamesandattributes)を使用します。

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a>を取得します。

オブジェクト内の特権エントリの数を`CTokenPrivileges`返します。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに含まれる特権の数を`CTokenPrivileges`返します。

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a>を取得します。

`CTokenPrivileges`オブジェクトの長さを返します。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに含まれるすべての特権エントリを含`TOKEN_PRIVILEGES`む、オブジェクトによって`CTokenPrivileges`表される構造体を保持するために必要なバイト数を返します。

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a>次の属性を取得します。

`CTokenPrivileges`ローカル一意識別子 (LUID) と属性フラグをオブジェクトから取得します。

```cpp
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*特権*<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid)オブジェクトの配列へのポインター。 `CLUIDArray`は、 として定義された`CAtlArray<LUID> CLUIDArray`型定義です。

*属性*<br/>
DWORD オブジェクトの配列へのポインター。 このパラメーターを省略するか NULL にすると、属性は取得されません。 `CAttributes`は、 として定義された`CAtlArray <DWORD> CAttributes`型定義です。

### <a name="remarks"></a>解説

このメソッドは、アクセス トークン オブジェクトに含`CTokenPrivileges`まれるすべての特権を列挙し、個々の LUID と (オプションで) 属性フラグを配列オブジェクトに配置します。

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a>次の要素を取得します。

オブジェクトから名前と属性フラグを`CTokenPrivileges`取得します。

```cpp
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*p名前*<br/>
オブジェクトの`CString`配列へのポインター。 `CNames`は、 として定義された`CAtlArray <CString> CNames`型定義です。

*属性*<br/>
DWORD オブジェクトの配列へのポインター。 このパラメーターを省略するか NULL にすると、属性は取得されません。 `CAttributes`は、 として定義された`CAtlArray <DWORD> CAttributes`型定義です。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトに含まれるすべての特権を`CTokenPrivileges`列挙し、名前と (オプションで) 属性フラグを配列オブジェクトに配置します。

このメソッドは、表示可能な名前ではなく SE_REMOTE_SHUTDOWN_NAME属性名を取得します。 表示可能な名前を取得するには、メソッド[CTokenPrivileges::GetDisplayNames](#getdisplaynames)を使用します。

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a>GetPTOKEN_PRIVILEGES

構造体へのポインターを`TOKEN_PRIVILEGES`返します。

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>戻り値

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)構造体へのポインターを返します。

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a>次の特権を取得します。

指定された特権名に関連付けられた属性を取得します。

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*プリビレッジ*<br/>
特権の名前を指定する、WINNT で定義されている NULL で終わる文字列へのポインター。H ヘッダー ファイル。 たとえば、このパラメーターでは、定数SE_SECURITY_NAME、または対応する文字列 "SeSecurityPrivilege" を指定できます。

*属性*<br/>
属性を受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

属性が正常に取得された場合は true を返し、それ以外の場合は false を返します。

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a>次の操作を行います。

代入演算子。

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*r特典*<br/>
オブジェクトに割り当てるTOKEN_PRIVILEGES構造。 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) `CTokenPrivileges`

*rhs*<br/>
`CTokenPrivileges`オブジェクトに割り当てるオブジェクト。

### <a name="return-value"></a>戻り値

更新された`CTokenPrivileges`オブジェクトを返します。

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a>TOKEN_PRIVILEGESする演算子\*

構造体へのポインターに値をキャストします`TOKEN_PRIVILEGES`。

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>解説

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)構造体へのポインターに値をキャストします。

## <a name="see-also"></a>関連項目

[セキュリティサンプル](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[Luid](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
