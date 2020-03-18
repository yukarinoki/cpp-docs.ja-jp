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
ms.openlocfilehash: 3bdb501d8210c98ce982719358564c4937991e12
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423064"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl クラス

このクラスは、`IOleControl` インターフェイスの既定の実装を提供し、`IUnknown`を実装します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
`IOleControlImpl`から派生したクラス。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[IOleControlImpl:: FreezeEvents](#freezeevents)|コンテナーがコントロールのイベントを無視するか受け入れるかを示します。|
|[IOleControlImpl:: Get制御 Linfo](#getcontrolinfo)|コントロールのキーボード動作に関する情報を入力します。 ATL 実装は E_NOTIMPL を返します。|
|[IOleControlImpl:: OnAmbientPropertyChange](#onambientpropertychange)|1つ以上のコンテナーのアンビエントプロパティが変更されたことをコントロールに通知します。 ATL 実装は S_OK を返します。|
|[IOleControlImpl:: OnMnemonic](#onmnemonic)|ユーザーが指定されたキーストロークを押したことをコントロールに通知します。 ATL 実装は E_NOTIMPL を返します。|

## <a name="remarks"></a>解説

クラス `IOleControlImpl` は、 [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol)インターフェイスの既定の実装を提供し、デバッグビルドのダンプデバイスに情報を送信することによって `IUnknown` を実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl. h

##  <a name="freezeevents"></a>IOleControlImpl:: FreezeEvents

ATL の実装では `FreezeEvents`、`bFreeze` が TRUE の場合はコントロールクラスの `m_nFreezeEvents` データメンバーをインクリメントし、`bFreeze` が FALSE の場合は `m_nFreezeEvents` をデクリメントします。

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>解説

`FreezeEvents` は S_OK を返します。

Windows SDK の「 [IOleControl:: FreezeEvents](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) 」を参照してください。

##  <a name="getcontrolinfo"></a>IOleControlImpl:: Get制御 Linfo

コントロールのキーボード動作に関する情報を入力します。

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IOleControl: Get Linfo](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) 」を参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

##  <a name="onambientpropertychange"></a>IOleControlImpl:: OnAmbientPropertyChange

1つ以上のコンテナーのアンビエントプロパティが変更されたことをコントロールに通知します。

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleControl:: OnAmbientPropertyChange](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) 」を参照してください。

##  <a name="onmnemonic"></a>IOleControlImpl:: OnMnemonic

ユーザーが指定されたキーストロークを押したことをコントロールに通知します。

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleControl:: OnMnemonic](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) 」を参照してください。

## <a name="see-also"></a>参照

[IOleObjectImpl クラス](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX コントロールインターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
