---
description: '詳細情報: CD2DLayer クラス'
title: CD2DLayer クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
ms.openlocfilehash: bd41cd591e6422c9434cd84d20cb6e5d778410bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306951"
---
# <a name="cd2dlayer-class"></a>CD2DLayer クラス

ID2D1Layer のラッパー。

## <a name="syntax"></a>構文

```
class CD2DLayer : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DLayer:: CD2DLayer](#cd2dlayer)|CD2DLayer オブジェクトを構築します。|
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|デストラクターです。 D2D layer オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DLayer:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DLayer:: Create](#create)|CD2DLayer を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DLayer::D estroy](#destroy)|CD2DLayer オブジェクトを破棄します。 ( [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。)|
|[CD2DLayer::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DLayer:: Get](#get)|ID2D1Layer インターフェイスを返します。|
|[CD2DLayer:: GetSize](#getsize)|レンダリングターゲットのサイズをデバイスに依存しないピクセル単位で返します|
|[CD2DLayer:: IsValid](#isvalid)|リソースの有効性を確認します ( [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)をオーバーライドします)。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DLayer:: operator ID2D1Layer *](#operator_id2d1layer_star)|ID2D1Layer インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DLayer:: m_pLayer](#m_player)|ID2D1Layer オブジェクトへのポインターを格納します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dlayercd2dlayer"></a><a name="_dtorcd2dlayer"></a> CD2DLayer:: ~ CD2DLayer

デストラクターです。 D2D layer オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DLayer();
```

## <a name="cd2dlayerattach"></a><a name="attach"></a> CD2DLayer:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 NULL にすることはできません

## <a name="cd2dlayercd2dlayer"></a><a name="cd2dlayer"></a> CD2DLayer:: CD2DLayer

CD2DLayer オブジェクトを構築します。

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dlayercreate"></a><a name="create"></a> CD2DLayer:: Create

CD2DLayer を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dlayerdestroy"></a><a name="destroy"></a> CD2DLayer::D estroy

CD2DLayer オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dlayerdetach"></a><a name="detach"></a> CD2DLayer::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dlayerget"></a><a name="get"></a> CD2DLayer:: Get

ID2D1Layer インターフェイスを返します。

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Layer インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dlayergetsize"></a><a name="getsize"></a> CD2DLayer:: GetSize

レンダリングターゲットのサイズをデバイスに依存しないピクセル単位で返します

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>戻り値

レンダリングターゲットの現在のサイズ (デバイスに依存しないピクセル単位)

## <a name="cd2dlayerisvalid"></a><a name="isvalid"></a> CD2DLayer:: IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dlayerm_player"></a><a name="m_player"></a> CD2DLayer:: m_pLayer

ID2D1Layer オブジェクトへのポインターを格納します。

```
ID2D1Layer* m_pLayer;
```

## <a name="cd2dlayeroperator-id2d1layer"></a><a name="operator_id2d1layer_star"></a> CD2DLayer:: operator ID2D1Layer *

ID2D1Layer インターフェイスを返します。

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>戻り値

ID2D1Layer インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
