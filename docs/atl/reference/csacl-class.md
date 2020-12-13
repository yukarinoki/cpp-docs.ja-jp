---
description: CSacl クラスの詳細情報
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
ms.openlocfilehash: 504276d22da963b9e8ec407e88ca73d63dd71541
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140856"
---
# <a name="csacl-class"></a>CSacl クラス

このクラスは、SACL (システムアクセス制御リスト) 構造体のラッパーです。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CSacl : public CAcl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CSacl:: CSacl](#csacl)|コンストラクターです。|
|[CSacl:: ~ CSacl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSacl:: AddAuditAce](#addauditace)|オブジェクトに監査アクセス制御エントリ (ACE: access control entry) を追加し `CSacl` ます。|
|[CSacl:: GetAceCount](#getacecount)|オブジェクト内のアクセス制御エントリ (Ace: access control entries) の数を返し `CSacl` ます。|
|[CSacl:: RemoveAce](#removeace)|オブジェクトから特定の ACE (アクセス制御エントリ) を削除 `CSacl` します。|
|[CSacl:: RemoveAllAces](#removeallaces)|オブジェクトに格納されているすべての Ace を削除 `CSacl` します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSacl:: operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

SACL には、ドメインコントローラーのセキュリティイベントログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (Ace) が含まれています。 SACL は、オブジェクトのレプリカを含むすべてのドメインコントローラーではなく、アクセス試行が発生したドメインコントローラー上でのみログエントリを生成することに注意してください。

オブジェクトのセキュリティ記述子の SACL を設定または取得するには、要求元のスレッドのアクセストークンで SE_SECURITY_NAME の特権が有効になっている必要があります。 Administrators グループには、この特権が既定で付与されており、他のユーザーまたはグループに付与することができます。 特権が付与されている必要があるだけではありません。特権によって定義された操作を実行する前に、セキュリティアクセストークンで特権を有効にして有効にする必要があります。 このモデルでは、特定のシステム操作に対してのみ特権を有効にし、不要になった場合は無効にすることができます。 SE_SECURITY_NAME を有効にする例については、「 [Atlgetsacl](security-global-functions.md#atlgetsacl) 」および「 [atlgetsacl](security-global-functions.md#atlsetsacl) 」を参照してください。

提供されているクラスメソッドを使用して、オブジェクトの Ace を追加、削除、作成、および削除し `SACL` ます。 [Atlgetsacl](security-global-functions.md#atlgetsacl)および[atlgetsacl](security-global-functions.md#atlsetsacl)も参照してください。

Windows のアクセス制御モデルの概要については、Windows SDK の「 [Access Control](/windows/win32/SecAuthZ/access-control) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>要件

**ヘッダー:** atlsecurity .h

## <a name="csacladdauditace"></a><a name="addauditace"></a> CSacl:: AddAuditAce

オブジェクトに監査アクセス制御エントリ (ACE: access control entry) を追加し `CSacl` ます。

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
指定したオブジェクトに対して監査するアクセス権のマスクを指定し `CSid` ます。

*bSuccess*<br/>
許可されたアクセス試行を監査するかどうかを指定します。 監査を有効にするには、このフラグを true に設定します。それ以外の場合は、false に設定します。

*bFailure*<br/>
拒否されたアクセス試行を監査するかどうかを指定します。 監査を有効にするには、このフラグを true に設定します。それ以外の場合は、false に設定します。

*AceFlags*<br/>
ACE の継承を制御するビットフラグのセット。

*pObjectType*<br/>
オブジェクトの型。

*pInheritedObjectType*<br/>
継承されたオブジェクト型。

### <a name="return-value"></a>戻り値

ACE がオブジェクトに追加された場合は TRUE、失敗した場合は FALSE を返し `CSacl` ます。

### <a name="remarks"></a>解説

オブジェクトには、 `CSacl` セキュリティイベントログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (ace) が含まれています。 このメソッドは、このような ACE をオブジェクトに追加し `CSacl` ます。

*AceFlags* パラメーターで設定できるさまざまなフラグの説明については、「 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 」を参照してください。

## <a name="csaclcsacl"></a><a name="csacl"></a> CSacl:: CSacl

コンストラクターです。

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存 `ACL` の (アクセス制御リスト) 構造体。

### <a name="remarks"></a>解説

オブジェクトは、 `CSacl` 必要に応じて、既存の構造を使用して作成でき `ACL` ます。 このパラメーターが、随意アクセス制御リスト (DACL) ではなく、システムアクセス制御リスト (SACL) であることを確認してください。 デバッグビルドでは、DACL が指定されている場合、アサーションが発生します。 リリースビルドでは、DACL からのエントリは無視されます。

## <a name="csaclcsacl"></a><a name="dtor"></a> CSacl:: ~ CSacl

デストラクターです。

```
~CSacl() throw();
```

### <a name="remarks"></a>解説

デストラクターは、すべてのアクセス制御エントリ (Ace) を含め、オブジェクトによって取得されたすべてのリソースを解放します。

## <a name="csaclgetacecount"></a><a name="getacecount"></a> CSacl:: GetAceCount

オブジェクト内のアクセス制御エントリ (Ace: access control entries) の数を返し `CSacl` ます。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに格納されている Ace の数を返し `CSacl` ます。

## <a name="csacloperator-"></a><a name="operator_eq"></a> CSacl:: operator =

代入演算子。

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
`ACL`既存のオブジェクトに割り当てる (アクセス制御リスト)。

### <a name="return-value"></a>戻り値

更新されたオブジェクトへの参照を返し `CSacl` ます。 `ACL`パラメーターが、随意アクセス制御リスト (DACL) ではなく、実際にシステムアクセス制御リスト (SACL) であることを確認します。 デバッグビルドでは、アサーションが発生します。リリースビルドでは、 `ACL` パラメーターは無視されます。

## <a name="csaclremoveace"></a><a name="removeace"></a> CSacl:: RemoveAce

オブジェクトから特定の ACE (アクセス制御エントリ) を削除 `CSacl` します。

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE エントリのインデックス。

### <a name="remarks"></a>解説

このメソッドは、 [CAtlArray:: RemoveAt](../../atl/reference/catlarray-class.md#removeat)から派生しています。

## <a name="csaclremoveallaces"></a><a name="removeallaces"></a> CSacl:: RemoveAllAces

オブジェクトに格納されているすべてのアクセス制御エントリ (Ace: access control entries) を削除 `CSacl` します。

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>解説

`ACE`オブジェクト内のすべての構造体 (存在する場合) を削除 `CSacl` します。

## <a name="see-also"></a>関連項目

[CAcl クラス](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
