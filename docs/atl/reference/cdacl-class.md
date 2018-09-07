---
title: CDacl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
dev_langs:
- C++
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3ce384c2478359b3496aa2d816a30e9a240c998
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760745"
---
# <a name="cdacl-class"></a>CDacl クラス

このクラスは、DACL (随意アクセス制御リスト) 構造体のラッパーです。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

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
|[CDacl::AddAllowedAce](#addallowedace)|許可されているように ACE を (アクセス制御エントリ) を追加、`CDacl`オブジェクト。|
|[CDacl::AddDeniedAce](#adddeniedace)|拒否された ACE を追加、`CDacl`オブジェクト。|
|[CDacl::GetAceCount](#getacecount)|Ace (アクセス制御エントリ) の数を返します、`CDacl`オブジェクト。|
|[CDacl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) を削除、`CDacl`オブジェクト。|
|[CDacl::RemoveAllAces](#removeallaces)|すべてに含まれている Ace の削除、`CDacl`オブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CDacl::operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>Remarks

オブジェクトのセキュリティ記述子は、DACL を含めることができます。 DACL には、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する 0 個以上の Ace (アクセス制御エントリ) が含まれています。 DACL が空の場合 (つまり、それに含まれる 0 個の Ace) のアクセスが明示的に付与ありません、ため、アクセスが暗黙的に拒否されます。 ただし、オブジェクトのセキュリティ記述子は、DACL を持たない場合、オブジェクトが保護されていないと、完全なアクセス権を持つすべてのユーザー。

オブジェクトの DACL を取得するには、オブジェクトの所有者であるか READ_CONTROL オブジェクトにアクセスします。 できます。 オブジェクトの DACL を変更するには、オブジェクトに対する WRITE_DAC アクセス許可が必要です。

作成、追加、削除、およびから Ace を削除する指定されたクラスのメソッドを使用して、`CDacl`オブジェクト。 参照してください[AtlGetDacl](security-global-functions.md#atlgetdacl)と[AtlSetDacl](security-global-functions.md#atlsetdacl)します。

Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity.h

##  <a name="addallowedace"></a>  CDacl::AddAllowedAce

許可されているように ACE を (アクセス制御エントリ) を追加、`CDacl`オブジェクト。

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

*rSid*  
A [CSid](../../atl/reference/csid-class.md)オブジェクト。

*AccessMask*  
許可されるアクセス権のマスクを指定します、指定された`CSid`オブジェクト。

*AceFlags*  
ACE の継承を制御するビット フラグのセット。

*pObjectType*  
オブジェクトの型。

*pInheritedObjectType*  
継承されたオブジェクトの種類。

### <a name="return-value"></a>戻り値

ACE を追加する場合は TRUE を返します、`CDacl`オブジェクト、false の場合失敗します。

### <a name="remarks"></a>Remarks

A`CDacl`オブジェクトには、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する 0 個以上の Ace (アクセス制御エントリ) が含まれています。 このメソッドへのアクセスを許可する ACE を追加、`CDacl`オブジェクト。

参照してください[ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header)で設定できるさまざまなフラグの説明については、`AceFlags`パラメーター。

##  <a name="adddeniedace"></a>  CDacl::AddDeniedAce

拒否 ACE (アクセス制御エントリ) に追加、`CDacl`オブジェクト。

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

*rSid*  
`CSid` オブジェクト。

*AccessMask*  
拒否するアクセス権のマスクを指定します、指定された`CSid`オブジェクト。

*AceFlags*  
ACE の継承を制御するビット フラグのセット。 既定値は、メソッドの最初のフォームでは 0 です。

*pObjectType*  
オブジェクトの型。

*pInheritedObjectType*  
継承されたオブジェクトの種類。

### <a name="return-value"></a>戻り値

ACE を追加する場合は TRUE を返します、`CDacl`オブジェクト、false の場合失敗します。

### <a name="remarks"></a>Remarks

A`CDacl`オブジェクトには、ユーザーとグループ オブジェクトにアクセスできるユーザーを識別する 0 個以上の Ace (アクセス制御エントリ) が含まれています。 このメソッドへのアクセスを拒否する ACE を追加、`CDacl`オブジェクト。

参照してください[ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header)で設定できるさまざまなフラグの説明については、`AceFlags`パラメーター。

##  <a name="cdacl"></a>  CDacl::CDacl

コンストラクターです。

```
CDacl (const ACL& rhs) throw(...);  
CDacl () throw();
```

### <a name="parameters"></a>パラメーター

*rhs*  
既存の`ACL`(アクセス制御リスト) の構造体。

### <a name="remarks"></a>Remarks

`CDacl`オブジェクトをオプションで作成した既存`ACL`構造体。 DACL (随意アクセス制御リスト) のみを確認することが重要と SACL ではありません (システム アクセス制御リスト) は、このパラメーターとして渡す必要があります。 デバッグ ビルドでは、SACL を渡すことするとアサートが発生します。 リリース ビルドでは、SACL を渡すことにより、(アクセス制御エントリ) の Ace は無視され、ACL でと、エラーは発生しません。

##  <a name="dtor"></a>  CDacl:: ~ CDacl

デストラクターです。

```
~CDacl () throw();
```

### <a name="remarks"></a>Remarks

デストラクターを使用してすべての Ace (アクセス制御エントリ) を含む、オブジェクトが取得したリソースを解放[CDacl::RemoveAllAces](#removeallaces)します。

##  <a name="getacecount"></a>  CDacl::GetAceCount

Ace (アクセス制御エントリ) の数を返します、`CDacl`オブジェクト。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>戻り値

含まれている Ace の数を返します、`CDacl`オブジェクト。

##  <a name="operator_eq"></a>  CDacl::operator =

代入演算子。

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*  
既存のオブジェクトに割り当てる ACL (アクセス制御リスト)。

### <a name="return-value"></a>戻り値

更新されたへの参照を返します`CDacl`オブジェクト。

### <a name="remarks"></a>Remarks

この関数には、DACL (随意アクセス制御リスト) を渡すのみことを確認してください。 SACL (システムへのアクセス制御リスト) を渡すことをこの関数によってアサート デバッグ ビルドでがエラーが発生しないリリース ビルドにします。

##  <a name="removeace"></a>  CDacl::RemoveAce

特定の ACE (アクセス制御エントリ) を削除、`CDacl`オブジェクト。

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*  
削除する ACE のエントリのインデックスです。

### <a name="remarks"></a>Remarks

このメソッドはから派生した[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)します。

##  <a name="removeallaces"></a>  CDacl::RemoveAllAces

すべてに含まれている (アクセス制御エントリ) の Ace の削除、`CDacl`オブジェクト。

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Remarks

削除ごと`ACE`(アクセス制御エントリ) 構造 (ある場合) で、`CDacl`オブジェクト。

## <a name="see-also"></a>関連項目

[セキュリティのサンプル](../../visual-cpp-samples.md)   
[CAcl クラス](../../atl/reference/cacl-class.md)   
[Acl](/windows/desktop/SecAuthZ/access-control-lists)   
[Ace](/windows/desktop/SecAuthZ/access-control-entries)   
[クラスの概要](../../atl/atl-class-overview.md)   
[セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
