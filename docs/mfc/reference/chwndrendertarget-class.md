---
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
ms.openlocfilehash: 24cf4127c2f429f66143af3a0f49625f23a4e6ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372458"
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
|[をクリックします。](#chwndrendertarget)|HWND から CHwndRenderTarget オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHwndレンダリングターゲット::アタッチ](#attach)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|
|[ウィンドウ状態を確認します。](#checkwindowstate)|このレンダー ターゲットに関連付けられている HWND が隠されているかどうかを示します。|
|[CHwndレンダリングターゲット::作成](#create)|ウィンドウに関連付けられたレンダー ターゲットを作成します。|
|[CHwndRenderターゲット::Dエタッハ](#detach)|オブジェクトからレンダー ターゲット インターフェイスをデタッチします。|
|[CHwndレンダーターゲット::ゲットワード](#gethwnd)|このレンダー ターゲットに関連付けられている HWND を返します。|
|[をクリックします。](#gethwndrendertarget)|インターフェイスを返します。|
|[CHwndレンダーターゲット::再作成](#recreate)|ウィンドウに関連付けられたレンダー ターゲットを再作成します。|
|[CHwndレンダーターゲット::サイズ変更](#resize)|レンダー ターゲットのサイズを指定したピクセル サイズに変更します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[::オペレーター ID2D1Hwndレンダーターゲット*](#operator_id2d1hwndrendertarget_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CHwndレンダーターゲット:m_pHwndRenderTarget](#m_phwndrendertarget)|オブジェクトへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[クレンダターゲット](../../mfc/reference/crendertarget-class.md)

[ターゲット](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="chwndrendertargetattach"></a><a name="attach"></a>CHwndレンダリングターゲット::アタッチ

既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>パラメーター

*pターゲット*<br/>
既存のレンダー ターゲット インターフェイス。 NULL にすることはできません。

## <a name="chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a>ウィンドウ状態を確認します。

このレンダー ターゲットに関連付けられている HWND が隠されているかどうかを示します。

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>戻り値

このレンダー ターゲットに関連付けられている HWND が閉塞されているかどうかを示す値。

## <a name="chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a>をクリックします。

HWND から CHwndRenderTarget オブジェクトを構築します。

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>パラメーター

*Hwnd*<br/>
このレンダー ターゲットに関連付けられた HWND

## <a name="chwndrendertargetcreate"></a><a name="create"></a>CHwndレンダリングターゲット::作成

ウィンドウに関連付けられたレンダー ターゲットを作成します。

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
このレンダー ターゲットに関連付けられた HWND

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="chwndrendertargetdetach"></a><a name="detach"></a>CHwndRenderターゲット::Dエタッハ

オブジェクトからレンダー ターゲット インターフェイスをデタッチします。

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたレンダー ターゲット インターフェイスへのポインター。

## <a name="chwndrendertargetgethwnd"></a><a name="gethwnd"></a>CHwndレンダーターゲット::ゲットワード

このレンダー ターゲットに関連付けられている HWND を返します。

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>戻り値

このレンダー ターゲットに関連付けられている HWND。

## <a name="chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a>をクリックします。

インターフェイスを返します。

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>戻り値

ID2D1HwndRenderTarget インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="chwndrendertargetm_phwndrendertarget"></a><a name="m_phwndrendertarget"></a>CHwndレンダーターゲット:m_pHwndRenderTarget

オブジェクトへのポインター。

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

## <a name="chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a>::オペレーター ID2D1Hwndレンダーターゲット*

インターフェイスを返します。

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>戻り値

ID2D1HwndRenderTarget インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="chwndrendertargetrecreate"></a><a name="recreate"></a>CHwndレンダーターゲット::再作成

ウィンドウに関連付けられたレンダー ターゲットを再作成します。

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
このレンダー ターゲットに関連付けられた HWND

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="chwndrendertargetresize"></a><a name="resize"></a>CHwndレンダーターゲット::サイズ変更

レンダー ターゲットのサイズを指定したピクセル サイズに変更します。

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
レンダー ターゲットの新しいサイズ (デバイス ピクセル単位)

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
