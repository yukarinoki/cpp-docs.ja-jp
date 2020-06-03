---
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
ms.openlocfilehash: 536d84fe2c2f68d62490e1ce2b65085426762e87
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754198"
---
# <a name="cd2dbrush-class"></a>CD2DBrush クラス

ID2D1 ブラシのラッパー。

## <a name="syntax"></a>構文

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dブラシ::CD2Dブラシ](#cd2dbrush)|CD2DBrush オブジェクトを構築します。|
|[CD2Dブラシ::〜CD2Dブラシ](#_dtorcd2dbrush)|デストラクターです。 D2D ブラシ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dブラシ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dブラシ::Dエストロイ](#destroy)|CD2DBrush オブジェクトを破棄します。 [(CD2D リソース::Dエストロイ](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。|
|[CD2Dブラシ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dブラシ::ゲット](#get)|ID2D1Brush インターフェイスを返します。|
|[CD2Dブラシ::ゲモパシティ](#getopacity)|このブラシの不透明度を取得します。|
|[CD2Dブラシ::変換を取得します。](#gettransform)|レンダー ターゲットの現在の変換を取得します。|
|[CD2Dブラシ::イズ有効](#isvalid)|リソースの妥当性を確認します[(CD2D リソースをオーバーライドします::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2Dブラシ::セタピシティ](#setopacity)|このブラシの不透明度を設定します。|
|[CD2Dブラシ::変換を設定します。](#settransform)|指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。 後続のすべての描画操作は、変換後の空間で行われます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2Dブラシ::オペレーターID2D1ブラシ*](#operator_id2d1brush_star)|ID2D1Brush インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dブラシ::m_pBrush](#m_pbrush)|ID2D1Brush オブジェクトへのポインターを格納します。|
|[CD2Dブラシ::m_pBrushProperties](#m_pbrushproperties)|ブラシのプロパティ。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a>CD2Dブラシ::〜CD2Dブラシ

デストラクターです。 D2D ブラシ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a>CD2Dブラシ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 Nll は指定できません。

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a>CD2Dブラシ::CD2Dブラシ

CD2DBrush オブジェクトを構築します。

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*プロパティ*<br/>
ブラシの不透明度と変換へのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a>CD2Dブラシ::Dエストロイ

CD2DBrush オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a>CD2Dブラシ::Dエタッハ

オブジェクトからリソース インターフェイスをデタッチします。

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dbrushget"></a><a name="get"></a>CD2Dブラシ::ゲット

ID2D1Brush インターフェイスを返します。

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Brush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a>CD2Dブラシ::ゲモパシティ

このブラシの不透明度を取得します。

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>戻り値

ブラシの不透明度を示す 0 ~ 1 の値。 この値は、ブラシによって塗りつぶされたすべてのピクセルのアルファ値を直線的にスケーリングする定数乗数です。 不透明度の値は、乗算される前に 0 から 1 の範囲でクランプされます。

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a>CD2Dブラシ::変換を取得します。

レンダー ターゲットの現在の変換を取得します。

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>パラメーター

*transform*<br/>
これが返されるときに、レンダー ターゲットの現在の変換を格納します。 このパラメーターは初期化せずに渡されます。

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a>CD2Dブラシ::イズ有効

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a>CD2Dブラシ::m_pBrush

ID2D1Brush オブジェクトへのポインターを格納します。

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a>CD2Dブラシ::m_pBrushProperties

ブラシのプロパティ。

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a>CD2Dブラシ::オペレーターID2D1ブラシ*

ID2D1Brush インターフェイスを返します。

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>戻り値

ID2D1Brush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a>CD2Dブラシ::セタピシティ

このブラシの不透明度を設定します。

```cpp
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>パラメーター

*不透明 度*<br/>
ブラシの不透明度を示す 0 ~ 1 の値。 この値は、ブラシによって塗りつぶされたすべてのピクセルのアルファ値を直線的にスケーリングする定数乗数です。 不透明度の値は、乗算される前に 0 から 1 の範囲でクランプされます。

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a>CD2Dブラシ::変換を設定します。

指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。 それ以降の描画操作はすべて、変換された空間で行われます。

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>パラメーター

*transform*<br/>
レンダー ターゲットに適用する変換

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
