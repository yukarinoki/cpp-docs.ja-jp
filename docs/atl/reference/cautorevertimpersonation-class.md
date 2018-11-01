---
title: CAutoRevertImpersonation クラス
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: 799ec11fd8542a8b30ef3aa95f1a20700c5c9796
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444916"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation クラス

このクラスは、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトがスコープ外になったときにこの状態にします。

## <a name="syntax"></a>構文

```
class CAutoRevertImpersonation
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|構築、`CAutoRevertImpersonation`オブジェクト|
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAutoRevertImpersonation::Attach](#attach)|アクセス トークンの権限借用元に戻す処理を自動化します。|
|[CAutoRevertImpersonation::Detach](#detach)|自動偽装を元に戻す処理をキャンセルします。|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|このオブジェクトに関連付けられた現在のトークンへのアクセスを取得します。|

## <a name="remarks"></a>Remarks

[アクセス トークン](/windows/desktop/SecAuthZ/access-tokens)プロセスまたはスレッドのセキュリティ コンテキストを示し、Windows NT または Windows 2000 のシステムにログオンしている各ユーザーに割り当てられているオブジェクトです。 これらのアクセス トークンを表すことができます、`CAccessToken`クラス。

アクセス トークンを偽装する必要があります。 便宜上、このクラスが提供されているが、アクセス トークンの偽装は実行されません。のみ、自動 nonimpersonated 状態を元に戻す処理を実行します。 これは、ため、アクセス トークンの偽装を実行できるいくつかの方法です。

Windows でのアクセス制御モデルの概要については、次を参照してください。[アクセス制御](/windows/desktop/SecAuthZ/access-control)Windows SDK に含まれています。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

##  <a name="attach"></a>  CAutoRevertImpersonation::Attach

アクセス トークンの権限借用元に戻す処理を自動化します。

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>パラメーター

*PAT*<br/>
アドレス、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトを自動的に元に戻す

### <a name="remarks"></a>Remarks

このメソッドは、場合にのみ使用する必要があります、 [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md)オブジェクトが NULL で作成された`CAccessToken`ポインター、または[デタッチ](#detach)以前に呼び出されて。 単純な状況では、このメソッドを使用する必要はありません。

##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation

`CAutoRevertImpersonation` オブジェクトを構築します。

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>パラメーター

*PAT*<br/>
アドレス、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトを自動的に元に戻されます。

### <a name="remarks"></a>Remarks

可能であれば、作成する前に、アクセス トークンの実際の権限借用を個別に実行する必要があります、`CAutoRevertImpersonation`オブジェクト。 この権限の借用はときに戻されます自動的に、`CAutoRevertImpersonation`オブジェクトがスコープ外になります。

##  <a name="dtor"></a>  CAutoRevertImpersonation:: ~ CAutoRevertImpersonation

オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Remarks

有効な現在権限借用を元に戻します、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトの構築時、またはを通じて提供される、[アタッチ](#attach)メソッド。 ない場合は`CAccessToken`が関連付けられている場合、デストラクターは、影響を与えません。

##  <a name="detach"></a>  CAutoRevertImpersonation::Detach

自動偽装を元に戻す処理をキャンセルします。

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>戻り値

以前関連付けられているアドレス[CAccessToken](../../atl/reference/caccesstoken-class.md)アソシエーションが存在しない場合は null です。

### <a name="remarks"></a>Remarks

呼び出す**デタッチ**により、`CAutoRevertImpersonation`オブジェクトに対して有効な権限借用現在に戻してから、 [CAccessToken](../../atl/reference/caccesstoken-class.md)このオブジェクトに関連付けられたオブジェクト。 `CAutoRevertImpersonation` 影響を破棄または、同じまたは別に再関連付けできる`CAccessToken`オブジェクトを使用して[アタッチ](#attach)します。

##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken

このオブジェクトに関連付けられた現在のトークンへのアクセスを取得します。

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>戻り値

以前関連付けられているアドレス[CAccessToken](../../atl/reference/caccesstoken-class.md)アソシエーションが存在しない場合は null です。

### <a name="remarks"></a>Remarks

権限の借用の元に戻す処理を含める目的でこのメソッドが呼び出された場合、`CAccessToken`オブジェクト、[デタッチ](#detach)メソッドを代わりに使用する必要があります。

## <a name="see-also"></a>関連項目

[ATLSecurity サンプル](../../visual-cpp-samples.md)<br/>
[アクセス トークン](/windows/desktop/SecAuthZ/access-tokens)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
