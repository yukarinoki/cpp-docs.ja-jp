---
title: CD2DRadialGradientBrush クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
ms.openlocfilehash: 450314fdbf8441b0cc345430518d083573659add
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750307"
---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush クラス

ID2D1ラジアルグラデーションブラシのラッパー。

## <a name="syntax"></a>構文

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dラジアルグラデーションブラシ::CD2Dラジアルグラデーションブラシ](#cd2dradialgradientbrush)|オブジェクトを構築します。|
|[CD2Dラジアルグラデーションブラシ:~CD2Dラジアルグラデーションブラシ](#_dtorcd2dradialgradientbrush)|デストラクターです。 D2D 放射状グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dラジアルグラデーションブラシ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dラジアルグラデーションブラシ::作成](#create)|CD2Dラジアルグラデーションブラシを作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dラジアルグラデーションブラシ::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2Dグラデーションブラシ::Dエストロイ](../../mfc/reference/cd2dgradientbrush-class.md#destroy)をオーバーライドします。|
|[CD2Dラジアルグラデーションブラシ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dラジアルグラデーションブラシ::取得](#get)|インターフェイスを返します。|
|[CD2Dラジアルグラデーションブラシ::ゲットセンター](#getcenter)|グラデーション楕円の中心を取得します。|
|[CD2Dラジアルグラデーションブラシ::取得グラデーションオリジンオフセット](#getgradientoriginoffset)|グラデーション楕円の中心を基準としたグラデーション原点のオフセットを取得します。|
|[CD2Dラジアルグラデーションブラシ::取得半径X](#getradiusx)|グラデーション楕円の x 半径を取得します。|
|[CD2Dラジアルグラデーションブラシ::取得半径](#getradiusy)|グラデーション楕円の y 半径を取得します。|
|[CD2Dラジアルグラデーションブラシ::セットセンター](#setcenter)|ブラシの座標空間内のグラデーション楕円の中心を指定します。|
|[CD2Dラジアルグラデーションブラシ::設定グラデーションオリジンオフセット](#setgradientoriginoffset)|グラデーション楕円の中心を基準としたグラデーション原点のオフセットを指定します。|
|[CD2Dラジアルグラデーションブラシ::セットラジアレックス](#setradiusx)|ブラシの座標空間でのグラデーション楕円の x 半径を指定します。|
|[CD2Dラジアルグラデーションブラシ::設定半径](#setradiusy)|ブラシの座標空間でのグラデーション楕円の Y 半径を指定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2Dラジアルグラデーションブラシ::演算子ID2D1ラジアルグラデーションブラシ*](#operator_id2d1radialgradientbrush_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dラジアルグラデーションブラシ::m_pRadialGradientBrush](#m_pradialgradientbrush)|ID2D1ラジアルグラデーションブラシへのポインタ。|
|[CD2Dラジアルグラデーションブラシ::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|ブラシのグラデーションの中心、原点オフセット、x 半径と y 半径。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[CD2Dブラシ](../../mfc/reference/cd2dbrush-class.md)

[グラデーションブラシ](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a>CD2Dラジアルグラデーションブラシ:~CD2Dラジアルグラデーションブラシ

デストラクターです。 D2D 放射状グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DRadialGradientBrush();
```

## <a name="cd2dradialgradientbrushattach"></a><a name="attach"></a>CD2Dラジアルグラデーションブラシ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a>CD2Dラジアルグラデーションブラシ::CD2Dラジアルグラデーションブラシ

オブジェクトを構築します。

```
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,
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

*ラジアルグラデーションブラシプロパティ*<br/>
ブラシのグラデーションの中心、原点オフセット、x 半径と y 半径。

*カラー補間ガンマ*<br/>
グラデーションの分岐点間の色補間を行うスペース。

*拡張モード*<br/>
[0,1] 正規化された範囲外のグラデーションの動作。

*プロパティ*<br/>
ブラシの不透明度と変換へのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dradialgradientbrushcreate"></a><a name="create"></a>CD2Dラジアルグラデーションブラシ::作成

CD2Dラジアルグラデーションブラシを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dradialgradientbrushdestroy"></a><a name="destroy"></a>CD2Dラジアルグラデーションブラシ::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dradialgradientbrushdetach"></a><a name="detach"></a>CD2Dラジアルグラデーションブラシ::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dradialgradientbrushget"></a><a name="get"></a>CD2Dラジアルグラデーションブラシ::取得

インターフェイスを返します。

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1RadialGradientBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a>CD2Dラジアルグラデーションブラシ::ゲットセンター

グラデーション楕円の中心を取得します。

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>戻り値

グラデーション楕円の中心。 この値はブラシの座標空間で表されます。

## <a name="cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a>CD2Dラジアルグラデーションブラシ::取得グラデーションオリジンオフセット

グラデーション楕円の中心を基準としたグラデーション原点のオフセットを取得します。

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>戻り値

グラデーション楕円の中心からのグラデーション原点のオフセット。 この値はブラシの座標空間で表されます。

## <a name="cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a>CD2Dラジアルグラデーションブラシ::取得半径X

グラデーション楕円の x 半径を取得します。

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>戻り値

グラデーション楕円の x 半径。 この値はブラシの座標空間で表されます。

## <a name="cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a>CD2Dラジアルグラデーションブラシ::取得半径

グラデーション楕円の y 半径を取得します。

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>戻り値

グラデーション楕円の y 半径。 この値はブラシの座標空間で表されます。

## <a name="cd2dradialgradientbrushm_pradialgradientbrush"></a><a name="m_pradialgradientbrush"></a>CD2Dラジアルグラデーションブラシ::m_pRadialGradientBrush

ID2D1ラジアルグラデーションブラシへのポインタ。

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

## <a name="cd2dradialgradientbrushm_radialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a>CD2Dラジアルグラデーションブラシ::m_RadialGradientBrushProperties

ブラシのグラデーションの中心、原点オフセット、x 半径と y 半径。

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

## <a name="cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a>CD2Dラジアルグラデーションブラシ::演算子ID2D1ラジアルグラデーションブラシ*

インターフェイスを返します。

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>戻り値

ID2D1RadialGradientBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a>CD2Dラジアルグラデーションブラシ::セットセンター

ブラシの座標空間内のグラデーション楕円の中心を指定します。

```cpp
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
グラデーション楕円の中心 (ブラシの座標空間内)

## <a name="cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a>CD2Dラジアルグラデーションブラシ::設定グラデーションオリジンオフセット

グラデーション楕円の中心を基準としたグラデーション原点のオフセットを指定します。

```cpp
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>パラメーター

*グラデーションオリジンオフセット*<br/>
グラデーション楕円の中心からのグラデーション原点のオフセット

## <a name="cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a>CD2Dラジアルグラデーションブラシ::セットラジアレックス

ブラシの座標空間でのグラデーション楕円の x 半径を指定します。

```cpp
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>パラメーター

*半径X*<br/>
グラデーション楕円の x 半径。 この値はブラシの座標空間内にあります。

## <a name="cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a>CD2Dラジアルグラデーションブラシ::設定半径

ブラシの座標空間でのグラデーション楕円の Y 半径を指定します。

```cpp
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>パラメーター

*半径Y*<br/>
グラデーション楕円の y 半径。 この値はブラシの座標空間内にあります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
