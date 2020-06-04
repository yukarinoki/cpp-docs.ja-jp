---
title: クラス
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
ms.openlocfilehash: 947ec16e91b99cc42cff90abe7df4a5d13576e98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329615"
---
# <a name="iolecontrolimpl-class"></a>クラス

このクラスは、インターフェイスの既定の`IOleControl`実装を提供し`IUnknown`、実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IOleControlImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IOle コントロール インプル::フリーズイベント](#freezeevents)|コンテナーがコントロールのイベントを無視するか受け入れるかを示します。|
|[コントロール インプル::取得コントロールヒント](#getcontrolinfo)|コントロールのキーボード動作に関する情報を入力します。 ATL の実装はE_NOTIMPL返します。|
|[IOle コントロール インプル::オンアンビエントプロパティチェンジ](#onambientpropertychange)|コンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。 ATL 実装はS_OKを返します。|
|[IOleコントロールインプル::オンムネモニック](#onmnemonic)|指定したキーストロークをユーザーが押したことをコントロールに通知します。 ATL の実装はE_NOTIMPL返します。|

## <a name="remarks"></a>解説

クラス`IOleControlImpl`は[、IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol)インターフェイスの既定の実装を提供`IUnknown`し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="iolecontrolimplfreezeevents"></a><a name="freezeevents"></a>IOle コントロール インプル::フリーズイベント

ATL の実装では、`FreezeEvents``m_nFreezeEvents`コントロール クラスのデータ メンバーが TRUE`bFreeze`の場合はインクリメントし`m_nFreezeEvents`、FALSE の場合`bFreeze`はデクリメントします。

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>解説

`FreezeEvents`S_OKを返します。

「Windows SDK[の IOleControl::フリーズイベント](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents)」を参照してください。

## <a name="iolecontrolimplgetcontrolinfo"></a><a name="getcontrolinfo"></a>コントロール インプル::取得コントロールヒント

コントロールのキーボード動作に関する情報を入力します。

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>解説

Windows SDK[の「IOleControl:GetControlInfo」](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo)を参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

## <a name="iolecontrolimplonambientpropertychange"></a><a name="onambientpropertychange"></a>IOle コントロール インプル::オンアンビエントプロパティチェンジ

コンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

を参照してください[。](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange)

## <a name="iolecontrolimplonmnemonic"></a><a name="onmnemonic"></a>IOleコントロールインプル::オンムネモニック

指定したキーストロークをユーザーが押したことをコントロールに通知します。

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOleControl::オンムネモニック](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic)」を参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX コントロール インターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
