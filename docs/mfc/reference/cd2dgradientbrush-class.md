---
description: '詳細情報: CD2DGradientBrush クラス'
title: CD2DGradientBrush クラス
ms.date: 03/27/2019
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
ms.openlocfilehash: c1af08ae27bd2cbee48c4abe22f413ffeb85cd1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193397"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush クラス

CD2DLinearGradientBrush クラスと CD2DRadialGradientBrush クラスの基本クラス。

## <a name="syntax"></a>構文

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DGradientBrush:: CD2DGradientBrush](#cd2dgradientbrush)|CD2DGradientBrush オブジェクトを構築します。|
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#_dtorcd2dgradientbrush)|デストラクターです。 D2D 勾配ブラシオブジェクトが破棄されるときに呼び出されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2DGradientBrush::D estroy](#destroy)|CD2DGradientBrush オブジェクトを破棄します。 ( [CD2DBrush::D estroy](../../mfc/reference/cd2dbrush-class.md#destroy)をオーバーライドします。)|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DGradientBrush:: m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP 構造体の配列。|
|[CD2DGradientBrush:: m_colorInterpolationGamma](#m_colorinterpolationgamma)|グラデーションの分岐点の間の色補間が実行される領域。|
|[CD2DGradientBrush:: m_extendMode](#m_extendmode)|[0, 1] の正規化された範囲外のグラデーションの動作。|
|[CD2DGradientBrush:: m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP 構造体の配列へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a> CD2DGradientBrush:: ~ CD2DGradientBrush

デストラクターです。 D2D 勾配ブラシオブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DGradientBrush();
```

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a> CD2DGradientBrush:: CD2DGradientBrush

CD2DGradientBrush オブジェクトを構築します。

```
CD2DGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*gradientStops*<br/>
D2D1_GRADIENT_STOP 構造体の配列へのポインター。

*gradientStopsCount*<br/>
GradientStops 配列内のグラデーションの分岐点の数を指定する1以上の値。

*colorInterpolationGamma*<br/>
グラデーションの分岐点の間の色補間が実行される領域。

*extendMode*<br/>
[0, 1] の正規化された範囲外のグラデーションの動作。

*pBrushProperties*<br/>
ブラシの不透明度と変換へのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dgradientbrushdestroy"></a><a name="destroy"></a> CD2DGradientBrush::D estroy

CD2DGradientBrush オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dgradientbrushm_argradientstops"></a><a name="m_argradientstops"></a> CD2DGradientBrush:: m_arGradientStops

D2D1_GRADIENT_STOP 構造体の配列。

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

## <a name="cd2dgradientbrushm_colorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a> CD2DGradientBrush:: m_colorInterpolationGamma

グラデーションの分岐点の間の色補間が実行される領域。

```
D2D1_GAMMA m_colorInterpolationGamma;
```

## <a name="cd2dgradientbrushm_extendmode"></a><a name="m_extendmode"></a> CD2DGradientBrush:: m_extendMode

[0, 1] の正規化された範囲外のグラデーションの動作。

```
D2D1_EXTEND_MODE m_extendMode;
```

## <a name="cd2dgradientbrushm_pgradientstops"></a><a name="m_pgradientstops"></a> CD2DGradientBrush:: m_pGradientStops

D2D1_GRADIENT_STOP 構造体の配列へのポインター。

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
