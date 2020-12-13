---
description: '詳細情報: IOleControlImpl クラス'
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
ms.openlocfilehash: e224f6f8db79c05cb8a774cd57517ba06108e592
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139426"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl クラス

このクラスは、インターフェイスの既定の実装を提供 `IOleControl` し、を実装し `IUnknown` ます。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleControlImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IOleControlImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IOleControlImpl:: FreezeEvents](#freezeevents)|コンテナーがコントロールのイベントを無視するか受け入れるかを示します。|
|[IOleControlImpl:: Get制御 Linfo](#getcontrolinfo)|コントロールのキーボード動作に関する情報を入力します。 ATL 実装は E_NOTIMPL を返します。|
|[IOleControlImpl:: OnAmbientPropertyChange](#onambientpropertychange)|1つ以上のコンテナーのアンビエントプロパティが変更されたことをコントロールに通知します。 ATL 実装は S_OK を返します。|
|[IOleControlImpl:: OnMnemonic](#onmnemonic)|ユーザーが指定されたキーストロークを押したことをコントロールに通知します。 ATL 実装は E_NOTIMPL を返します。|

## <a name="remarks"></a>解説

クラス `IOleControlImpl` は、 [IOleControl](/windows/win32/api/ocidl/nn-ocidl-iolecontrol) インターフェイスの既定の実装を提供し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleControl`

`IOleControlImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="iolecontrolimplfreezeevents"></a><a name="freezeevents"></a> IOleControlImpl:: FreezeEvents

ATL の実装で `FreezeEvents` は、が TRUE の場合はコントロールクラスの `m_nFreezeEvents` データメンバーをインクリメントし、 `bFreeze` が FALSE の場合はデクリメントし `m_nFreezeEvents` `bFreeze` ます。

```
HRESULT FreezeEvents(BOOL bFreeze);
```

### <a name="remarks"></a>解説

`FreezeEvents` 次に、S_OK を返します。

Windows SDK の「 [IOleControl:: FreezeEvents](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-freezeevents) 」を参照してください。

## <a name="iolecontrolimplgetcontrolinfo"></a><a name="getcontrolinfo"></a> IOleControlImpl:: Get制御 Linfo

コントロールのキーボード動作に関する情報を入力します。

```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IOleControl: Get Linfo](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-getcontrolinfo) 」を参照してください。

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

## <a name="iolecontrolimplonambientpropertychange"></a><a name="onambientpropertychange"></a> IOleControlImpl:: OnAmbientPropertyChange

1つ以上のコンテナーのアンビエントプロパティが変更されたことをコントロールに通知します。

```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleControl:: OnAmbientPropertyChange](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onambientpropertychange) 」を参照してください。

## <a name="iolecontrolimplonmnemonic"></a><a name="onmnemonic"></a> IOleControlImpl:: OnMnemonic

ユーザーが指定されたキーストロークを押したことをコントロールに通知します。

```
HRESULT OnMnemonic(LPMSG pMsg);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleControl:: OnMnemonic](/windows/win32/api/ocidl/nf-ocidl-iolecontrol-onmnemonic) 」を参照してください。

## <a name="see-also"></a>関連項目

[IOleObjectImpl クラス](../../atl/reference/ioleobjectimpl-class.md)<br/>
[ActiveX コントロールインターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
