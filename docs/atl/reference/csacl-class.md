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
ms.openlocfilehash: 72b5c9fee3868286f9e4a0917f46aeb732349c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330997"
---
# <a name="csacl-class"></a>CSacl クラス

このクラスは、SACL (システム アクセス制御リスト) 構造体のラッパーです。

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
|[CSacl::CSacl](#csacl)|コンストラクターです。|
|[CSacl::~CSacl](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSacl:監査エースの追加](#addauditace)|`CSacl`オブジェクトに監査アクセス制御エントリ (ACE) を追加します。|
|[CSacl::ゲットエースカウント](#getacecount)|オブジェクト内のアクセス制御エントリ (ACE) の数を`CSacl`返します。|
|[CSacl::除去エース](#removeace)|`CSacl`オブジェクトから特定の ACE (アクセス制御エントリ) を削除します。|
|[CSacl::削除AllAces](#removeallaces)|`CSacl`オブジェクトに含まれるすべての ACE を削除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CSacl::演算子 =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

SACL には、ドメイン コントローラのセキュリティ イベント ログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (ACE) が含まれています。 SACL は、アクセス試行が行われたドメイン コントローラ上でのみログ エントリを生成し、オブジェクトのレプリカを含むすべてのドメイン コントローラ上で生成されます。

オブジェクトのセキュリティ記述子で SACL を設定または取得するには、要求元スレッドのアクセス トークンでSE_SECURITY_NAME特権を有効にする必要があります。 管理者グループには、この特権が既定で付与されており、他のユーザーまたはグループに付与できます。 特権を付与する必要があるすべてではありません: 特権によって定義された操作を実行する前に、特権を有効にするためには、セキュリティ アクセス トークンで特権を有効にする必要があります。 このモデルでは、特定のシステム操作に対してのみ特権を有効にし、必要がなくなったときに無効にすることができます。 SE_SECURITY_NAMEを有効にする例については[、AtlGetSacl](security-global-functions.md#atlgetsacl)および[AtlSetSacl](security-global-functions.md#atlsetsacl)を参照してください。

提供されているクラス メソッドを使用して、オブジェクトの ACE の追加、削除`SACL`、作成、および削除を行います。 [「AtlGetSacl および AtlSetSacl」](security-global-functions.md#atlgetsacl)も参照してください。 [AtlSetSacl](security-global-functions.md#atlsetsacl)

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[Cacl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="csacladdauditace"></a><a name="addauditace"></a>CSacl:監査エースの追加

`CSacl`オブジェクトに監査アクセス制御エントリ (ACE) を追加します。

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

*アクセスマスク*<br/>
指定したオブジェクトについて監査するアクセス権のマスクを指定します`CSid`。

*b成功*<br/>
許可されたアクセス試行を監査するかどうかを指定します。 監査を有効にするには、このフラグを true に設定します。それ以外の場合は、false に設定します。

*b失敗*<br/>
拒否されたアクセス試行を監査するかどうかを指定します。 監査を有効にするには、このフラグを true に設定します。それ以外の場合は、false に設定します。

*エースフラッグス*<br/>
ACE 継承を制御するビット フラグのセット。

*オブジェクトタイプ*<br/>
オブジェクトの種類。

*オブジェクト型*<br/>
継承されたオブジェクトの種類。

### <a name="return-value"></a>戻り値

ACE が`CSacl`オブジェクトに追加された場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

オブジェクト`CSacl`には、セキュリティ イベント ログに監査レコードを生成するアクセス試行の種類を指定するアクセス制御エントリ (ACE) が含まれています。 このメソッドは、オブジェクトにこのような`CSacl`ACE を追加します。

*AceFlags*パラメーターで設定できるさまざまなフラグの説明については[、ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header)を参照してください。

## <a name="csaclcsacl"></a><a name="csacl"></a>CSacl::CSacl

コンストラクターです。

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存`ACL`の (アクセス制御リスト) 構造。

### <a name="remarks"></a>解説

オブジェクト`CSacl`は、既存`ACL`の構造を使用して任意で作成できます。 このパラメーターが、随意アクセス制御リスト (DACL) ではなく、システムのアクセス制御リスト (SACL) であることを確認します。 デバッグ ビルドでは、DACL が指定されるとアサーションが発生します。 リリース ビルドでは、DACL からのエントリはすべて無視されます。

## <a name="csaclcsacl"></a><a name="dtor"></a>CSacl::~CSacl

デストラクターです。

```
~CSacl() throw();
```

### <a name="remarks"></a>解説

デストラクターは、オブジェクトが取得したリソース (すべてのアクセス制御エントリ (ACE) を含む) を解放します。

## <a name="csaclgetacecount"></a><a name="getacecount"></a>CSacl::ゲットエースカウント

オブジェクト内のアクセス制御エントリ (ACE) の数を`CSacl`返します。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトに含まれる ACE の数`CSacl`を返します。

## <a name="csacloperator-"></a><a name="operator_eq"></a>CSacl::演算子 =

代入演算子。

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>パラメーター

*rhs*<br/>
既存`ACL`のオブジェクトに割り当てる (アクセス制御リスト)。

### <a name="return-value"></a>戻り値

更新された`CSacl`オブジェクトへの参照を返します。 `ACL`パラメータが実際にはシステム アクセス制御リスト (SACL) であり、随意アクセス制御リスト (DACL) ではないことを確認します。 デバッグ ビルドではアサーションが発生し、リリース ビルドでは`ACL`パラメーターは無視されます。

## <a name="csaclremoveace"></a><a name="removeace"></a>CSacl::除去エース

`CSacl`オブジェクトから特定の ACE (アクセス制御エントリ) を削除します。

```
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
削除する ACE エントリへのインデックス。

### <a name="remarks"></a>解説

このメソッドは[、CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat)から派生しています。

## <a name="csaclremoveallaces"></a><a name="removeallaces"></a>CSacl::削除AllAces

`CSacl`オブジェクトに含まれるアクセス制御エントリ (ACE) をすべて削除します。

```
void RemoveAllAces() throw();
```

### <a name="remarks"></a>解説

`CSacl`オブジェクト内のすべての`ACE`構造体 (存在する場合) を削除します。

## <a name="see-also"></a>関連項目

[CAcl クラス](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[エース](/windows/win32/SecAuthZ/access-control-entries)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[セキュリティグローバル関数](../../atl/reference/security-global-functions.md)
