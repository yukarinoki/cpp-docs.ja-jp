---
title: IOleControlImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
ms.openlocfilehash: 8b84f982d06547dd162da530d326d4cdb92e254a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442160"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl クラス

このクラスの既定の実装を提供する、`IOleControl`インターフェイスと実装`IUnknown`します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IOleControlImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IOleControlImpl::FreezeEvents](#freezeevents)|コンテナーを無視するか、コントロールからのイベントを受け取るかどうかを示します。|
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|コントロールのキーボード動作に関する情報が表示されます。 ATL の実装では、E_NOTIMPL を返します。|
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|1 つ以上のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。 ATL の実装では、S_OK を返します。|
|[IOleControlImpl::OnMnemonic](#onmnemonic)|ユーザーが指定されたキーストロークを押されたことをコントロールに通知します。 ATL の実装では、E_NOTIMPL を返します。|

## <a name="remarks"></a>Remarks

クラス`IOleControlImpl`の既定の実装を提供します、 [IOleControl](/windows/desktop/api/ocidl/nn-ocidl-iolecontrol)インターフェイスと実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents

ATL の実装で`FreezeEvents`コントロール クラスのインクリメント`m_nFreezeEvents`データ メンバー場合`bFreeze`が true の場合、およびデクリメント`m_nFreezeEvents`場合`bFreeze`は FALSE です。

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>Remarks

`FreezeEvents` S_OK を返します。

参照してください[:freezeevents](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-freezeevents) Windows SDK にします。

##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo

コントロールのキーボード動作に関する情報が表示されます。

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>Remarks

参照してください[IOleControl:GetControlInfo](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) Windows SDK にします。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange

1 つ以上のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IOleControl::OnAmbientPropertyChange](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) Windows SDK にします。

##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic

ユーザーが指定されたキーストロークを押されたことをコントロールに通知します。

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

参照してください[IOleControl::OnMnemonic](/windows/desktop/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) Windows SDK にします。

## <a name="see-also"></a>関連項目

[IOleObjectImpl クラス](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX コントロールのインターフェイス](/windows/desktop/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
