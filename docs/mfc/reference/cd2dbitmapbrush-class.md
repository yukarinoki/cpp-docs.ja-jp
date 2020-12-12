---
description: '詳細情報: CD2DBitmapBrush クラス'
title: CD2DBitmapBrush クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
ms.openlocfilehash: a9d4c1955b1318ecb273482cd49025090bf97d3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227586"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush クラス

ID2D1BitmapBrush のラッパー。

## <a name="syntax"></a>構文

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DBitmapBrush:: CD2DBitmapBrush](#cd2dbitmapbrush)|オーバーロードされます。 ファイルから CD2DBitmapBrush オブジェクトを構築します。|
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|デストラクターです。 D2D bitmap brush オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DBitmapBrush:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DBitmapBrush:: Create](#create)|CD2DBitmapBrush を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DBitmapBrush::D estroy](#destroy)|CD2DBitmapBrush オブジェクトを破棄します。 ( [CD2DBrush::D estroy](../../mfc/reference/cd2dbrush-class.md#destroy)をオーバーライドします。)|
|[CD2DBitmapBrush::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DBitmapBrush:: Get](#get)|ID2D1BitmapBrush インターフェイスを返します。|
|[CD2DBitmapBrush:: GetBitmap](#getbitmap)|このブラシが描画に使用するビットマップソースを取得します。|
|[CD2DBitmapBrush:: GetExtendModeX](#getextendmodex)|ブラシがビットマップの後ろにある領域を水平方向に並べて配置する方法を取得します。|
|[CD2DBitmapBrush:: GetExtendModeY](#getextendmodey)|ビットマップの外側を拡張する領域をブラシが垂直方向にタイルする方法を取得します。|
|[CD2DBitmapBrush:: GetInterpolationMode](#getinterpolationmode)|ブラシビットマップが拡大縮小または回転したときに使用される補間方式を取得します。|
|[CD2DBitmapBrush:: SetBitmap](#setbitmap)|このブラシが描画に使用するビットマップソースを指定します|
|[CD2DBitmapBrush:: SetExtendModeX](#setextendmodex)|ブラシがビットマップの後に拡張する領域を水平方向にタイルする方法を指定します。|
|[CD2DBitmapBrush:: SetExtendModeY](#setextendmodey)|ビットマップの外側を拡張する領域をブラシが垂直方向にタイルする方法を指定します。|
|[CD2DBitmapBrush:: SetInterpolationMode](#setinterpolationmode)|ブラシビットマップをスケールまたは回転するときに使用する補間モードを指定します|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2DBitmapBrush:: CommonInit](#commoninit)|オブジェクトを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DBitmapBrush:: operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|ID2D1BitmapBrush インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DBitmapBrush:: m_pBitmap](#m_pbitmap)|CD2DBitmap オブジェクトへのポインターを格納します。|
|[CD2DBitmapBrush:: m_pBitmapBrush](#m_pbitmapbrush)|ID2D1BitmapBrush オブジェクトへのポインターを格納します。|
|[CD2DBitmapBrush:: m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|ビットマップブラシのプロパティ。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a> CD2DBitmapBrush:: ~ CD2DBitmapBrush

デストラクターです。 D2D bitmap brush オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DBitmapBrush();
```

## <a name="cd2dbitmapbrushattach"></a><a name="attach"></a> CD2DBitmapBrush:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 NULL にすることはできません

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a> CD2DBitmapBrush:: CD2DBitmapBrush

CD2DBitmapBrush オブジェクトを構築します。

```
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszImagePath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*pBitmapBrushProperties*<br/>
ビットマップブラシの拡張モードと補間モードへのポインター。

*pBrushProperties*<br/>
ブラシの不透明度と変換へのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

*uiResID*<br/>
リソースのリソース ID 番号。

*lpszType*<br/>
リソースの種類を含む null で終わる文字列へのポインター。

*sizeDest*<br/>
ビットマップのターゲットサイズ。

*lpszImagePath*<br/>
ファイルの名前を含む null で終わる文字列へのポインター。

## <a name="cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a> CD2DBitmapBrush:: CommonInit

オブジェクトを初期化します。

```cpp
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>パラメーター

*pBitmapBrushProperties*<br/>
ビットマップブラシのプロパティへのポインター。

## <a name="cd2dbitmapbrushcreate"></a><a name="create"></a> CD2DBitmapBrush:: Create

CD2DBitmapBrush を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dbitmapbrushdestroy"></a><a name="destroy"></a> CD2DBitmapBrush::D estroy

CD2DBitmapBrush オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dbitmapbrushdetach"></a><a name="detach"></a> CD2DBitmapBrush::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dbitmapbrushget"></a><a name="get"></a> CD2DBitmapBrush:: Get

ID2D1BitmapBrush インターフェイスを返します。

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1BitmapBrush インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a> CD2DBitmapBrush:: GetBitmap

このブラシが描画に使用するビットマップソースを取得します。

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>戻り値

CD2DBitmap オブジェクトへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a> CD2DBitmapBrush:: GetExtendModeX

ブラシがビットマップの後ろにある領域を水平方向に並べて配置する方法を取得します。

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>戻り値

ビットマップの前に拡張する領域をブラシで水平方向にタイルする方法を指定する値。

## <a name="cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a> CD2DBitmapBrush:: GetExtendModeY

ビットマップの外側を拡張する領域をブラシが垂直方向にタイルする方法を取得します。

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>戻り値

ビットマップの外側を拡張する領域をブラシが垂直方向にタイルする方法を指定する値。

## <a name="cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a> CD2DBitmapBrush:: GetInterpolationMode

ブラシビットマップが拡大縮小または回転したときに使用される補間方式を取得します。

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>戻り値

ブラシビットマップのスケールまたは回転時に使用される補間方式

## <a name="cd2dbitmapbrushm_pbitmap"></a><a name="m_pbitmap"></a> CD2DBitmapBrush:: m_pBitmap

CD2DBitmap オブジェクトへのポインターを格納します。

```
CD2DBitmap* m_pBitmap;
```

## <a name="cd2dbitmapbrushm_pbitmapbrush"></a><a name="m_pbitmapbrush"></a> CD2DBitmapBrush:: m_pBitmapBrush

ID2D1BitmapBrush オブジェクトへのポインターを格納します。

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

## <a name="cd2dbitmapbrushm_pbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a> CD2DBitmapBrush:: m_pBitmapBrushProperties

ビットマップブラシのプロパティ。

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

## <a name="cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a> CD2DBitmapBrush:: operator ID2D1BitmapBrush *

ID2D1BitmapBrush インターフェイスを返します。

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>戻り値

ID2D1BitmapBrush インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a> CD2DBitmapBrush:: SetBitmap

このブラシが描画に使用するビットマップソースを指定します

```cpp
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

*pBitmap*<br/>
ブラシによって使用されるビットマップソース

## <a name="cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a> CD2DBitmapBrush:: SetExtendModeX

ブラシがビットマップの後に拡張する領域を水平方向にタイルする方法を指定します。

```cpp
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>パラメーター

*extendModeX*<br/>
ビットマップの前に拡張する領域をブラシで水平方向にタイルする方法を指定する値。

## <a name="cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a> CD2DBitmapBrush:: SetExtendModeY

ビットマップの外側を拡張する領域をブラシが垂直方向にタイルする方法を指定します。

```cpp
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>パラメーター

*extendModeY*<br/>
ビットマップの外側を拡張する領域をブラシが垂直方向にタイルする方法を指定する値。

## <a name="cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a> CD2DBitmapBrush:: SetInterpolationMode

ブラシビットマップをスケールまたは回転するときに使用する補間モードを指定します

```cpp
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>パラメーター

*interpolationMode*<br/>
ブラシビットマップのスケールまたは回転時に使用される補間モード

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
