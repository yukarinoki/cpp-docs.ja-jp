---
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
ms.openlocfilehash: d87cdae5c24eae391be8db2fcdd04f91d592e427
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753159"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush クラス

ID2D1線形グラデーションブラシのラッパー。

## <a name="syntax"></a>構文

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dリニアグラディエントグラデーションブラシ::CD2Dリニアグラデーションブラシ](#cd2dlineargradientbrush)|オブジェクトを構築します。|
|[CD2Dリニアグラディエントグラデーションブラシ:~CD2Dリニアグラデーションブラシ](#_dtorcd2dlineargradientbrush)|デストラクターです。 D2D 線形グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dリニアグラデーションブラシ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dリニアグラディエントグラデーションブラシ::作成](#create)|CD2D 線形グラデーションブラシを作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dリニアグラディエントグラデーションブラシ::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2Dグラデーションブラシ::Dエストロイ](../../mfc/reference/cd2dgradientbrush-class.md#destroy)をオーバーライドします。|
|[CD2Dリニアグラディエントグラデーションブラシ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dリニアグラディエントグラデーションブラシ::取得](#get)|インターフェイスを返します。|
|[CD2Dリニアグラディエントグラデーションブラシ::ゲットエンドポイント](#getendpoint)|線形グラデーションの終了座標を取得します。|
|[CD2Dリニアグラディエントブラシ::ゲットスタートポイント](#getstartpoint)|線形グラデーションの開始座標を取得します。|
|[CD2Dリニアグラディエントグラデーションブラシ::セットエンドポイント](#setendpoint)|ブラシの座標空間の線形グラデーションの終了座標を設定します。|
|[CD2Dリニアグラディエントブラシ::セットスタートポイント](#setstartpoint)|ブラシの座標空間の線形グラデーションの開始座標を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2Dリニアグラディエントブラシ::演算子ID2D1線形グラデーションブラシ*](#operator_id2d1lineargradientbrush_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dリニアグラディエントグラデーションブラシ::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|グラデーションの開始点と終了点。|
|[CD2Dリニアグラディエントグラデーションブラシ::m_pLinearGradientBrush](#m_plineargradientbrush)|ID2D1線形グラデーションブラシへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[CD2Dブラシ](../../mfc/reference/cd2dbrush-class.md)

[グラデーションブラシ](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a>CD2Dリニアグラディエントグラデーションブラシ:~CD2Dリニアグラデーションブラシ

デストラクターです。 D2D 線形グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a>CD2Dリニアグラデーションブラシ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a>CD2Dリニアグラディエントグラデーションブラシ::CD2Dリニアグラデーションブラシ

オブジェクトを構築します。

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

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*グラデーションストップ*<br/>
D2D1_GRADIENT_STOP構造体の配列へのポインター。

*グラデーションストップカウント*<br/>
gradientStops 配列内のグラデーションの終了位置の数を指定する 1 以上の値。

*線形グラデーションブラシプロパティ*<br/>
グラデーションの開始点と終了点。

*カラー補間ガンマ*<br/>
グラデーションの分岐点間の色補間を行うスペース。

*拡張モード*<br/>
[0,1] 正規化された範囲外のグラデーションの動作。

*プロパティ*<br/>
ブラシの不透明度と変換へのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a>CD2Dリニアグラディエントグラデーションブラシ::作成

CD2D 線形グラデーションブラシを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a>CD2Dリニアグラディエントグラデーションブラシ::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a>CD2Dリニアグラディエントグラデーションブラシ::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a>CD2Dリニアグラディエントグラデーションブラシ::取得

インターフェイスを返します。

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1LinearGradientBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a>CD2Dリニアグラディエントグラデーションブラシ::ゲットエンドポイント

線形グラデーションの終了座標を取得します。

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>戻り値

ブラシの座標空間における線形グラデーションの終了 2 次元座標

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a>CD2Dリニアグラディエントブラシ::ゲットスタートポイント

線形グラデーションの開始座標を取得します。

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>戻り値

ブラシの座標空間における線形グラデーションの開始 2 次元座標

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a>CD2Dリニアグラディエントグラデーションブラシ::m_LinearGradientBrushProperties

グラデーションの開始点と終了点。

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a>CD2Dリニアグラディエントグラデーションブラシ::m_pLinearGradientBrush

ID2D1線形グラデーションブラシへのポインター。

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a>CD2Dリニアグラディエントブラシ::演算子ID2D1線形グラデーションブラシ*

インターフェイスを返します。

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>戻り値

ID2D1LinearGradientBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a>CD2Dリニアグラディエントグラデーションブラシ::セットエンドポイント

ブラシの座標空間の線形グラデーションの終了座標を設定します。

```cpp
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
ブラシの座標空間における線形グラデーションの終了 2 次元座標

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a>CD2Dリニアグラディエントブラシ::セットスタートポイント

ブラシの座標空間の線形グラデーションの開始座標を設定します。

```cpp
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
ブラシの座標空間における線形グラデーションの開始 2 次元座標

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
