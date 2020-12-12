---
description: '詳細情報: CDCRenderTarget クラス'
title: CDCRenderTarget クラス
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 3959321bbd6274c821b1f02be5962b23ec9dbc95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185324"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget クラス

ID2D1DCRenderTarget のラッパー。

## <a name="syntax"></a>構文

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDCRenderTarget:: CDCRenderTarget](#cdcrendertarget)|CDCRenderTarget オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDCRenderTarget:: Attach](#attach)|既存のレンダーターゲットインターフェイスをオブジェクトにアタッチします。|
|[CDCRenderTarget:: BindDC](#binddc)|描画コマンドを発行するデバイスコンテキストにレンダーターゲットをバインドします。|
|[CDCRenderTarget:: Create](#create)|CDCRenderTarget を作成します。|
|[CDCRenderTarget::D etach。](#detach)|オブジェクトからレンダーターゲットインターフェイスをデタッチします|
|[CDCRenderTarget:: GetDCRenderTarget](#getdcrendertarget)|ID2D1DCRenderTarget インターフェイスを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CDCRenderTarget:: operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|ID2D1DCRenderTarget インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CDCRenderTarget:: m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget オブジェクトへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cdcrendertargetattach"></a><a name="attach"></a> CDCRenderTarget:: Attach

既存のレンダーターゲットインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>パラメーター

*pTarget*<br/>
既存のレンダーターゲットインターフェイス。 NULL にすることはできません

## <a name="cdcrendertargetbinddc"></a><a name="binddc"></a> CDCRenderTarget:: BindDC

描画コマンドを発行するデバイスコンテキストにレンダーターゲットをバインドします。

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
レンダーターゲットが描画コマンドを発行するデバイスコンテキスト

*rect*<br/>
レンダーターゲットがバインドされているデバイスコンテキスト (HDC) へのハンドルのサイズ

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a> CDCRenderTarget:: CDCRenderTarget

CDCRenderTarget オブジェクトを構築します。

```
CDCRenderTarget();
```

## <a name="cdcrendertargetcreate"></a><a name="create"></a> CDCRenderTarget:: Create

CDCRenderTarget を作成します。

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>パラメーター

*props*<br/>
レンダリングモード、ピクセル形式、リモート処理オプション、DPI 情報、およびハードウェアレンダリングに必要な最小限の DirectX サポート。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cdcrendertargetdetach"></a><a name="detach"></a> CDCRenderTarget::D etach。

オブジェクトからレンダーターゲットインターフェイスをデタッチします

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたレンダーターゲットインターフェイスへのポインター。

## <a name="cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a> CDCRenderTarget:: GetDCRenderTarget

ID2D1DCRenderTarget インターフェイスを返します。

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>戻り値

ID2D1DCRenderTarget インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cdcrendertargetm_pdcrendertarget"></a><a name="m_pdcrendertarget"></a> CDCRenderTarget:: m_pDCRenderTarget

ID2D1DCRenderTarget オブジェクトへのポインター。

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

## <a name="cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a> CDCRenderTarget:: operator ID2D1DCRenderTarget *

ID2D1DCRenderTarget インターフェイスを返します。

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>戻り値

ID2D1DCRenderTarget インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
