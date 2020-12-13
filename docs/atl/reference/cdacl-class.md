---
description: '詳細情報: CDacl クラス'
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
ms.openlocfilehash: 0f071cbf426fe9cf89752defa19ff7f212e142d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142000"
---
# <a name="cdacl-class"></a>CDacl クラス

このクラスは、DACL (随意アクセス制御リスト) 構造のラッパーです。

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
|[CDacl:: ~ CDacl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDacl:: AddAllowedAce](#addallowedace)|許可された ACE (アクセス制御エントリ) をオブジェクトに追加し `CDacl` ます。|
|[CDacl::AddDeniedAce](#adddeniedace)|拒否された ACE をオブジェクトに追加し `CDacl` ます。|
|[CDacl:: GetAceCount](#getacecount)|オブジェクト内の Ace (アクセス制御エントリ) の数を返し `CDacl` ます。|
|[CDacl:: RemoveAce](#removeace)|オブジェクトから特定の ACE (アクセス制御エントリ) を削除 `CDacl` します。|
|[CDacl::RemoveAllAces](#removeallaces)|オブジェクトに格納されているすべての Ace を削除 `CDacl` します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CDacl:: operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

オブジェクトのセキュリティ記述子には、DACL を含めることができます。 DACL には、オブジェクトにアクセスできるユーザーおよびグループを識別する、0個以上の Ace (アクセス制御エントリ) が含まれています。 DACL が空の場合 (つまり、Ace がゼロの場合)、アクセスは明示的に付与されないため、アクセスは暗黙的に拒否されます。 ただし、オブジェクトのセキュリティ記述子に DACL がない場合、オブジェクトは保護されず、すべてのユーザーが完全なアクセス権を持ちます。

オブジェクトの DACL を取得するには、オブジェクトの所有者であるか、オブジェクトへの READ_CONTROL アクセス権を持っている必要があります。 オブジェクトの DACL を変更するには、オブジェクトへの WRITE_DAC アクセス権が必要です。

提供されているクラスメソッドを使用して、オブジェクトの Ace を作成、追加、削除、および削除し `CDacl` ます。 [Atlgetdacl](security-global-functions.md#atlgetdacl)および[atlgetdacl](security-global-functions.md#atlsetdacl)も参照してください。

Windows のアクセス制御モデルの概要については、Windows SDK の「 [Access Control](/windows/win32/SecAuthZ/access-control) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a> CDacl:: AddAllowedAce

許可された ACE (アクセス制御エントリ) をオブジェクトに追加し `CDacl` ます。

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

*AccessMask*<br/>
指定したオブジェクトに許可するアクセス権のマスクを指定し `CSid` ます。

*AceFlags*<br/>
ACE の継承を制御するビットフラグのセット。

*pObjectType*<br/>
オブジェクトの型。

*pInheritedObjectType*<br/>
継承されたオブジェクト型。

### <a name="return-value"></a>戻り値

ACE がオブジェクトに追加された場合は TRUE、失敗した場合は FALSE を返し `CDacl` ます。

### <a name="remarks"></a>解説

オブジェクトには、 `CDacl` オブジェクトにアクセスできるユーザーおよびグループを識別する、0個以上の ace (アクセス制御エントリ) が含まれています。 このメソッドは、オブジェクトへのアクセスを許可する ACE を追加し `CDacl` ます。

パラメーターで設定できるさまざまなフラグの説明については、「 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 」を参照してください `AceFlags` 。

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a> CDacl::AddDeniedAce

拒否された ACE (アクセス制御エントリ) をオブジェクトに追加し `CDacl` ます。

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

*AccessMask*<br/>
指定したオブジェクトに対して拒否するアクセス権のマスクを指定し `CSid` ます。

*AceFlags*<br/>
ACE の継承を制御するビットフラグのセット。 メソッドの最初の形式では、既定値は0です。

*pObjectType*<br/>
オブジェクトの型。

*pInheritedObjectType*<br/>
継承されたオブジェクト型。

### <a name="return-value"></a>戻り値

ACE がオブジェクトに追加された場合は TRUE、失敗した場合は FALSE を返し `CDacl` ます。

### <a name="remarks"></a>解説

オブジェクトには、 `CDacl` オブジェクトにアクセスできるユーザーおよびグループを識別する、0個以上の ace (アクセス制御エントリ) が含まれています。 このメソッドは、オブジェクトへのアクセスを拒否する ACE を追加し `CDacl` ます。

パラメーターで設定できるさまざまなフラグの説明については、「 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 」を参照してください `AceFlags` 。

## <a name="cdaclcdacl"></a><a name="cdacl"></a> CDacl::CDacl

コンストラクターです。

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存 `ACL` の (アクセス制御リスト) 構造体。

### <a name="remarks"></a>解説

オブジェクトは、 `CDacl` 必要に応じて、既存の構造を使用して作成でき `ACL` ます。 このパラメーターとして渡す必要があるのは、SACL (システムアクセス制御リスト) ではなく DACL (随意アクセス制御リスト) のみであることに注意してください。 デバッグビルドでは、SACL を渡すとアサートが発生します。 リリースビルドでは、SACL を渡すと、ACL 内の Ace (アクセス制御エントリ) が無視され、エラーは発生しません。

## <a name="cdaclcdacl"></a><a name="dtor"></a> CDacl:: ~ CDacl

デストラクターです。

```
~CDacl () throw();
```

### <a name="remarks"></a>解説

デストラクターは、 [CDacl:: RemoveAllAces](#removeallaces)を使用して、すべての ace (アクセス制御エントリ) を含む、オブジェクトによって取得されたすべてのリソースを解放します。

## <a name="cdaclgetacecount"></a><a name="getacecount"></a> CDacl:: GetAceCount

オブジェクト内の Ace (アクセス制御エントリ) の数を返し `CDacl` ます。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに格納されている Ace の数を返し `CDacl` ます。

## <a name="cdacloperator-"></a><a name="operator_eq"></a> CDacl:: operator =

代入演算子。

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存のオブジェクトに割り当てる ACL (アクセス制御リスト)。

### <a name="return-value"></a>戻り値

更新されたオブジェクトへの参照を返し `CDacl` ます。

### <a name="remarks"></a>解説

DACL (随意アクセス制御リスト) のみをこの関数に渡すようにしてください。 この関数に SACL (システムアクセス制御リスト) を渡すと、デバッグビルドでアサートが発生しますが、リリースビルドではエラーは発生しません。

## <a name="cdaclremoveace"></a><a name="removeace"></a> CDacl:: RemoveAce

オブジェクトから特定の ACE (アクセス制御エントリ) を削除 `CDacl` します。

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE エントリのインデックス。

### <a name="remarks"></a>解説

このメソッドは、 [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat)から派生しています。

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a> CDacl::RemoveAllAces

オブジェクトに格納されているすべての Ace (アクセス制御エントリ) を削除 `CDacl` します。

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>解説

`ACE`オブジェクト内のすべての (アクセス制御エントリ) 構造体 (存在する場合) を削除 `CDacl` します。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../overview/visual-cpp-samples.md)<br/>
[CAcl クラス](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
