---
description: '詳細情報: CHwndRenderTarget クラス'
title: CHwndRenderTarget クラス
ms.date: 11/04/2016
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
ms.openlocfilehash: 3a3058105fff5e5ac304f2cc980cd93f2bac70a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143638"
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget クラス

ID2D1HwndRenderTarget のラッパー。

## <a name="syntax"></a>構文

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHwndRenderTarget:: CHwndRenderTarget](#chwndrendertarget)|HWND から CHwndRenderTarget オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHwndRenderTarget:: Attach](#attach)|既存のレンダーターゲットインターフェイスをオブジェクトにアタッチします。|
|[CHwndRenderTarget:: CheckWindowState](#checkwindowstate)|このレンダーターゲットに関連付けられている HWND が occluded かどうかを示します。|
|[CHwndRenderTarget:: Create](#create)|ウィンドウに関連付けられているレンダーターゲットを作成します。|
|[CHwndRenderTarget::D etach](#detach)|オブジェクトからレンダーターゲットインターフェイスをデタッチします|
|[CHwndRenderTarget:: GetHwnd](#gethwnd)|このレンダーターゲットに関連付けられている HWND を返します。|
|[CHwndRenderTarget:: GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget インターフェイスを返します。|
|[CHwndRenderTarget:: 再作成](#recreate)|ウィンドウに関連付けられているレンダーターゲットを再作成します。|
|[CHwndRenderTarget:: Resize](#resize)|レンダーターゲットのサイズを指定したピクセルサイズに変更します|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CHwndRenderTarget:: operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CHwndRenderTarget:: m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget オブジェクトへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="chwndrendertargetattach"></a><a name="attach"></a> CHwndRenderTarget:: Attach

既存のレンダーターゲットインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>パラメーター

*pTarget*<br/>
既存のレンダーターゲットインターフェイス。 NULL にすることはできません

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a> CHwndRenderTarget:: CheckWindowState

このレンダーターゲットに関連付けられている HWND が occluded かどうかを示します。

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>戻り値

このレンダーターゲットに関連付けられている HWND が occluded かどうかを示す値。

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a> CHwndRenderTarget:: CHwndRenderTarget

HWND から CHwndRenderTarget オブジェクトを構築します。

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>パラメーター

*hwnd*<br/>
このレンダーターゲットに関連付けられている HWND。

## <a name="chwndrendertargetcreate"></a><a name="create"></a> CHwndRenderTarget:: Create

ウィンドウに関連付けられているレンダーターゲットを作成します。

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
このレンダーターゲットに関連付けられている HWND。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="chwndrendertargetdetach"></a><a name="detach"></a> CHwndRenderTarget::D etach

オブジェクトからレンダーターゲットインターフェイスをデタッチします

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたレンダーターゲットインターフェイスへのポインター。

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a> CHwndRenderTarget:: GetHwnd

このレンダーターゲットに関連付けられている HWND を返します。

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>戻り値

このレンダーターゲットに関連付けられている HWND。

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a> CHwndRenderTarget:: GetHwndRenderTarget

ID2D1HwndRenderTarget インターフェイスを返します。

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>戻り値

ID2D1HwndRenderTarget インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a> CHwndRenderTarget:: m_pHwndRenderTarget

ID2D1HwndRenderTarget オブジェクトへのポインター。

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a> CHwndRenderTarget:: operator ID2D1HwndRenderTarget *

ID2D1HwndRenderTarget インターフェイスを返します。

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>戻り値

ID2D1HwndRenderTarget インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a> CHwndRenderTarget:: 再作成

ウィンドウに関連付けられているレンダーターゲットを再作成します。

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
このレンダーターゲットに関連付けられている HWND。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="chwndrendertargetresize"></a><a name="resize"></a> CHwndRenderTarget:: Resize

レンダーターゲットのサイズを指定したピクセルサイズに変更します

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
レンダーターゲットの新しいサイズ (デバイスピクセル単位)

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
