---
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
ms.openlocfilehash: 6249c121f7bcca0675a8138baef0e2cdc9e632d8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352598"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget クラス

ID2D1ビットマップレンダーターゲットのラッパー。

## <a name="syntax"></a>構文

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#cbitmaprendertarget)|オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#attach)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|
|[レンダリングターゲット::Dエタッハ](#detach)|オブジェクトからレンダー ターゲット インターフェイスをデタッチします。|
|[をクリックします。](#getbitmap)|このレンダー ターゲットのビットマップを取得します。 返されたビットマップは、描画操作に使用できます。|
|[をクリックします。](#getbitmaprendertarget)|インターフェイスを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を示す値を指定します。](#operator_id2d1bitmaprendertarget_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[オブジェクトを描画します。:m_pBitmapRenderTarget](#m_pbitmaprendertarget)|オブジェクトへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[クレンダターゲット](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a>をクリックします。

既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>パラメーター

*pターゲット*<br/>
既存のレンダー ターゲット インターフェイス。 NULL にすることはできません。

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a>をクリックします。

オブジェクトを構築します。

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a>レンダリングターゲット::Dエタッハ

オブジェクトからレンダー ターゲット インターフェイスをデタッチします。

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたレンダー ターゲット インターフェイスへのポインター。

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a>をクリックします。

このレンダー ターゲットのビットマップを取得します。 返されたビットマップは、描画操作に使用できます。

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
このメソッドが返されるときに、このレンダー ターゲットに有効なビットマップを格納します。 このビットマップは、描画操作に使用できます。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a>をクリックします。

インターフェイスを返します。

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>戻り値

オブジェクトがまだ初期化されていない場合は、ID2D1BitmapRenderTarget インターフェイスへのポインターまたは NULL。

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a>オブジェクトを描画します。:m_pBitmapRenderTarget

オブジェクトへのポインター。

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a>を示す値を指定します。

インターフェイスを返します。

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>戻り値

オブジェクトがまだ初期化されていない場合は、ID2D1BitmapRenderTarget インターフェイスへのポインターまたは NULL。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
