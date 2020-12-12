---
description: '詳細情報: CBitmapRenderTarget クラス'
title: CBitmapRenderTarget クラス
ms.date: 11/04/2016
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
ms.openlocfilehash: a7987651c988dcf7fcd4c4decf4a2bd474ab8619
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122682"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget クラス

ID2D1BitmapRenderTarget のラッパー。

## <a name="syntax"></a>構文

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CBitmapRenderTarget:: CBitmapRenderTarget](#cbitmaprendertarget)|CBitmapRenderTarget オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CBitmapRenderTarget:: Attach](#attach)|既存のレンダーターゲットインターフェイスをオブジェクトにアタッチします。|
|[CBitmapRenderTarget::D etach](#detach)|オブジェクトからレンダーターゲットインターフェイスをデタッチします|
|[CBitmapRenderTarget:: GetBitmap](#getbitmap)|このレンダーターゲットのビットマップを取得します。 返されたビットマップは描画操作に使用できます。|
|[CBitmapRenderTarget:: GetBitmapRenderTarget](#getbitmaprendertarget)|ID2D1BitmapRenderTarget インターフェイスを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CBitmapRenderTarget:: operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|ID2D1BitmapRenderTarget インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CBitmapRenderTarget:: m_pBitmapRenderTarget](#m_pbitmaprendertarget)|ID2D1BitmapRenderTarget オブジェクトへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a> CBitmapRenderTarget:: Attach

既存のレンダーターゲットインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>パラメーター

*pTarget*<br/>
既存のレンダーターゲットインターフェイス。 NULL にすることはできません

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a> CBitmapRenderTarget:: CBitmapRenderTarget

CBitmapRenderTarget オブジェクトを構築します。

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a> CBitmapRenderTarget::D etach

オブジェクトからレンダーターゲットインターフェイスをデタッチします

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたレンダーターゲットインターフェイスへのポインター。

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a> CBitmapRenderTarget:: GetBitmap

このレンダーターゲットのビットマップを取得します。 返されたビットマップは描画操作に使用できます。

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
このメソッドから制御が戻るときに、このレンダーターゲットの有効なビットマップを格納します。 このビットマップは描画操作に使用できます。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a> CBitmapRenderTarget:: GetBitmapRenderTarget

ID2D1BitmapRenderTarget インターフェイスを返します。

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>戻り値

ID2D1BitmapRenderTarget インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a> CBitmapRenderTarget:: m_pBitmapRenderTarget

ID2D1BitmapRenderTarget オブジェクトへのポインター。

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a> CBitmapRenderTarget:: operator ID2D1BitmapRenderTarget *

ID2D1BitmapRenderTarget インターフェイスを返します。

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>戻り値

ID2D1BitmapRenderTarget インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
