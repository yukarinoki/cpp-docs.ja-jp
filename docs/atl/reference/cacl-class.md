---
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
ms.openlocfilehash: 458f7cd50462a145d005f3f81d87cc06fc7e01b1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748780"
---
# <a name="cacl-class"></a>CAcl クラス

このクラスは`ACL`、(アクセス制御リスト) 構造体のラッパーです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAcl
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CAcl::コアクセスマスクアレイ](#caccessmaskarray)|ACCESS_MASKsの配列。|
|[CAcl::エースフラッグアレイ](#caceflagarray)|BYE の配列。|
|[CAcl::エースタイプアレイ](#cacetypearray)|BYE の配列。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAcl::CAcl](#cacl)|コンストラクターです。|
|[CAcl::~CAcl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAcl::ゲットエースカウント](#getacecount)|アクセス制御エントリ (ACE) オブジェクトの数を返します。|
|[CAcl::ゲットアクエントリ](#getaclentries)|オブジェクトからアクセス制御リスト (ACL) エントリを`CAcl`取得します。|
|[CAcl::ゲットアクエントリ](#getaclentry)|オブジェクト内のエントリに関するすべての情報を`CAcl`取得します。|
|[CAcl::ゲットレングス](#getlength)|ACL の長さを返します。|
|[CAcl::ゲットパック](#getpacl)|PACL (ACL へのポインタ) を返します。|
|[CAcl::IsEmpty](#isempty)|オブジェクトの`CAcl`エントリをテストします。|
|[CAcl::IsNull](#isnull)|オブジェクトのステータスを`CAcl`返します。|
|[CAcl::除去エース](#removeace)|`CAcl`オブジェクトから特定の ACE (アクセス制御エントリ) を削除します。|
|[CAcl::除去エース](#removeaces)|指定`CAcl``CSid`された に適用されるすべての ACE (アクセス制御エントリ) を から削除します。|
|[CAcl::セットEmpty](#setempty)|オブジェクトを`CAcl`空としてマークします。|
|[CAcl::セットヌル](#setnull)|オブジェクトを`CAcl`NULL としてマークします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAcl::演算子のコンスト ACL *](#operator_const_acl__star)|オブジェクトを`CAcl`構造体にキャストします`ACL`。|
|[CAcl::演算子 =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

構造`ACL`は ACL (アクセス制御リスト) のヘッダーです。 ACL には、0 個以上の[ACE](/windows/win32/SecAuthZ/access-control-entries) (アクセス制御エントリ) の順次リストが含まれます。 ACL 内の個々の ACE には 0 から*n-1*までの*番号が付*けられます。 ACL を編集する場合、アプリケーションは ACL 内のアクセス制御エントリ(ACE)をインデックスで参照します。

ACL には次の 2 つのタイプがあります。

- 随意

- システム

随意 ACL は、オブジェクトの所有者、またはオブジェクトへのアクセスを付与WRITE_DACユーザーによって制御されます。 これは、特定のユーザーおよびグループがオブジェクトに対して持つことができるアクセスを指定します。 たとえば、ファイルの所有者は、任意の ACL を使用して、ファイルへのアクセスを許可するユーザーとグループを制御できます。

オブジェクトは、システム管理者によって制御されるシステム ACL の形式で、システムレベルのセキュリティ情報を関連付けることもできます。 システム ACL を使用すると、システム管理者はオブジェクトへのアクセスを試みて監査できます。

詳細については、Windows SDK の[ACL](/windows/win32/SecAuthZ/access-control-lists)の説明を参照してください。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="caclcaccessmaskarray"></a><a name="caccessmaskarray"></a>CAcl::コアクセスマスクアレイ

ACCESS_MASKオブジェクトの配列。

```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```

### <a name="remarks"></a>解説

この typedef は、アクセス制御エントリ (ACE) で使用されるアクセス権を格納するために使用できる配列の種類を指定します。

## <a name="caclcaceflagarray"></a><a name="caceflagarray"></a>CAcl::エースフラッグアレイ

BYE の配列。

```
typedef CAtlArray<BYTE> CAceFlagArray;
```

### <a name="remarks"></a>解説

この typedef は、アクセス制御エントリ (ACE) の型固有の制御フラグを定義するために使用される配列型を指定します。 可能なフラグの完全なリストについては[、ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header)定義を参照してください。

## <a name="caclcacetypearray"></a><a name="cacetypearray"></a>CAcl::エースタイプアレイ

BYE の配列。

```
typedef CAtlArray<BYTE> CAceTypeArray;
```

### <a name="remarks"></a>解説

この typedef は、ACCESS_ALLOWED_ACE_TYPEやACCESS_DENIED_ACE_TYPEなどのアクセス制御エントリ (ACE) オブジェクトの性質を定義するために使用される配列型を指定します。 可能な型の完全なリストについては[、ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header)定義を参照してください。

## <a name="caclcacl"></a><a name="cacl"></a>CAcl::CAcl

コンストラクターです。

```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存の `CAcl` オブジェクトです。

### <a name="remarks"></a>解説

オブジェクト`CAcl`は、既存`CAcl`のオブジェクトを使用して任意で作成できます。

## <a name="caclcacl"></a><a name="dtor"></a>CAcl::~CAcl

デストラクターです。

```
virtual ~CAcl() throw();
```

### <a name="remarks"></a>解説

デストラクターは、オブジェクトによって取得されたリソースを解放します。

## <a name="caclgetacecount"></a><a name="getacecount"></a>CAcl::ゲットエースカウント

アクセス制御エントリ (ACE) オブジェクトの数を返します。

```
virtual UINT GetAceCount() const throw() = 0;
```

### <a name="return-value"></a>戻り値

オブジェクト内の ACE エントリの`CAcl`数を返します。

## <a name="caclgetaclentries"></a><a name="getaclentries"></a>CAcl::ゲットアクエントリ

オブジェクトからアクセス制御リスト (ACL) エントリを`CAcl`取得します。

```cpp
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```

### <a name="parameters"></a>パラメーター

*pSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクトの配列へのポインター。

*アクセスマスク*<br/>
アクセス マスク。

*pAceTypes*<br/>
アクセス制御エントリ (ACE) の種類。

*エースフラグ*<br/>
ACE フラグ。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトに含まれるすべての ACE オブジェクトの詳細を配列`CAcl`パラメーターに格納します。 特定の配列の詳細が必要ない場合は、NULL を使用します。

各配列の内容は互いに対応し合い、配列の最初の要素は`CAccessMaskArray``CSidArray`配列の最初の要素に対応します。

ACE の種類とフラグの詳細については[、ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header)を参照してください。

## <a name="caclgetaclentry"></a><a name="getaclentry"></a>CAcl::ゲットアクエントリ

アクセス制御リスト (ACL) 内のエントリに関するすべての情報を取得します。

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
取得する ACL エントリへのインデックス。

*pSid*<br/>
ACL エントリが適用される[CSid](../../atl/reference/csid-class.md)オブジェクト。

*pマスク*<br/>
アクセスを許可または拒否するアクセス許可を指定するマスク。

*pタイプ*<br/>
ACE の種類。

*フラグ*<br/>
ACE フラグ。

*オブジェクトタイプ*<br/>
オブジェクトの種類。 オブジェクトタイプが ACE で指定されていない場合、または ACE が OBJECT ACE でない場合は、この値はGUID_NULLに設定されます。

*オブジェクト型*<br/>
継承されたオブジェクトの種類。 継承されたオブジェクトの種類が ACE で指定されていない場合、または ACE が OBJECT ACE でない場合は、この値は GUID_NULL に設定されます。

### <a name="remarks"></a>解説

このメソッドは、個々の ACE に関するすべての情報を取得し[、CAcl::GetAclEntries](#getaclentries)だけで使用可能にする情報よりも多くの情報を提供します。

ACE の種類とフラグの詳細については[、ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header)を参照してください。

## <a name="caclgetlength"></a><a name="getlength"></a>CAcl::ゲットレングス

アクセス制御リスト (ACL) の長さを返します。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>戻り値

構造体を保持するために必要な長さをバイト単位`ACL`で返します。

## <a name="caclgetpacl"></a><a name="getpacl"></a>CAcl::ゲットパック

アクセス制御リスト (ACL) へのポインターを返します。

```
const ACL* GetPACL() const throw(...);
```

### <a name="return-value"></a>戻り値

構造体へのポインターを`ACL`返します。

## <a name="caclisempty"></a><a name="isempty"></a>CAcl::IsEmpty

オブジェクトの`CAcl`エントリをテストします。

```
bool IsEmpty() const throw();
```

### <a name="remarks"></a>解説

オブジェクトが`CAcl`NULL でなく、エントリが含まれていない場合は TRUE を返します。 オブジェクトが NULL`CAcl`であるか、または少なくとも 1 つのエントリを含む場合は FALSE を返します。

## <a name="caclisnull"></a><a name="isnull"></a>CAcl::IsNull

オブジェクトのステータスを`CAcl`返します。

```
bool IsNull() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが`CAcl`NULL の場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cacloperator-const-acl-"></a><a name="operator_const_acl__star"></a>CAcl::演算子のコンスト ACL *

オブジェクトを`CAcl` `ACL` (アクセス制御リスト) 構造体にキャストします。

```
operator const ACL *() const throw(...);
```

### <a name="remarks"></a>解説

構造体のアドレスを`ACL`返します。

## <a name="cacloperator-"></a><a name="operator_eq"></a>CAcl::演算子 =

代入演算子。

```
CAcl& operator= (const CAcl& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存`CAcl`のオブジェクトに割り当てる。

### <a name="return-value"></a>戻り値

更新された`CAcl`オブジェクトへの参照を返します。

## <a name="caclremoveace"></a><a name="removeace"></a>CAcl::除去エース

`CAcl`オブジェクトから特定の ACE (アクセス制御エントリ) を削除します。

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE エントリへのインデックス。

### <a name="remarks"></a>解説

このメソッドは[、CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)から派生しています。

## <a name="caclremoveaces"></a><a name="removeaces"></a>CAcl::除去エース

指定`CAcl``CSid`された に適用されるすべての ACE (アクセス制御エントリ) を から削除します。

```
bool RemoveAces(const CSid& rSid) throw(...)
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
`CSid` オブジェクトへの参照です。

## <a name="caclsetempty"></a><a name="setempty"></a>CAcl::セットEmpty

オブジェクトを`CAcl`空としてマークします。

```cpp
void SetEmpty() throw();
```

### <a name="remarks"></a>解説

は`CAcl`、空または NULL に設定できます。

## <a name="caclsetnull"></a><a name="setnull"></a>CAcl::セットヌル

オブジェクトを`CAcl`NULL としてマークします。

```cpp
void SetNull() throw();
```

### <a name="remarks"></a>解説

は`CAcl`、空または NULL に設定できます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
