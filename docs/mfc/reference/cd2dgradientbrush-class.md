---
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
ms.openlocfilehash: 861bc32382737bd6482a3d51eb8470bf834e8508
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369230"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush クラス

CD2D線形グラデーションブラシと CD2Dラジアルグラデーションブラシクラスの基本クラス。

## <a name="syntax"></a>構文

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dグラデーションブラシ::CD2Dグラデーションブラシ](#cd2dgradientbrush)|オブジェクトを構築します。|
|[CD2Dグラデーションブラシ::~CD2Dグラデーションブラシ](#_dtorcd2dgradientbrush)|デストラクターです。 D2D グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dグラデーションブラシ::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2Dブラシ::Dエストロイ](../../mfc/reference/cd2dbrush-class.md#destroy)をオーバーライドします。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dグラデーションブラシ::m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP構造体の配列。|
|[CD2Dグラデーションブラシ::m_colorInterpolationGamma](#m_colorinterpolationgamma)|グラデーションの分岐点間の色補間を行うスペース。|
|[CD2Dグラデーションブラシ::m_extendMode](#m_extendmode)|[0,1] 正規化された範囲外のグラデーションの動作。|
|[CD2Dグラデーションブラシ::m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP構造体の配列へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[CD2Dブラシ](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a>CD2Dグラデーションブラシ::~CD2Dグラデーションブラシ

デストラクターです。 D2D グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DGradientBrush();
```

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a>CD2Dグラデーションブラシ::CD2Dグラデーションブラシ

オブジェクトを構築します。

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

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*グラデーションストップ*<br/>
D2D1_GRADIENT_STOP構造体の配列へのポインター。

*グラデーションストップカウント*<br/>
gradientStops 配列内のグラデーションの終了位置の数を指定する 1 以上の値。

*カラー補間ガンマ*<br/>
グラデーションの分岐点間の色補間を行うスペース。

*拡張モード*<br/>
[0,1] 正規化された範囲外のグラデーションの動作。

*プロパティ*<br/>
ブラシの不透明度と変換へのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dgradientbrushdestroy"></a><a name="destroy"></a>CD2Dグラデーションブラシ::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dgradientbrushm_argradientstops"></a><a name="m_argradientstops"></a>CD2Dグラデーションブラシ::m_arGradientStops

D2D1_GRADIENT_STOP構造体の配列。

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

## <a name="cd2dgradientbrushm_colorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a>CD2Dグラデーションブラシ::m_colorInterpolationGamma

グラデーションの分岐点間の色補間を行うスペース。

```
D2D1_GAMMA m_colorInterpolationGamma;
```

## <a name="cd2dgradientbrushm_extendmode"></a><a name="m_extendmode"></a>CD2Dグラデーションブラシ::m_extendMode

[0,1] 正規化された範囲外のグラデーションの動作。

```
D2D1_EXTEND_MODE m_extendMode;
```

## <a name="cd2dgradientbrushm_pgradientstops"></a><a name="m_pgradientstops"></a>CD2Dグラデーションブラシ::m_pGradientStops

D2D1_GRADIENT_STOP構造体の配列へのポインター。

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
