---
title: CFirePropNotifyEvent クラス
ms.date: 11/04/2016
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
ms.openlocfilehash: 493bc00708d031f1bf7a4eb74d56e927a9c3f1dd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57277158"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent クラス

このクラスは、コントロール プロパティの変更について、コンテナーのシンクに通知するためのメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CFirePropNotifyEvent
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(静的)コントロールのプロパティが変更されたコンテナーのシンクに通知します。|
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(静的)コントロールのプロパティが変更しようとしていますが、コンテナーのシンクに通知します。|

## <a name="remarks"></a>Remarks

`CFirePropNotifyEvent` コントロールのプロパティが変更されたかを変更するには、コンテナーのシンクに通知する 2 つのメソッドがあります。

場合は、制御を実装するクラスから派生`IPropertyNotifySink`、`CFirePropNotifyEvent`メソッドを呼び出すときに呼び出す`FireOnRequestEdit`または`FireOnChanged`します。 コントロール クラスを派生していない場合`IPropertyNotifySink`、これらの関数の呼び出しが S_OK を返します。

コントロールの作成の詳細については、、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged

すべての通知接続[IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイス (オブジェクトの接続ポイントがすべて) 上に、指定したオブジェクトのプロパティが変更されました。

```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*pUnk*<br/>
[in]ポインター、`IUnknown`の通知を送信するオブジェクト。

*dispID*<br/>
[in]変更されたプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>Remarks

この関数は、コントロールが接続ポイントをサポートしていない場合でも呼び出しが安全です。

##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit

すべての通知接続されている[IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイス (上、オブジェクトの接続ポイントがすべて)、指定したオブジェクトのプロパティが変更されようにします。

```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```

### <a name="parameters"></a>パラメーター

*pUnk*<br/>
[in]ポインター、`IUnknown`の通知を送信するオブジェクト。

*dispID*<br/>
[in]変更するプロパティの識別子。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>Remarks

この関数は、コントロールが接続ポイントをサポートしていない場合でも呼び出しが安全です。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
