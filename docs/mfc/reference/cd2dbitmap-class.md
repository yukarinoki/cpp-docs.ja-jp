---
description: '詳細情報: CD2DBitmap クラス'
title: CD2DBitmap クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
ms.openlocfilehash: ab023caa92683b24098db1a03d081922e3dfd48b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227651"
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap クラス

ID2D1Bitmap のラッパー。

## <a name="syntax"></a>構文

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DBitmap:: CD2DBitmap](#cd2dbitmap)|オーバーロードされます。 HBITMAP から CD2DBitmap オブジェクトを構築します。|
|[CD2DBitmap:: ~ CD2DBitmap](#_dtorcd2dbitmap)|デストラクターです。 D2D bitmap オブジェクトが破棄されるときに呼び出されます。|

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DBitmap:: CD2DBitmap](#cd2dbitmap)|オーバーロードされます。 CD2DBitmap オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DBitmap:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DBitmap:: CopyFromBitmap](#copyfrombitmap)|指定したビットマップから現在のビットマップに、指定した領域をコピーします。|
|[CD2DBitmap:: CopyFromMemory](#copyfrommemory)|指定された領域をメモリから現在のビットマップにコピーします。|
|[CD2DBitmap:: CopyFromRenderTarget](#copyfromrendertarget)|指定したレンダーターゲットから現在のビットマップに、指定した領域をコピーします。|
|[CD2DBitmap:: Create](#create)|CD2DBitmap を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DBitmap::D estroy](#destroy)|CD2DBitmap オブジェクトを破棄します。 ( [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。)|
|[CD2DBitmap::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DBitmap:: Get](#get)|ID2D1Bitmap インターフェイスを返します。|
|[CD2DBitmap:: GetDPI](#getdpi)|ビットマップのドット/インチ (DPI) を返す|
|[CD2DBitmap:: Getピクセル形式](#getpixelformat)|ビットマップのピクセル形式とアルファモードを取得します。|
|[CD2DBitmap:: Getピクセルサイズ](#getpixelsize)|ビットマップのサイズをデバイスに依存する単位 (ピクセル) 単位で返します。|
|[CD2DBitmap:: GetSize](#getsize)|ビットマップのサイズをデバイスに依存しないピクセル (Dip) で返します。|
|[CD2DBitmap:: IsValid](#isvalid)|リソースの有効性を確認します ( [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)をオーバーライドします)。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2DBitmap:: CommonInit](#commoninit)|オブジェクトを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DBitmap:: operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|ID2D1Bitmap インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DBitmap:: m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|M_hBmpSrc を破棄する必要がある場合は TRUE。それ以外の場合は FALSE。|
|[CD2DBitmap:: m_hBmpSrc](#m_hbmpsrc)|ソースビットマップハンドル。|
|[CD2DBitmap:: m_lpszType](#m_lpsztype)|リソースの種類。|
|[CD2DBitmap:: m_pBitmap](#m_pbitmap)|ID2D1Bitmap オブジェクトへのポインターを格納します。|
|[CD2DBitmap:: m_sizeDest](#m_sizedest)|ビットマップの変換先のサイズ。|
|[CD2DBitmap:: m_strPath](#m_strpath)|Botmap ファイルパス。|
|[CD2DBitmap:: m_uiResID](#m_uiresid)|ビットマップリソース ID。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a> CD2DBitmap:: ~ CD2DBitmap

デストラクターです。 D2D bitmap オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a> CD2DBitmap:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 Nll は指定できません。

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a> CD2DBitmap:: CD2DBitmap

リソースから CD2DBitmap オブジェクトを構築します。

```
CD2DBitmap(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszPath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    HBITMAP hbmpSrc,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*uiResID*<br/>
リソースのリソース ID 番号。

*lpszType*<br/>
リソースの種類を含む null で終わる文字列へのポインター。

*sizeDest*<br/>
ビットマップのターゲットサイズ。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

*lpszPath*<br/>
ファイルの名前を含む null で終わる文字列へのポインター。

*hbmpSrc*<br/>
ビットマップをハンドルします。

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a> CD2DBitmap:: CommonInit

オブジェクトを初期化します。

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a> CD2DBitmap:: CopyFromBitmap

指定したビットマップから現在のビットマップに、指定した領域をコピーします。

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pBitmap*<br/>
コピー元のビットマップ。

*destPoint*<br/>
現在のビットマップでは、srcRect によって指定された領域の左上隅がコピーされます。

*srcRect*<br/>
コピーするビットマップの領域。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a> CD2DBitmap:: CopyFromMemory

指定された領域をメモリから現在のビットマップにコピーします。

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>パラメーター

*srcData*<br/>
コピーするデータ。

*送り*<br/>
SrcData に格納されているソースビットマップのストライド (ピッチ)。 Stride は、scanline (メモリ内の1行のピクセル) のバイト数です。 Stride は、ピクセルあたりのピクセル幅の \* バイト数 + メモリの余白という式から計算できます。

*destRect*<br/>
現在のビットマップでは、srcRect によって指定された領域の左上隅がコピーされます。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a> CD2DBitmap:: CopyFromRenderTarget

指定したレンダーターゲットから、指定した領域を現在のビットマップにコピーします。

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
コピーする領域を格納しているレンダーターゲット。

*destPoint*<br/>
現在のビットマップでは、srcRect によって指定された領域の左上隅がコピーされます。

*srcRect*<br/>
コピーする作りの領域。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dbitmapcreate"></a><a name="create"></a> CD2DBitmap:: Create

CD2DBitmap を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a> CD2DBitmap::D estroy

CD2DBitmap オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a> CD2DBitmap::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dbitmapget"></a><a name="get"></a> CD2DBitmap:: Get

ID2D1Bitmap インターフェイスを返します。

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Bitmap インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a> CD2DBitmap:: GetDPI

ビットマップの dpi (1 インチあたりのドット数) を返します。

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>戻り値

ビットマップの水平および垂直 DPI。

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a> CD2DBitmap:: Getピクセル形式

ビットマップのピクセル形式とアルファモードを取得します。

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>戻り値

ビットマップのピクセル形式とアルファモード。

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a> CD2DBitmap:: Getピクセルサイズ

ビットマップのサイズをデバイスに依存する単位 (ピクセル) 単位で返します。

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>戻り値

ビットマップのサイズ (ピクセル単位)。

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a> CD2DBitmap:: GetSize

ビットマップのサイズをデバイスに依存しないピクセル (Dip) で返します。

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>戻り値

ビットマップのサイズ (Dip 単位)。

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a> CD2DBitmap:: IsValid

リソースの有効性を確認します。

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a> CD2DBitmap:: m_bAutoDestroyHBMP

M_hBmpSrc を破棄する必要がある場合は TRUE。それ以外の場合は FALSE。

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a> CD2DBitmap:: m_hBmpSrc

ソースビットマップハンドル。

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a> CD2DBitmap:: m_lpszType

リソースの種類。

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a> CD2DBitmap:: m_pBitmap

ID2D1Bitmap オブジェクトへのポインターを格納します。

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a> CD2DBitmap:: m_sizeDest

ビットマップの変換先のサイズ。

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a> CD2DBitmap:: m_strPath

Botmap ファイルパス。

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a> CD2DBitmap:: m_uiResID

ビットマップリソース ID。

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a> CD2DBitmap:: operator ID2D1Bitmap *

ID2D1Bitmap インターフェイスを返します。

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>戻り値

ID2D1Bitmap インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
