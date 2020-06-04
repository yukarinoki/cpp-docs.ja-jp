---
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
ms.openlocfilehash: a3cabb00ded7dbc5f9c396a1de767058443a4436
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754208"
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
|[CD2D ビットマップ::CD2D ビットマップ](#cd2dbitmap)|オーバーロードされます。 HBITMAP から CD2DBitmap オブジェクトを構築します。|
|[CD2D ビットマップ::~CD2D ビットマップ](#_dtorcd2dbitmap)|デストラクターです。 D2D ビットマップ オブジェクトが破棄されるときに呼び出されます。|

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2D ビットマップ::CD2D ビットマップ](#cd2dbitmap)|オーバーロードされます。 オブジェクトを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2D ビットマップ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[ビットマップからコピーします。](#copyfrombitmap)|指定したビットマップから指定した領域を現在のビットマップにコピーします。|
|[メモリからコピーします。](#copyfrommemory)|指定した領域をメモリから現在のビットマップにコピーします。|
|[ソースのコピーを作成します。](#copyfromrendertarget)|指定したレンダー ターゲットから現在のビットマップに指定した領域をコピーします。|
|[CD2D ビットマップ::作成](#create)|CD2D ビットマップを作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2D ビットマップ::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2D リソース::Dエストロイ](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。|
|[CD2Dビットマップ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2D ビットマップ::取得します。](#get)|ID2D1 ビットマップ インターフェイスを返します。|
|[CD2D ビットマップ::ゲットドピ](#getdpi)|ビットマップの 1 インチあたりのドット数 (DPI) を返します。|
|[CD2D ビットマップ::ピクセルフォーマット](#getpixelformat)|ビットマップのピクセル形式とアルファ モードを取得します。|
|[ビットマップを使用します。](#getpixelsize)|ビットマップのサイズをデバイスに依存する単位 (ピクセル) で返します。|
|[CD2D ビットマップ::ゲットサイズ](#getsize)|ビットマップのサイズをデバイスに依存しないピクセル (DIP) で返します。|
|[CD2D ビットマップ::IsValid](#isvalid)|リソースの妥当性を確認します[(CD2D リソースをオーバーライドします::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dビットマップ::コモンイニト](#commoninit)|オブジェクトを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2D ビットマップ:: 演算子 ID2D1 ビットマップ*](#operator_id2d1bitmap_star)|ID2D1 ビットマップ インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2D ビットマップ:m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|m_hBmpSrc破棄する場合は TRUE。それ以外の場合は FALSE。|
|[CD2D ビットマップ::m_hBmpSrc](#m_hbmpsrc)|ソース ビットマップ ハンドル。|
|[CD2D ビットマップ:m_lpszType](#m_lpsztype)|リソースの種類。|
|[CD2D ビットマップ:m_pBitmap](#m_pbitmap)|ID2D1Bitmap オブジェクトへのポインターを格納します。|
|[CD2D ビットマップ::m_sizeDest](#m_sizedest)|ビットマップの出力先のサイズ。|
|[CD2D ビットマップ:m_strPath](#m_strpath)|ボットマップ ファイルのパス。|
|[CD2D ビットマップ:m_uiResID](#m_uiresid)|ビットマップ リソース ID。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a>CD2D ビットマップ::~CD2D ビットマップ

デストラクターです。 D2D ビットマップ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a>CD2D ビットマップ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 Nll は指定できません。

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a>CD2D ビットマップ::CD2D ビットマップ

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

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*UIResID*<br/>
リソースのリソース ID 番号。

*lpsz タイプ*<br/>
リソースの種類を含む null で終わる文字列へのポインター。

*サイズ最も大きな*<br/>
ビットマップのコピー先のサイズ。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

*パス*<br/>
ファイル名を含む null で終わる文字列へのポインター。

*hbmpSrc*<br/>
ビットマップへのハンドル。

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a>CD2Dビットマップ::コモンイニト

オブジェクトを初期化します。

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a>ビットマップからコピーします。

指定したビットマップから指定した領域を現在のビットマップにコピーします。

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
コピー元のビットマップ。

*デストポイント*<br/>
現在のビットマップで、srcRect で指定した領域がコピーされる領域の左上隅。

*srcRect*<br/>
コピーするビットマップの領域。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a>メモリからコピーします。

指定した領域をメモリから現在のビットマップにコピーします。

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>パラメーター

*srcデータ*<br/>
コピーするデータ。

*ピッチ*<br/>
srcData に格納されているソース ビットマップのストライド(ピッチ)です。 stride はスキャンラインのバイト数 (メモリ内のピクセルの 1 行) です。 stride は、ピクセルごとのピクセル幅\*バイト + メモリパディングの式から計算できます。

*デストレクト*<br/>
現在のビットマップで、srcRect で指定した領域がコピーされる領域の左上隅。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a>ソースのコピーを作成します。

指定したレンダー ターゲットから指定した領域を現在のビットマップにコピーします。

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
コピーする領域を含むレンダー ターゲット。

*デストポイント*<br/>
現在のビットマップで、srcRect で指定した領域がコピーされる領域の左上隅。

*srcRect*<br/>
コピーするレンダー ターゲットの領域。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dbitmapcreate"></a><a name="create"></a>CD2D ビットマップ::作成

CD2D ビットマップを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a>CD2D ビットマップ::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a>CD2Dビットマップ::Dエタッハ

オブジェクトからリソース インターフェイスをデタッチします。

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dbitmapget"></a><a name="get"></a>CD2D ビットマップ::取得します。

ID2D1Bitmap インターフェイスを返します。

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Bitmap インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a>CD2D ビットマップ::ゲットドピ

ビットマップのドット/インチ (DPI) を返します。

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>戻り値

ビットマップの水平方向および垂直方向の DPI。

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a>CD2D ビットマップ::ピクセルフォーマット

ビットマップのピクセル形式とアルファ モードを取得します。

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>戻り値

ビットマップのピクセル形式とアルファ モード。

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a>ビットマップを使用します。

ビットマップのサイズをデバイスに依存する単位 (ピクセル) で返します。

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>戻り値

ビットマップのサイズ (ピクセル単位)。

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a>CD2D ビットマップ::ゲットサイズ

ビットマップのサイズをデバイスに依存しないピクセル (DIP) で返します。

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>戻り値

ビットマップのサイズ (DIP 単位)。

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a>CD2D ビットマップ::IsValid

リソースの有効性を確認します。

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a>CD2D ビットマップ:m_bAutoDestroyHBMP

m_hBmpSrc破棄する場合は TRUE。それ以外の場合は FALSE。

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a>CD2D ビットマップ::m_hBmpSrc

ソース ビットマップ ハンドル。

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a>CD2D ビットマップ:m_lpszType

リソースの種類。

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a>CD2D ビットマップ:m_pBitmap

ID2D1Bitmap オブジェクトへのポインターを格納します。

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a>CD2D ビットマップ::m_sizeDest

ビットマップの出力先のサイズ。

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a>CD2D ビットマップ:m_strPath

ボットマップ ファイルのパス。

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a>CD2D ビットマップ:m_uiResID

ビットマップ リソース ID。

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a>CD2D ビットマップ:: 演算子 ID2D1 ビットマップ*

ID2D1 ビットマップ インターフェイスを返します。

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>戻り値

ID2D1Bitmap インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
