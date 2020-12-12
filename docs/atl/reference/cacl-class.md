---
description: '詳細情報: CAcl クラス'
title: CAcl クラス
ms.date: 11/04/2016
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
ms.openlocfilehash: 60c498336f1bfb5358dd8e5b2eb771456a84ce17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165070"
---
# <a name="cacl-class"></a>CAcl クラス

このクラスは、 `ACL` (アクセス制御リスト) 構造体のラッパーです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
class CAcl
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CAcl:: CAccessMaskArray](#caccessmaskarray)|ACCESS_MASKs の配列。|
|[CAcl:: CAceFlagArray](#caceflagarray)|バイト配列。|
|[CAcl:: CAceTypeArray](#cacetypearray)|バイト配列。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAcl:: CAcl](#cacl)|コンストラクターです。|
|[CAcl:: ~ CAcl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAcl:: GetAceCount](#getacecount)|アクセス制御エントリ (ACE: access control entry) オブジェクトの数を返します。|
|[CAcl:: GetAclEntries](#getaclentries)|オブジェクトからアクセス制御リスト (ACL) エントリを取得し `CAcl` ます。|
|[CAcl:: GetAclEntry](#getaclentry)|オブジェクトのエントリに関するすべての情報を取得し `CAcl` ます。|
|[CAcl:: GetLength](#getlength)|ACL の長さを返します。|
|[CAcl:: GetPACL](#getpacl)|PACL (ACL へのポインター) を返します。|
|[CAcl:: IsEmpty](#isempty)|オブジェクトの `CAcl` エントリをテストします。|
|[CAcl:: IsNull](#isnull)|オブジェクトの状態を返し `CAcl` ます。|
|[CAcl:: RemoveAce](#removeace)|オブジェクトから特定の ACE (アクセス制御エントリ) を削除 `CAcl` します。|
|[CAcl:: RemoveAces](#removeaces)|指定したに適用されるすべての Ace (アクセス制御エントリ) をから削除し `CAcl` `CSid` ます。|
|[CAcl:: SetEmpty](#setempty)|オブジェクトを `CAcl` 空としてマークします。|
|[CAcl:: SetNull](#setnull)|オブジェクトを `CAcl` NULL としてマークします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAcl:: operator const ACL *](#operator_const_acl__star)|オブジェクトを `CAcl` `ACL` 構造体にキャストします。|
|[CAcl:: operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

`ACL`構造体は、ACL (アクセス制御リスト) のヘッダーです。 ACL には、0個以上の [ace](/windows/win32/SecAuthZ/access-control-entries) (アクセス制御エントリ) の連続したリストが含まれます。 ACL 内の個々の Ace には、0 ~ *n-1* の番号が付けられます。ここで、 *n* は acl の ace の数です。 ACL を編集する場合、アプリケーションは、そのインデックスによって ACL 内のアクセス制御エントリ (ACE) を参照します。

次の2つの ACL の種類があります。

- 支出

- システム

随意 ACL は、オブジェクトの所有者またはオブジェクトへの WRITE_DAC アクセスを許可されたユーザーによって制御されます。 これは、特定のユーザーおよびグループがオブジェクトに対して持つことができるアクセス権を指定します。 たとえば、ファイルの所有者は、随意 ACL を使用して、ファイルにアクセスできるユーザーとグループを制御することができます。

また、オブジェクトには、システム管理者によって制御されるシステム ACL の形式で、システムレベルのセキュリティ情報を関連付けることもできます。 システム ACL を使用すると、システム管理者は、オブジェクトへのアクセスの試行を監査できます。

詳細については、Windows SDK の [ACL](/windows/win32/SecAuthZ/access-control-lists) の説明を参照してください。

Windows のアクセス制御モデルの概要については、Windows SDK の「 [Access Control](/windows/win32/SecAuthZ/access-control) 」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="caclcaccessmaskarray"></a><a name="caccessmaskarray"></a> CAcl:: CAccessMaskArray

ACCESS_MASK オブジェクトの配列。

```cpp
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>解説

この typedef は、アクセス制御エントリ (Ace) で使用されるアクセス権を格納するために使用できる配列型を指定します。

## <a name="caclcaceflagarray"></a><a name="caceflagarray"></a> CAcl:: CAceFlagArray

バイト配列。

```cpp
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>解説

この typedef は、アクセス制御エントリ (ACE: access control entry) の型固有のコントロールフラグを定義するために使用される配列型を指定します。 使用可能なフラグの完全な一覧については、 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 定義を参照してください。

## <a name="caclcacetypearray"></a><a name="cacetypearray"></a> CAcl:: CAceTypeArray

バイト配列。

```cpp
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>解説

この typedef は、ACCESS_ALLOWED_ACE_TYPE や ACCESS_DENIED_ACE_TYPE など、アクセス制御エントリ (ACE) オブジェクトの性質を定義するために使用される配列型を指定します。 使用可能な型の完全な一覧については、 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 定義を参照してください。

## <a name="caclcacl"></a><a name="cacl"></a> CAcl:: CAcl

コンストラクターです。

```cpp
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存の `CAcl` オブジェクトです。

### <a name="remarks"></a>解説

オブジェクトは、 `CAcl` 必要に応じて、既存のオブジェクトを使用して作成でき `CAcl` ます。

## <a name="caclcacl"></a><a name="dtor"></a> CAcl:: ~ CAcl

デストラクターです。

```cpp
virtual ~CAcl() throw();
```

### <a name="remarks"></a>解説

デストラクターは、オブジェクトによって取得されたすべてのリソースを解放します。

## <a name="caclgetacecount"></a><a name="getacecount"></a> CAcl:: GetAceCount

アクセス制御エントリ (ACE: access control entry) オブジェクトの数を返します。

```cpp
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>戻り値

オブジェクト内の ACE エントリの数を返し `CAcl` ます。

## <a name="caclgetaclentries"></a><a name="getaclentries"></a> CAcl:: GetAclEntries

オブジェクトからアクセス制御リスト (ACL) エントリを取得し `CAcl` ます。

```cpp
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSids*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクトの配列へのポインター。

*pAccessMasks*<br/>
アクセスマスク。

*pAceTypes*<br/>
アクセス制御エントリ (ACE: access control entry) 型。

*pAceFlags*<br/>
ACE フラグ。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトに格納されているすべての ACE オブジェクトの詳細を配列パラメーターに格納し `CAcl` ます。 特定の配列の詳細が不要な場合は、NULL を使用します。

各配列の内容は互いに対応しています。つまり、配列の最初の要素は `CAccessMaskArray` 配列の最初の要素に対応 `CSidArray` します。

ACE の種類とフラグの詳細については、「 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 」を参照してください。

## <a name="caclgetaclentry"></a><a name="getaclentry"></a> CAcl:: GetAclEntry

アクセス制御リスト (ACL: access control list) のエントリに関するすべての情報を取得します。

```cpp
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得する ACL エントリのインデックス。

*pSid*<br/>
ACL エントリが適用される [CSid](../../atl/reference/csid-class.md) オブジェクト。

*pMask*<br/>
アクセスを許可または拒否するためのアクセス許可を指定するマスク。

*pType*<br/>
ACE 型。

*pFlags*<br/>
ACE フラグ。

*pObjectType*<br/>
オブジェクトの型。 ACE にオブジェクト型が指定されていない場合、または ACE がオブジェクト ACE でない場合は、GUID_NULL に設定されます。

*pInheritedObjectType*<br/>
継承されたオブジェクト型。 継承されたオブジェクト型が ACE に指定されていない場合、または ACE がオブジェクト ACE でない場合は、GUID_NULL に設定されます。

### <a name="remarks"></a>解説

このメソッドは、個々の ACE に関するすべての情報を取得します。この情報は、 [「CAcl:: GetAclEntries](#getaclentries) 」を参照してください。

ACE の種類とフラグの詳細については、「 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 」を参照してください。

## <a name="caclgetlength"></a><a name="getlength"></a> CAcl:: GetLength

アクセス制御リスト (ACL) の長さを返します。

```cpp
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

構造体を保持するために必要なバイト単位の長さを返し `ACL` ます。

## <a name="caclgetpacl"></a><a name="getpacl"></a> CAcl:: GetPACL

アクセス制御リスト (ACL) へのポインターを返します。

```cpp
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>戻り値

構造体へのポインターを返し `ACL` ます。

## <a name="caclisempty"></a><a name="isempty"></a> CAcl:: IsEmpty

オブジェクトの `CAcl` エントリをテストします。

```cpp
bool IsEmpty() const throw();
```

### <a name="remarks"></a>解説

`CAcl`オブジェクトが NULL ではなく、エントリが含まれていない場合は TRUE を返します。 `CAcl`オブジェクトが NULL であるか、またはエントリが少なくとも1つ含まれている場合は、FALSE を返します。

## <a name="caclisnull"></a><a name="isnull"></a> CAcl:: IsNull

オブジェクトの状態を返し `CAcl` ます。

```cpp
bool IsNull() const throw();
```

### <a name="return-value"></a>戻り値

`CAcl`オブジェクトが NULL の場合は TRUE、それ以外の場合は FALSE を返します。

## <a name="cacloperator-const-acl-"></a><a name="operator_const_acl__star"></a> CAcl:: operator const ACL *

オブジェクトを `CAcl` `ACL` (アクセス制御リスト) 構造体にキャストします。

```cpp
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>解説

構造体のアドレスを返し `ACL` ます。

## <a name="cacloperator-"></a><a name="operator_eq"></a> CAcl:: operator =

代入演算子。

```cpp
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CAcl`既存のオブジェクトに割り当てる。

### <a name="return-value"></a>戻り値

更新されたオブジェクトへの参照を返し `CAcl` ます。

## <a name="caclremoveace"></a><a name="removeace"></a> CAcl:: RemoveAce

オブジェクトから特定の ACE (アクセス制御エントリ) を削除 `CAcl` します。

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE エントリのインデックス。

### <a name="remarks"></a>解説

このメソッドは、 [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat)から派生しています。

## <a name="caclremoveaces"></a><a name="removeaces"></a> CAcl:: RemoveAces

指定したに適用される alls Ace (アクセス制御エントリ) をから削除し `CAcl` `CSid` ます。

```cpp
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
`CSid` オブジェクトへの参照です。

## <a name="caclsetempty"></a><a name="setempty"></a> CAcl:: SetEmpty

オブジェクトを `CAcl` 空としてマークします。

```cpp
void SetEmpty() throw();
```

### <a name="remarks"></a>解説

は、 `CAcl` empty または NULL に設定できます。この2つの状態は個別です。

## <a name="caclsetnull"></a><a name="setnull"></a> CAcl:: SetNull

オブジェクトを `CAcl` NULL としてマークします。

```cpp
void SetNull() throw();
```

### <a name="remarks"></a>解説

は、 `CAcl` empty または NULL に設定できます。この2つの状態は個別です。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
