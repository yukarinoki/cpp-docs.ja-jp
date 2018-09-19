---
title: CAcl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db7903dccfd851bb4bf76f1990424f887686d344
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070107"
---
# <a name="cacl-class"></a>CAcl クラス

このクラスは、のラッパー、 `ACL` (アクセス制御リスト) の構造体。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAcl
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CAcl::CAccessMaskArray](#caccessmaskarray)|ACCESS_MASKs の配列。|
|[CAcl::CAceFlagArray](#caceflagarray)|バイト配列。|
|[CAcl::CAceTypeArray](#cacetypearray)|バイト配列。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|コンストラクターです。|
|[CAcl:: ~ CAcl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAcl::GetAceCount](#getacecount)|アクセス制御の数のエントリ (ACE) オブジェクトを返します。|
|[CAcl::GetAclEntries](#getaclentries)|アクセス制御リスト (ACL) エントリを取得、`CAcl`オブジェクト。|
|[CAcl::GetAclEntry](#getaclentry)|すべてのエントリに関する情報の取得、`CAcl`オブジェクト。|
|[CAcl::GetLength](#getlength)|ACL の長さを返します。|
|[CAcl::GetPACL](#getpacl)|PACL (ACL へのポインター) を返します。|
|[CAcl::IsEmpty](#isempty)|テスト、`CAcl`エントリ オブジェクト。|
|[CAcl::IsNull](#isnull)|状態を返し、`CAcl`オブジェクト。|
|[CAcl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) を削除、`CAcl`オブジェクト。|
|[CAcl::RemoveAces](#removeaces)|すべての Ace (アクセス制御エントリ) を削除、`CAcl`に適用される、指定された`CSid`します。|
|[CAcl::SetEmpty](#setempty)|マーク、`CAcl`空としてオブジェクトします。|
|[CAcl::SetNull](#setnull)|マーク、`CAcl`オブジェクトを NULL として。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAcl::operator const ACL *](#operator_const_acl__star)|キャストを`CAcl`オブジェクトを`ACL`構造体。|
|[CAcl::operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>Remarks

`ACL`構造体が ACL (アクセス制御リスト) のヘッダー。 ACL には、連続した 0 個以上の一覧が含まれています。 [Ace](/windows/desktop/SecAuthZ/access-control-entries) (アクセス制御エントリ)。 ACL 内の個々 の Ace の番号が 0 から*n-1*ここで、 *n* ACL に Ace の数です。 ACL を編集するには、アプリケーションはそのインデックスを使用して、ACL 内でアクセス制御エントリ (ACE) を表します。

2 つの ACL の種類があります。

- 随意

- システム

随意 ACL は、オブジェクトの所有者によって制御されます。 または、オブジェクトに対する WRITE_DAC アクセス許可を与えられたユーザー。 これは、アクセスの特定のユーザーとグループ オブジェクトを持つことができますを指定します。 たとえば、ファイルの所有者では、コントロールできるユーザーとグループ、およびファイルへのアクセスを持つことはできませんを随意 ACL を使用できます。

オブジェクトには、システム レベルのセキュリティ情報がシステムには、システム管理者によって制御される ACL の形式で、それに関連付けられていることもできます。 システムの ACL は、オブジェクトにアクセスするすべての試行を監査するシステム管理者に許可できます。

詳細については、次を参照してください。、 [ACL](/windows/desktop/SecAuthZ/access-control-lists) Windows SDK で説明します。

Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity.h

##  <a name="caccessmaskarray"></a>  CAcl::CAccessMaskArray

ACCESS_MASK オブジェクトの配列。

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>Remarks

この typedef は、アクセス制御エントリ (Ace) で使用されるアクセス権を格納するために使用する配列の型を指定します。

##  <a name="caceflagarray"></a>  CAcl::CAceFlagArray

バイト配列。

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>Remarks

この typedef は、アクセス制御エントリ (ACE) の種類に固有の制御フラグを定義するために使用する配列の型を指定します。 参照してください、 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header)可能なフラグの完全な一覧を定義します。

##  <a name="cacetypearray"></a>  CAcl::CAceTypeArray

バイト配列。

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>Remarks

この typedef は、ACCESS_ALLOWED_ACE_TYPE または ACCESS_DENIED_ACE_TYPE など、アクセス制御エントリ (ACE) オブジェクトの種類を定義するために使用する配列の型を指定します。 参照してください、 [ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header)使用可能な型の完全な一覧を定義します。

##  <a name="cacl"></a>  CAcl::CAcl

コンストラクターです。

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存の `CAcl` オブジェクト。

### <a name="remarks"></a>Remarks

`CAcl`オブジェクトをオプションで作成した既存`CAcl`オブジェクト。

##  <a name="dtor"></a>  CAcl:: ~ CAcl

デストラクターです。

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>Remarks

デストラクターは、オブジェクトが取得したすべてのリソースを解放します。

##  <a name="getacecount"></a>  CAcl::GetAceCount

アクセス制御の数のエントリ (ACE) オブジェクトを返します。

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>戻り値

ACE のエントリの数を返します、`CAcl`オブジェクト。

##  <a name="getaclentries"></a>  CAcl::GetAclEntries

アクセス制御リスト (ACL) エントリを取得、`CAcl`オブジェクト。

```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSids*<br/>
配列へのポインター [CSid](../../atl/reference/csid-class.md)オブジェクト。

*pAccessMasks*<br/>
アクセス マスク。

*pAceTypes*<br/>
アクセス制御エントリ (ACE) の型。

*pAceFlags*<br/>
ACE フラグを設定します。

### <a name="remarks"></a>Remarks

このメソッドによって、配列パラメーターに含まれているすべての ACE オブジェクトの詳細を`CAcl`オブジェクト。 その特定の配列の詳細が必要でない場合は、NULL を使用します。

つまりの最初の要素の互いに、各配列の内容が対応、`CAccessMaskArray`の最初の要素に対応する配列、`CSidArray`配列、という具合です。

参照してください[ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) ACE 型とフラグの詳細についてはします。

##  <a name="getaclentry"></a>  CAcl::GetAclEntry

すべてのアクセス制御リスト (ACL) 内のエントリに関する情報を取得します。

```
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
取得する ACL エントリのインデックスです。

*pSid*<br/>
[CSid](../../atl/reference/csid-class.md) ACL エントリを適用するオブジェクトします。

*pMask*<br/>
アクセス許可または拒否するアクセス許可を指定するマスク。

*p 入力してください。*<br/>
ACE の種類。

*pFlags*<br/>
ACE フラグを設定します。

*pObjectType*<br/>
オブジェクトの型。 ACE がオブジェクトの ACE ではない場合、ACE のオブジェクトの種類が指定されていない場合または GUID_ に設定されます。

*pInheritedObjectType*<br/>
継承されたオブジェクトの種類。 ACE がオブジェクトの ACE ではない場合、ACE の継承されたオブジェクトの種類が指定されていない場合または GUID_ に設定されます。

### <a name="remarks"></a>Remarks

このメソッドは、個々 の ACE のより多くの情報を提供することに関する情報がすべては取得[CAcl::GetAclEntries](#getaclentries)単独で使用できるようにします。

参照してください[ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header) ACE 型とフラグの詳細についてはします。

##  <a name="getlength"></a>  CAcl::GetLength

アクセス制御リスト (ACL) の長さを返します。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

保持するために必要なバイト数で、必要な長さを返します、`ACL`構造体。

##  <a name="getpacl"></a>  CAcl::GetPACL

アクセス制御リスト (ACL) へのポインターを返します。

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>戻り値

ポインターを返します、`ACL`構造体。

##  <a name="isempty"></a>  CAcl::IsEmpty

テスト、`CAcl`エントリ オブジェクト。

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>Remarks

True の場合、`CAcl`オブジェクトが NULL でないと、エントリが含まれていません。 場合は FALSE を返します、`CAcl`オブジェクトが NULL であるか、または少なくとも 1 つのエントリが含まれています。

##  <a name="isnull"></a>  CAcl::IsNull

状態を返し、`CAcl`オブジェクト。

```
bool IsNull() const throw();
```

### <a name="return-value"></a>戻り値

True の場合、`CAcl`オブジェクトが null の場合、FALSE それ以外の場合。

##  <a name="operator_const_acl__star"></a>  CAcl::operator const ACL *

キャストを`CAcl`オブジェクトを`ACL`(アクセス制御リスト) の構造体。

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>Remarks

アドレスを返して、`ACL`構造体。

##  <a name="operator_eq"></a>  CAcl::operator =

代入演算子。

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`CAcl`を既存のオブジェクトを割り当てる。

### <a name="return-value"></a>戻り値

更新されたへの参照を返します`CAcl`オブジェクト。

##  <a name="removeace"></a>  CAcl::RemoveAce

特定の ACE (アクセス制御エントリ) を削除、`CAcl`オブジェクト。

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE のエントリのインデックスです。

### <a name="remarks"></a>Remarks

このメソッドはから派生した[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)します。

##  <a name="removeaces"></a>  CAcl::RemoveAces

Alls Ace (アクセス制御エントリ) を削除、`CAcl`に適用される、指定された`CSid`します。

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
`CSid` オブジェクトへの参照。

##  <a name="setempty"></a>  CAcl::SetEmpty

マーク、`CAcl`空としてオブジェクトします。

```
void SetEmpty() throw();
```

### <a name="remarks"></a>Remarks

`CAcl`空または NULL に設定できます。 2 つの状態は異なります。

##  <a name="setnull"></a>  CAcl::SetNull

マーク、`CAcl`オブジェクトを NULL として。

```
void SetNull() throw();
```

### <a name="remarks"></a>Remarks

`CAcl`空または NULL に設定できます。 2 つの状態は異なります。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
