---
title: CD2DSolidColorBrush クラス
ms.date: 03/27/2019
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
ms.openlocfilehash: 5aa3d7688046b0c1b04983f2d27fe5579dd7c680
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369053"
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush クラス

ID2D1 ソリッドカラーブラシのラッパー。

## <a name="syntax"></a>構文

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dソリッドカラーブラシ::CD2Dソリッドカラーブラシ](#cd2dsolidcolorbrush)|オーバーロードされます。 オブジェクトを作成します。|
|[CD2Dソリッドカラーブラシ::~CD2Dソリッドカラーブラシ](#_dtorcd2dsolidcolorbrush)|デストラクターです。 D2D ソリッド ブラシ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dソリッドカラーブラシ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dソリッドカラーブラシ::作成](#create)|CD2D ソリッドカラーブラシを作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dソリッドカラーブラシ::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2Dブラシ::Dエストロイ](../../mfc/reference/cd2dbrush-class.md#destroy)をオーバーライドします。|
|[CD2Dソリッドカラーブラシ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dソリッドカラーブラシ::取得](#get)|インターフェイスを返します。|
|[CD2Dソリッドカラーブラシ::ゲットカラー](#getcolor)|単色ブラシのカラーを取得します。|
|[CD2Dソリッドカラーブラシ::セットカラー](#setcolor)|この単色ブラシの色を指定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2Dソリッドカラーブラシ::オペレーターID2D1ソリッドカラーブラシ*](#operator_id2d1solidcolorbrush_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dソリッドカラーブラシ::m_colorSolid](#m_colorsolid)|ブラシの純色。|
|[CD2Dソリッドカラーブラシ::m_pSolidColorBrush](#m_psolidcolorbrush)|オブジェクトを ID2D1SolidColorBrush オブジェクトへのポインターを格納します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[CD2Dブラシ](../../mfc/reference/cd2dbrush-class.md)

[CD2Dソリッドカラーブラシ](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a>CD2Dソリッドカラーブラシ::~CD2Dソリッドカラーブラシ

デストラクターです。 D2D ソリッド ブラシ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DSolidColorBrush();
```

## <a name="cd2dsolidcolorbrushattach"></a><a name="attach"></a>CD2Dソリッドカラーブラシ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a>CD2Dソリッドカラーブラシ::CD2Dソリッドカラーブラシ

オブジェクトを作成します。

```
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    D2D1_COLOR_F color,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    COLORREF color,
    int nAlpha = 255,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*色*<br/>
ブラシの色の赤、緑、青、アルファの値。

*プロパティ*<br/>
ブラシの不透明度と変換へのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

*nアルファ*<br/>
ブラシの色の不透明度。

## <a name="cd2dsolidcolorbrushcreate"></a><a name="create"></a>CD2Dソリッドカラーブラシ::作成

CD2D ソリッドカラーブラシを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a>CD2Dソリッドカラーブラシ::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dsolidcolorbrushdetach"></a><a name="detach"></a>CD2Dソリッドカラーブラシ::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dsolidcolorbrushget"></a><a name="get"></a>CD2Dソリッドカラーブラシ::取得

インターフェイスを返します。

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1SolidColorBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a>CD2Dソリッドカラーブラシ::ゲットカラー

単色ブラシのカラーを取得します。

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>戻り値

この単色ブラシの色

## <a name="cd2dsolidcolorbrushm_colorsolid"></a><a name="m_colorsolid"></a>CD2Dソリッドカラーブラシ::m_colorSolid

ブラシの純色。

```
D2D1_COLOR_F m_colorSolid;
```

## <a name="cd2dsolidcolorbrushm_psolidcolorbrush"></a><a name="m_psolidcolorbrush"></a>CD2Dソリッドカラーブラシ::m_pSolidColorBrush

オブジェクトを ID2D1SolidColorBrush オブジェクトへのポインターを格納します。

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

## <a name="cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a>CD2Dソリッドカラーブラシ::オペレーターID2D1ソリッドカラーブラシ*

インターフェイスを返します。

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>戻り値

ID2D1SolidColorBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a>CD2Dソリッドカラーブラシ::セットカラー

この単色ブラシの色を指定します。

```
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
この単色ブラシの色

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
