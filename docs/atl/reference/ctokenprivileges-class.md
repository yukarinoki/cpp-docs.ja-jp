---
description: '詳細情報: CTokenPrivileges クラス'
title: CTokenPrivileges クラス
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
ms.openlocfilehash: 22953c0d2aa8c4fa7dd0b79b001e46797bd3ca25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140310"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges クラス

このクラスは、構造体のラッパーです `TOKEN_PRIVILEGES` 。

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
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|コンストラクターです。|
|[CTokenPrivileges:: ~ CTokenPrivileges](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTokenPrivileges:: Add](#add)|オブジェクトに1つ以上の特権を追加し `CTokenPrivileges` ます。|
|[CTokenPrivileges::D e)](#delete)|オブジェクトから特権を削除 `CTokenPrivileges` します。|
|[CTokenPrivileges::D eleteAll](#deleteall)|オブジェクトからすべての特権を削除 `CTokenPrivileges` します。|
|[CTokenPrivileges:: GetCount](#getcount)|オブジェクト内の特権エントリの数を返し `CTokenPrivileges` ます。|
|[CTokenPrivileges:: GetDisplayNames](#getdisplaynames)|オブジェクトに格納されている特権の表示名を取得 `CTokenPrivileges` します。|
|[CTokenPrivileges:: GetLength](#getlength)|`TOKEN_PRIVILEGES`オブジェクトによって表される構造体を保持するために必要なバイト単位のバッファーサイズを返し `CTokenPrivileges` ます。|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|オブジェクトからローカル一意識別子 (Luid) と属性フラグを取得し `CTokenPrivileges` ます。|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|オブジェクトから特権名と属性フラグを取得し `CTokenPrivileges` ます。|
|[CTokenPrivileges:: GetPTOKEN_PRIVILEGES](#getptoken_privileges)|構造体へのポインターを返し `TOKEN_PRIVILEGES` ます。|
|[CTokenPrivileges:: LookupPrivilege](#lookupprivilege)|指定された特権名に関連付けられている属性を取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CTokenPrivileges:: operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|構造体へのポインターに値をキャスト `TOKEN_PRIVILEGES` します。|
|[CTokenPrivileges:: operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

[アクセストークン](/windows/win32/SecAuthZ/access-tokens)は、プロセスまたはスレッドのセキュリティコンテキストを記述するオブジェクトで、Windows システムにログオンした各ユーザーに割り当てられます。

アクセストークンは、各ユーザーに付与されるさまざまなセキュリティ特権を記述するために使用されます。 特権は、ローカル一意識別子 ( [LUID](/windows/win32/api/winnt/ns-winnt-luid)) と記述子文字列と呼ばれる64ビット番号で構成されます。

`CTokenPrivileges`クラスは[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)構造体のラッパーであり、0個以上の特権を含みます。 特権は、指定されたクラスメソッドを使用して追加、削除、または照会できます。

Windows のアクセス制御モデルの概要については、Windows SDK の「 [Access Control](/windows/win32/SecAuthZ/access-control) 」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="ctokenprivilegesadd"></a><a name="add"></a> CTokenPrivileges:: Add

アクセストークンオブジェクトに1つ以上の特権を追加し `CTokenPrivileges` ます。

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*<br/>
権限の名前を指定する null で終わる文字列へのポインター (WINNT で定義)。H ヘッダーファイル。

*bEnable*<br/>
True の場合、特権が有効になります。 False の場合、特権は無効になります。

*rPrivileges*<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)構造体への参照。 特権および属性は、この構造からコピーされ、オブジェクトに追加され `CTokenPrivileges` ます。

### <a name="return-value"></a>戻り値

このメソッドの最初の形式は、特権が正常に追加された場合は true、それ以外の場合は false を返します。

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a> CTokenPrivileges::CTokenPrivileges

コンストラクターです。

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CTokenPrivileges`新しいオブジェクトに割り当てるオブジェクト。

*rPrivileges*<br/>
新しいオブジェクトに割り当てる [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 構造体 `CTokenPrivileges` 。

### <a name="remarks"></a>解説

オブジェクトは、 `CTokenPrivileges` 必要に応じて、構造体または以前に定義したオブジェクトを使用して作成でき `TOKEN_PRIVILEGES` `CTokenPrivileges` ます。

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a> CTokenPrivileges:: ~ CTokenPrivileges

デストラクターです。

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>解説

デストラクターは、割り当てられたすべてのリソースを解放します。

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a> CTokenPrivileges::D e)

アクセストークンオブジェクトから特権を削除 `CTokenPrivileges` します。

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*<br/>
権限の名前を指定する null で終わる文字列へのポインター (WINNT で定義)。H ヘッダーファイル。 たとえば、このパラメーターでは、定数 SE_SECURITY_NAME、またはそれに対応する文字列 "SeSecurityPrivilege" を指定できます。

### <a name="return-value"></a>戻り値

特権が正常に削除された場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

このメソッドは、制限付きトークンを作成するためのツールとして役立ちます。

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a> CTokenPrivileges::D eleteAll

アクセストークンオブジェクトからすべての特権を削除 `CTokenPrivileges` します。

```cpp
void DeleteAll() throw();
```

### <a name="remarks"></a>解説

アクセストークンオブジェクトに格納されているすべての特権を削除 `CTokenPrivileges` します。

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a> CTokenPrivileges:: GetDisplayNames

アクセストークンオブジェクトに格納されている特権の表示名を取得 `CTokenPrivileges` します。

```cpp
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pDisplayNames*<br/>
`CString` オブジェクトの配列へのポインター。 `CNames` は typedef として定義されます `CTokenPrivileges::CAtlArray<CString>` 。

### <a name="remarks"></a>解説

パラメーターは、 `pDisplayNames` オブジェクトに格納されて `CString` いる特権に対応する表示名を受け取るオブジェクトの配列へのポインターです `CTokenPrivileges` 。 このメソッドは、WINNT.H の [定義された特権] セクションで指定された特権の表示名のみを取得します。

このメソッドは、使用可能な名前を取得します。たとえば、属性名が SE_REMOTE_SHUTDOWN_NAME の場合、"リモートシステムからの強制シャットダウン" という名前の名前が付いています。 システム名を取得するには、 [CTokenPrivileges:: GetNamesAndAttributes](#getnamesandattributes)を使用します。

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a> CTokenPrivileges:: GetCount

オブジェクト内の特権エントリの数を返し `CTokenPrivileges` ます。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに格納されている特権の数を返し `CTokenPrivileges` ます。

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a> CTokenPrivileges:: GetLength

オブジェクトの長さを返し `CTokenPrivileges` ます。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトによって表される構造体を保持するために必要なバイト数を返し `TOKEN_PRIVILEGES` `CTokenPrivileges` ます。格納されているすべての特権エントリを含みます。

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a> CTokenPrivileges::GetLuidsAndAttributes

オブジェクトからローカル一意識別子 (Luid) と属性フラグを取得し `CTokenPrivileges` ます。

```cpp
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pPrivileges*<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid)オブジェクトの配列へのポインター。 `CLUIDArray` は、として定義される typedef `CAtlArray<LUID> CLUIDArray` です。

*pAttributes*<br/>
DWORD オブジェクトの配列へのポインター。 このパラメーターを省略した場合、または NULL の場合、属性は取得されません。 `CAttributes` は、として定義される typedef `CAtlArray <DWORD> CAttributes` です。

### <a name="remarks"></a>解説

このメソッドは、アクセストークンオブジェクトに含まれているすべての特権 `CTokenPrivileges` を列挙し、個々の luid と (必要に応じて) 属性フラグを配列オブジェクトに配置します。

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a> CTokenPrivileges::GetNamesAndAttributes

オブジェクトから名前と属性フラグを取得し `CTokenPrivileges` ます。

```cpp
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pNames*<br/>
オブジェクトの配列へのポインター `CString` 。 `CNames` は、として定義される typedef `CAtlArray <CString> CNames` です。

*pAttributes*<br/>
DWORD オブジェクトの配列へのポインター。 このパラメーターを省略した場合、または NULL の場合、属性は取得されません。 `CAttributes` は、として定義される typedef `CAtlArray <DWORD> CAttributes` です。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトに含まれているすべての特権を列挙し `CTokenPrivileges` 、名前と (オプションで) 属性フラグを配列オブジェクトに格納します。

このメソッドは、名前を指定した名前ではなく、属性名を取得します。たとえば、属性名が SE_REMOTE_SHUTDOWN_NAME の場合、システム名は "Seremotesを使用する特権" になります。 名前を確認できる名前を取得するには、 [CTokenPrivileges:: GetDisplayNames](#getdisplaynames)メソッドを使用します。

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a> CTokenPrivileges:: GetPTOKEN_PRIVILEGES

構造体へのポインターを返し `TOKEN_PRIVILEGES` ます。

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>戻り値

[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)構造体へのポインターを返します。

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a> CTokenPrivileges:: LookupPrivilege

指定された特権名に関連付けられている属性を取得します。

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pszPrivilege*<br/>
権限の名前を指定する null で終わる文字列へのポインター (WINNT で定義)。H ヘッダーファイル。 たとえば、このパラメーターでは、定数 SE_SECURITY_NAME、またはそれに対応する文字列 "SeSecurityPrivilege" を指定できます。

*pdwAttributes*<br/>
属性を受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

属性が正常に取得された場合は true、それ以外の場合は false を返します。

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a> CTokenPrivileges:: operator =

代入演算子。

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rPrivileges*<br/>
オブジェクトに割り当てる [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 構造体 `CTokenPrivileges` 。

*rhs*<br/>
`CTokenPrivileges`オブジェクトに割り当てるオブジェクト。

### <a name="return-value"></a>戻り値

更新されたオブジェクトを返し `CTokenPrivileges` ます。

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a> CTokenPrivileges:: operator const TOKEN_PRIVILEGES \*

構造体へのポインターに値をキャスト `TOKEN_PRIVILEGES` します。

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>解説

値を [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 構造体へのポインターにキャストします。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
