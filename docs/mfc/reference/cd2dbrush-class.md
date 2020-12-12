---
description: '詳細情報: CD2DBrush クラス'
title: CD2DBrush クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
ms.openlocfilehash: 6d19601258951a297a734aa304e2a22c98baf5c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227573"
---
# <a name="cd2dbrush-class"></a>CD2DBrush クラス

ID2D1Brush のラッパー。

## <a name="syntax"></a>構文

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DBrush:: CD2DBrush](#cd2dbrush)|CD2DBrush オブジェクトを構築します。|
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|デストラクターです。 D2D brush オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DBrush:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DBrush::D estroy](#destroy)|CD2DBrush オブジェクトを破棄します。 ( [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。)|
|[CD2DBrush::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DBrush:: Get](#get)|ID2D1Brush インターフェイスを返します。|
|[CD2DBrush:: GetOpacity しくみ](#getopacity)|このブラシの不透明度を取得します。|
|[CD2DBrush:: GetTransform](#gettransform)|レンダーターゲットの現在の変換を取得します。|
|[CD2DBrush:: IsValid](#isvalid)|リソースの有効性を確認します ( [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)をオーバーライドします)。|
|[CD2DBrush:: SetOpacity しくみ](#setopacity)|このブラシの不透明度を設定します|
|[CD2DBrush:: SetTransform](#settransform)|指定された変換をレンダーターゲットに適用し、既存の変換を置き換えます。 それ以降のすべての描画操作は、変換された領域で発生します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DBrush:: operator ID2D1Brush *](#operator_id2d1brush_star)|ID2D1Brush インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DBrush:: m_pBrush](#m_pbrush)|ID2D1Brush オブジェクトへのポインターを格納します。|
|[CD2DBrush:: m_pBrushProperties](#m_pbrushproperties)|ブラシのプロパティ。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a> CD2DBrush:: ~ CD2DBrush

デストラクターです。 D2D brush オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a> CD2DBrush:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 Nll は指定できません。

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a> CD2DBrush:: CD2DBrush

CD2DBrush オブジェクトを構築します。

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*pBrushProperties*<br/>
ブラシの不透明度と変換へのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a> CD2DBrush::D estroy

CD2DBrush オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a> CD2DBrush::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dbrushget"></a><a name="get"></a> CD2DBrush:: Get

ID2D1Brush インターフェイスを返します。

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Brush インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a> CD2DBrush:: GetOpacity しくみ

このブラシの不透明度を取得します。

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>戻り値

ブラシの不透明度を示す 0 ~ 1 の値。 この値は、ブラシで塗りつぶされたすべてのピクセルのアルファ値を線形にスケーリングする定数乗数です。 不透明度の値は、0 ~ 1 の範囲で、乗算される前にクランプされます。

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a> CD2DBrush:: GetTransform

レンダーターゲットの現在の変換を取得します。

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>パラメーター

*transform*<br/>
このが返されるときに、レンダーターゲットの現在の変換を格納します。 このパラメーターは初期化せずに渡されます。

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a> CD2DBrush:: IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a> CD2DBrush:: m_pBrush

ID2D1Brush オブジェクトへのポインターを格納します。

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a> CD2DBrush:: m_pBrushProperties

ブラシのプロパティ。

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a> CD2DBrush:: operator ID2D1Brush *

ID2D1Brush インターフェイスを返します。

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>戻り値

ID2D1Brush インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a> CD2DBrush:: SetOpacity しくみ

このブラシの不透明度を設定します

```cpp
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>パラメーター

*透過*<br/>
ブラシの不透明度を示す 0 ~ 1 の値。 この値は、ブラシで塗りつぶされたすべてのピクセルのアルファ値を線形にスケーリングする定数乗数です。 不透明度の値は、0 ~ 1 の範囲で、乗算される前にクランプされます。

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a> CD2DBrush:: SetTransform

指定された変換をレンダーターゲットに適用し、既存の変換を置き換えます。 それ以降のすべての描画操作は、変換された領域で発生します。

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>パラメーター

*transform*<br/>
レンダーターゲットに適用する変換。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
