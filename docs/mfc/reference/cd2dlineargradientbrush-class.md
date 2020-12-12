---
description: '詳細情報: CD2DLinearGradientBrush クラス'
title: CD2DLinearGradientBrush クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: b133abe796e609a44d1ebe35a6e6e969c8ee2a68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180332"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush クラス

ID2D1LinearGradientBrush のラッパー。

## <a name="syntax"></a>構文

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DLinearGradientBrush:: CD2DLinearGradientBrush](#cd2dlineargradientbrush)|CD2DLinearGradientBrush オブジェクトを構築します。|
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|デストラクターです。 D2D 線状グラデーションブラシオブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DLinearGradientBrush:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DLinearGradientBrush:: Create](#create)|CD2DLinearGradientBrush を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DLinearGradientBrush::D estroy](#destroy)|CD2DLinearGradientBrush オブジェクトを破棄します。 ( [CD2DGradientBrush::D estroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy)をオーバーライドします。)|
|[CD2DLinearGradientBrush::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DLinearGradientBrush:: Get](#get)|ID2D1LinearGradientBrush インターフェイスを返します。|
|[CD2DLinearGradientBrush:: GetEndPoint](#getendpoint)|線状グラデーションの終了座標を取得します。|
|[CD2DLinearGradientBrush:: GetStartPoint](#getstartpoint)|線状グラデーションの開始座標を取得します。|
|[CD2DLinearGradientBrush:: SetEndPoint](#setendpoint)|ブラシの座標空間における線状グラデーションの終了座標を設定します。|
|[CD2DLinearGradientBrush:: SetStartPoint](#setstartpoint)|ブラシの座標空間における線状グラデーションの開始座標を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DLinearGradientBrush:: operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|ID2D1LinearGradientBrush インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DLinearGradientBrush:: m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|グラデーションの始点と終点。|
|[CD2DLinearGradientBrush:: m_pLinearGradientBrush](#m_plineargradientbrush)|ID2D1LinearGradientBrush へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a> CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush

デストラクターです。 D2D 線状グラデーションブラシオブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a> CD2DLinearGradientBrush:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 NULL にすることはできません

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a> CD2DLinearGradientBrush:: CD2DLinearGradientBrush

CD2DLinearGradientBrush オブジェクトを構築します。

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
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

*LinearGradientBrushProperties*<br/>
グラデーションの始点と終点。

*colorInterpolationGamma*<br/>
グラデーションの分岐点の間の色補間が実行される領域。

*extendMode*<br/>
[0, 1] の正規化された範囲外のグラデーションの動作。

*pBrushProperties*<br/>
ブラシの不透明度と変換へのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a> CD2DLinearGradientBrush:: Create

CD2DLinearGradientBrush を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a> CD2DLinearGradientBrush::D estroy

CD2DLinearGradientBrush オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a> CD2DLinearGradientBrush::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a> CD2DLinearGradientBrush:: Get

ID2D1LinearGradientBrush インターフェイスを返します。

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1LinearGradientBrush インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a> CD2DLinearGradientBrush:: GetEndPoint

線状グラデーションの終了座標を取得します。

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>戻り値

ブラシの座標空間における線状グラデーションの終点の2次元座標。

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a> CD2DLinearGradientBrush:: GetStartPoint

線状グラデーションの開始座標を取得します。

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>戻り値

ブラシの座標空間における線形グラデーションの開始2次元座標。

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a> CD2DLinearGradientBrush:: m_LinearGradientBrushProperties

グラデーションの始点と終点。

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a> CD2DLinearGradientBrush:: m_pLinearGradientBrush

ID2D1LinearGradientBrush へのポインター。

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a> CD2DLinearGradientBrush:: operator ID2D1LinearGradientBrush *

ID2D1LinearGradientBrush インターフェイスを返します。

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>戻り値

ID2D1LinearGradientBrush インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a> CD2DLinearGradientBrush:: SetEndPoint

ブラシの座標空間における線状グラデーションの終了座標を設定します。

```cpp
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
ブラシの座標空間における線状グラデーションの終点の2次元座標。

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a> CD2DLinearGradientBrush:: SetStartPoint

ブラシの座標空間における線状グラデーションの開始座標を設定します。

```cpp
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
ブラシの座標空間における線形グラデーションの開始2次元座標。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
