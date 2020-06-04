---
title: クラスを自動復帰する
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
ms.openlocfilehash: ea119436fd36d0814c05f1b48380028ad3f63f0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748242"
---
# <a name="cautorevertimpersonation-class"></a>クラスを自動復帰する

このクラスは[、CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトがスコープ外に出たときに、非偽装状態に戻します。

## <a name="syntax"></a>構文

```
class CAutoRevertImpersonation
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[偽装を元に戻す::C オートリバート偽装](#cautorevertimpersonation)|オブジェクトを構築`CAutoRevertImpersonation`します。|
|[偽装を元に戻す:~C オートリバート偽装](#dtor)|オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[偽装を元に戻す::アタッチ](#attach)|アクセス トークンの偽装の再変換を自動化します。|
|[偽装::Dエタッハ](#detach)|偽装の自動復帰をキャンセルします。|
|[偽装を行います。](#getaccesstoken)|このオブジェクトに関連付けられているアクセス トークンの現在を取得します。|

## <a name="remarks"></a>解説

[アクセス トークン](/windows/win32/SecAuthZ/access-tokens)は、プロセスまたはスレッドのセキュリティ コンテキストを記述するオブジェクトで、Windows NT または Windows 2000 システムにログオンしている各ユーザーに割り当てられます。 これらのアクセス トークンは`CAccessToken`、クラスで表すことができます。

アクセス トークンを偽装する必要がある場合があります。 このクラスは便宜上提供されていますが、アクセス トークンの偽装は実行しません。偽装されていない状態への自動復帰のみを実行します。 これは、トークン アクセスの偽装は、いくつかの異なる方法で実行できるためです。

Windows のアクセス制御モデルの概要については、Windows SDK の[アクセス制御](/windows/win32/SecAuthZ/access-control)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsecurity.h

## <a name="cautorevertimpersonationattach"></a><a name="attach"></a>偽装を元に戻す::アタッチ

アクセス トークンの偽装の再変換を自動化します。

```cpp
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>パラメーター

*Pat*<br/>
自動的に元に戻す[CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトのアドレス

### <a name="remarks"></a>解説

このメソッドは[、CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md)オブジェクトが NULL`CAccessToken`ポインターで作成された場合、または[以前に Detach](#detach)が呼び出された場合にのみ使用してください。 単純な場合、このメソッドを使用する必要はありません。

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="cautorevertimpersonation"></a>偽装を元に戻す::C オートリバート偽装

`CAutoRevertImpersonation` オブジェクトを構築します。

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>パラメーター

*Pat*<br/>
自動的に元に戻す[CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトのアドレス。

### <a name="remarks"></a>解説

アクセス トークンの実際の偽装は、オブジェクトの作成前に、できれば別に実行する`CAutoRevertImpersonation`必要があります。 オブジェクトがスコープ外に出ると、`CAutoRevertImpersonation`この偽装は自動的に元に戻されます。

## <a name="cautorevertimpersonationcautorevertimpersonation"></a><a name="dtor"></a>偽装を元に戻す:~C オートリバート偽装

オブジェクトを破棄し、アクセス トークンの偽装を元に戻します。

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>解説

構築時または[Attach](#attach)メソッドを使用して提供される[CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトに対して現在有効な偽装を元に戻します。 no`CAccessToken`が関連付けられている場合、デストラクターは何の効果もありません。

## <a name="cautorevertimpersonationdetach"></a><a name="detach"></a>偽装::Dエタッハ

偽装の自動復帰をキャンセルします。

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>戻り値

以前に関連付けられた[CAccessToken](../../atl/reference/caccesstoken-class.md)のアドレス。または関連付けが存在しない場合は NULL。

### <a name="remarks"></a>解説

**Detach**を呼び`CAutoRevertImpersonation`出すと、オブジェクトは、このオブジェクトに関連付けられている[CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトに対して現在有効な偽装を元に戻すことを防ぎます。 `CAutoRevertImpersonation`その後、効果なしで破棄したり、[アタッチ]を使用して同じ`CAccessToken`オブジェクトまたは別のオブジェクトに再び関連付[けたり](#attach)することができます。

## <a name="cautorevertimpersonationgetaccesstoken"></a><a name="getaccesstoken"></a>偽装を行います。

このオブジェクトに関連付けられているアクセス トークンの現在を取得します。

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>戻り値

以前に関連付けられた[CAccessToken](../../atl/reference/caccesstoken-class.md)のアドレス。または関連付けが存在しない場合は NULL。

### <a name="remarks"></a>解説

オブジェクトの偽装の復帰を含む目的でこのメソッドが呼び出された場合、代わりに Detach メソッドを使用する必要があります。 [Detach](#detach) `CAccessToken`

## <a name="see-also"></a>関連項目

[ATL セキュリティのサンプル](../../overview/visual-cpp-samples.md)<br/>
[アクセストークン](/windows/win32/SecAuthZ/access-tokens)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
