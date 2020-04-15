---
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
ms.openlocfilehash: aa6fb313bfcc2983f167936e5ad4f78be1e17a44
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369215"
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
|[CD2Dレイヤー::CD2Dレイヤー](#cd2dlayer)|CD2DLayer オブジェクトを構築します。|
|[CD2Dレイヤー::~CD2Dレイヤー](#_dtorcd2dlayer)|デストラクターです。 D2D レイヤー オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dレイヤー::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dレイヤー::作成](#create)|CD2D レイヤーを作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dレイヤー::Dエストロイ](#destroy)|CD2DLayer オブジェクトを破棄します。 [(CD2D リソース::Dエストロイ](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。|
|[CD2Dレイヤー::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dレイヤー::取得](#get)|ID2D1Layer インターフェイスを返します。|
|[CD2Dレイヤー::ゲットサイズ](#getsize)|レンダー ターゲットのサイズをデバイスに依存しないピクセル単位で返します。|
|[CD2Dレイヤー::イズバリ](#isvalid)|リソースの妥当性を確認します[(CD2D リソースをオーバーライドします::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2Dレイヤー::オペレーターID2D1レイヤー*](#operator_id2d1layer_star)|ID2D1Layer インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dレイヤー:m_pLayer](#m_player)|ID2D1Layer オブジェクトへのポインターを格納します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

`CD2DLayer`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dlayercd2dlayer"></a><a name="_dtorcd2dlayer"></a>CD2Dレイヤー::~CD2Dレイヤー

デストラクターです。 D2D レイヤー オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DLayer();
```

## <a name="cd2dlayerattach"></a><a name="attach"></a>CD2Dレイヤー::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1Layer* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dlayercd2dlayer"></a><a name="cd2dlayer"></a>CD2Dレイヤー::CD2Dレイヤー

CD2DLayer オブジェクトを構築します。

```
CD2DLayer(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dlayercreate"></a><a name="create"></a>CD2Dレイヤー::作成

CD2D レイヤーを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dlayerdestroy"></a><a name="destroy"></a>CD2Dレイヤー::Dエストロイ

CD2DLayer オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dlayerdetach"></a><a name="detach"></a>CD2Dレイヤー::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1Layer* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dlayerget"></a><a name="get"></a>CD2Dレイヤー::取得

ID2D1Layer インターフェイスを返します。

```
ID2D1Layer* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Layer インターフェイスへのポインタ、またはオブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dlayergetsize"></a><a name="getsize"></a>CD2Dレイヤー::ゲットサイズ

レンダー ターゲットのサイズをデバイスに依存しないピクセル単位で返します。

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>戻り値

デバイスに依存しないピクセル単位のレンダー ターゲットの現在のサイズ

## <a name="cd2dlayerisvalid"></a><a name="isvalid"></a>CD2Dレイヤー::イズバリ

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dlayerm_player"></a><a name="m_player"></a>CD2Dレイヤー:m_pLayer

ID2D1Layer オブジェクトへのポインターを格納します。

```
ID2D1Layer* m_pLayer;
```

## <a name="cd2dlayeroperator-id2d1layer"></a><a name="operator_id2d1layer_star"></a>CD2Dレイヤー::オペレーターID2D1レイヤー*

ID2D1Layer インターフェイスを返します。

```
operator ID2D1Layer* ();
```

### <a name="return-value"></a>戻り値

ID2D1Layer インターフェイスへのポインタ、またはオブジェクトがまだ初期化されていない場合は NULL。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
