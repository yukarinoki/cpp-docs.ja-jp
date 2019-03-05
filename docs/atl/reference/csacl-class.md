---
title: CSacl クラス
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: f8820be3073c6ffaffdaa9d04a7338ad584d36ca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267292"
---
# <a name="csacl-class"></a>CSacl クラス

このクラスは、SACL (システムへのアクセス制御リスト) 構造体のラッパーです。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CSacl : public CAcl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|コンストラクターです。|
|[CSacl:: ~ CSacl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSacl::AddAuditAce](#addauditace)|監査アクセス制御エントリ (ACE) を追加、`CSacl`オブジェクト。|
|[CSacl::GetAceCount](#getacecount)|アクセス制御エントリ (Ace) の数を返します、`CSacl`オブジェクト。|
|[CSacl::RemoveAce](#removeace)|特定の ACE (アクセス制御エントリ) を削除、`CSacl`オブジェクト。|
|[CSacl::RemoveAllAces](#removeallaces)|すべてに含まれている Ace の削除、`CSacl`オブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSacl::operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>Remarks

SACL には、ドメイン コント ローラーのセキュリティ イベント ログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (Ace) が含まれています。 SACL がドメイン コント ローラーへのアクセス試行が発生した場所でのみ、オブジェクトのレプリカを含むすべてのドメイン コント ローラーではなく、ログ エントリを生成することに注意してください。

を設定またはオブジェクトのセキュリティ記述子の SACL を取得するのには、スレッドを要求するアクセス トークンで SE_SECURITY_NAME 特権を有効にする必要があります。 管理者グループにはこの権限が既定では、与えられて、その他のユーザーまたはグループに付与することができます。 権限を持つ許可が必要なの。 反映するためにセキュリティのアクセス トークンで、特権が有効にする必要があります特権によって定義された操作を実行する前にします。 モデルは、特定のシステム操作でのみ有効にし、不要になったときに、無効にするには特権を使用できます。 参照してください[AtlGetSacl](security-global-functions.md#atlgetsacl)と[AtlSetSacl](security-global-functions.md#atlsetsacl) SE_SECURITY_NAME の有効化の例についてはします。

追加、削除、作成、およびから Ace を削除する指定されたクラスのメソッドを使用して、`SACL`オブジェクト。 参照してください[AtlGetSacl](security-global-functions.md#atlgetsacl)と[AtlSetSacl](security-global-functions.md#atlsetsacl)します。

Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。

## <a name="inheritance-hierarchy"></a>継承階層

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

##  <a name="addauditace"></a>  CSacl::AddAuditAce

監査アクセス制御エントリ (ACE) を追加、`CSacl`オブジェクト。

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>パラメーター

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)オブジェクト。

*AccessMask*<br/>
監査するアクセス権のマスクを指定します、指定された`CSid`オブジェクト。

*bSuccess*<br/>
許可されるアクセス試行を監査するかどうかを指定します。 このフラグは、; 監査を有効にする場合は true を設定します。それ以外の場合、false に設定します。

*bFailure*<br/>
拒否されたアクセス試行を監査するかどうかを指定します。 このフラグは、; 監査を有効にする場合は true を設定します。それ以外の場合、false に設定します。

*AceFlags*<br/>
ACE の継承を制御するビット フラグのセット。

*pObjectType*<br/>
オブジェクトの型。

*pInheritedObjectType*<br/>
継承されたオブジェクトの種類。

### <a name="return-value"></a>戻り値

ACE を追加する場合は TRUE を返します、`CSacl`オブジェクト、false の場合失敗します。

### <a name="remarks"></a>Remarks

A`CSacl`オブジェクトには、セキュリティ イベント ログで監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (Ace) が含まれています。 このメソッドにこのような ACE を追加、`CSacl`オブジェクト。

参照してください[ACE_HEADER](/windows/desktop/api/winnt/ns-winnt-_ace_header)で設定できるさまざまなフラグの説明については、 *AceFlags*パラメーター。

##  <a name="csacl"></a>  CSacl::CSacl

コンストラクターです。

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存の`ACL`(アクセス制御リスト) の構造体。

### <a name="remarks"></a>Remarks

`CSacl`オブジェクトをオプションで作成した既存`ACL`構造体。 このパラメーターは、システム アクセス制御リスト (SACL) と随意アクセス制御リスト (DACL) ではなくことを確認します。 DACL が指定されている場合、デバッグ ビルドでアサーションが発生します。 リリース ビルドでは、DACL からのエントリは無視されます。

##  <a name="dtor"></a>  CSacl:: ~ CSacl

デストラクターです。

```
~CSacl() throw();
```

### <a name="remarks"></a>Remarks

デストラクターは、すべてのアクセス制御エントリ (Ace) を含む、オブジェクトが取得したすべてのリソースを解放します。

##  <a name="getacecount"></a>  CSacl::GetAceCount

アクセス制御エントリ (Ace) の数を返します、`CSacl`オブジェクト。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>戻り値

含まれている Ace の数を返します、`CSacl`オブジェクト。

##  <a name="operator_eq"></a>  CSacl::operator =

代入演算子。

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`ACL`を既存のオブジェクトを割り当てる (アクセス制御リスト)。

### <a name="return-value"></a>戻り値

更新されたへの参照を返します`CSacl`オブジェクト。 いることを確認、`ACL`パラメーターが実際には、システム アクセス制御リスト (SACL) と随意アクセス制御リスト (DACL) ではなく。 アサーションが発生すると、デバッグ ビルドとリリース ビルドでは、`ACL`パラメーターは無視されます。

##  <a name="removeace"></a>  CSacl::RemoveAce

特定の ACE (アクセス制御エントリ) を削除、`CSacl`オブジェクト。

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE のエントリのインデックスです。

### <a name="remarks"></a>Remarks

このメソッドはから派生した[CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)します。

##  <a name="removeallaces"></a>  CSacl::RemoveAllAces

含まれているアクセス制御エントリ (Ace) のすべてを削除、`CSacl`オブジェクト。

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>Remarks

削除ごと`ACE`(ある場合) を構成、`CSacl`オブジェクト。

## <a name="see-also"></a>関連項目

[CAcl クラス](../../atl/reference/cacl-class.md)<br/>
[Acl](/windows/desktop/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/desktop/SecAuthZ/access-control-entries)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)
