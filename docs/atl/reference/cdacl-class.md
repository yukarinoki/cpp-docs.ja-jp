---
title: CDacl クラス
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 713e78635fe261615a82ab518cdb2c68ac0eeed4
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747742"
---
# <a name="cdacl-class"></a>CDacl クラス

このクラスは、DACL (随意アクセス制御リスト) 構造体のラッパーです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CDacl : public CAcl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|コンストラクターです。|
|[CDacl::~CDacl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDacl::許可されたエースの追加](#addallowedace)|許可された ACE (アクセス制御エントリ) を`CDacl`オブジェクトに追加します。|
|[CDacl::拒否エースの追加](#adddeniedace)|拒否された ACE を`CDacl`オブジェクトに追加します。|
|[CDacl::ゲットエースカウント](#getacecount)|オブジェクト内の ACE (アクセス制御エントリ) の数`CDacl`を返します。|
|[CDacl::除去エース](#removeace)|`CDacl`オブジェクトから特定の ACE (アクセス制御エントリ) を削除します。|
|[CDacl::削除AllAces](#removeallaces)|`CDacl`オブジェクトに含まれるすべての ACE を削除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CDacl::演算子 =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

オブジェクトのセキュリティ記述子には、DACL を含めることができます。 DACL には、オブジェクトにアクセスできるユーザーとグループを識別する ACE (アクセス制御エントリ) が 0 個以上含まれています。 DACL が空の場合 (つまり、ACE がゼロである) 場合、アクセスは明示的に許可されないので、アクセスは暗黙的に拒否されます。 ただし、オブジェクトのセキュリティ記述子に DACL がない場合、オブジェクトは保護されず、すべてのユーザーが完全にアクセスできます。

オブジェクトの DACL を取得するには、オブジェクトの所有者であるか、オブジェクトにREAD_CONTROLアクセスできる必要があります。 オブジェクトの DACL を変更するには、オブジェクトへのアクセスWRITE_DAC必要があります。

オブジェクトの ACE の作成、追加、削除、削除を行うために用意されている`CDacl`クラス メソッドを使用します。 [「AtlGetDacl および AtlSetDacl](security-global-functions.md#atlgetdacl) 」も参照してください。 [AtlSetDacl](security-global-functions.md#atlsetdacl)

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[Cacl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a>CDacl::許可されたエースの追加

許可された ACE (アクセス制御エントリ) を`CDacl`オブジェクトに追加します。

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクト。

*アクセスマスク*<br/>
指定したオブジェクトに許可されるアクセス権のマスクを指定`CSid`します。

*エースフラッグス*<br/>
ACE 継承を制御するビット フラグのセット。

*オブジェクトタイプ*<br/>
オブジェクトの種類。

*オブジェクト型*<br/>
継承されたオブジェクトの種類。

### <a name="return-value"></a>戻り値

ACE が`CDacl`オブジェクトに追加された場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

オブジェクト`CDacl`には、オブジェクトにアクセスできるユーザーおよびグループを識別する、ゼロ個以上の ACE (アクセス制御エントリ) が含まれています。 このメソッドは、オブジェクトへのアクセスを許可する`CDacl`ACE を追加します。

パラメーターで設定できるさまざまなフラグの説明については[、ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header)を`AceFlags`参照してください。

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a>CDacl::拒否エースの追加

オブジェクトに拒否 ACE (アクセス制御エントリ)`CDacl`を追加します。

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
`CSid` オブジェクト。

*アクセスマスク*<br/>
指定したオブジェクトに対して拒否するアクセス権のマスク`CSid`を指定します。

*エースフラッグス*<br/>
ACE 継承を制御するビット フラグのセット。 メソッドの最初の形式では、既定値は 0 です。

*オブジェクトタイプ*<br/>
オブジェクトの種類。

*オブジェクト型*<br/>
継承されたオブジェクトの種類。

### <a name="return-value"></a>戻り値

ACE が`CDacl`オブジェクトに追加された場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

オブジェクト`CDacl`には、オブジェクトにアクセスできるユーザーおよびグループを識別する、ゼロ個以上の ACE (アクセス制御エントリ) が含まれています。 このメソッドは、オブジェクトへのアクセスを拒否する`CDacl`ACE を追加します。

パラメーターで設定できるさまざまなフラグの説明については[、ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header)を`AceFlags`参照してください。

## <a name="cdaclcdacl"></a><a name="cdacl"></a>CDacl::CDacl

コンストラクターです。

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存`ACL`の (アクセス制御リスト) 構造。

### <a name="remarks"></a>解説

オブジェクト`CDacl`は、既存`ACL`の構造を使用して任意で作成できます。 DACL (随意アクセス制御リスト) のみをこのパラメータとして渡す必要があり、SACL (システム アクセス制御リスト) は渡されないことに注意してください。 デバッグ ビルドでは、SACL を渡すと、アサートが発生します。 リリース ビルドでは、SACL を渡すと ACL 内の ACE (アクセス制御エントリ) が無視され、エラーは発生しません。

## <a name="cdaclcdacl"></a><a name="dtor"></a>CDacl::~CDacl

デストラクターです。

```
~CDacl () throw();
```

### <a name="remarks"></a>解説

デストラクターは[、CDacl::RemoveAllAces](#removeallaces)を使用して、すべての ACE (アクセス制御エントリ) を含む、オブジェクトによって取得されたリソースを解放します。

## <a name="cdaclgetacecount"></a><a name="getacecount"></a>CDacl::ゲットエースカウント

オブジェクト内の ACE (アクセス制御エントリ) の数`CDacl`を返します。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに含まれる ACE の数`CDacl`を返します。

## <a name="cdacloperator-"></a><a name="operator_eq"></a>CDacl::演算子 =

代入演算子。

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存のオブジェクトに割り当てる ACL (アクセス制御リスト)。

### <a name="return-value"></a>戻り値

更新された`CDacl`オブジェクトへの参照を返します。

### <a name="remarks"></a>解説

DACL (随意アクセス制御リスト) のみをこの関数に渡す必要があります。 SACL (システム アクセス制御リスト) をこの関数に渡すと、デバッグ ビルドで ASSERT が発生しますが、リリース ビルドではエラーは発生しません。

## <a name="cdaclremoveace"></a><a name="removeace"></a>CDacl::除去エース

`CDacl`オブジェクトから特定の ACE (アクセス制御エントリ) を削除します。

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE エントリへのインデックス。

### <a name="remarks"></a>解説

このメソッドは[、CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)から派生しています。

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a>CDacl::削除AllAces

`CDacl`オブジェクトに含まれるすべての ACE (アクセス制御エントリ) を削除します。

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>解説

`CDacl`オブジェクト内のすべての`ACE`(アクセス制御エントリ) 構造体 (存在する場合) を削除します。

## <a name="see-also"></a>関連項目

[セキュリティサンプル](../../overview/visual-cpp-samples.md)<br/>
[CAcl クラス](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[エース](/windows/win32/SecAuthZ/access-control-entries)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
