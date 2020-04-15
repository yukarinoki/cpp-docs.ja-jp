---
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
ms.openlocfilehash: e26202392bf4783598aec0dddfea514fce806a8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369296"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush クラス

ID2D1 ビットマップ ブラシのラッパー。

## <a name="syntax"></a>構文

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2D ビットマップブラシ::CD2D ビットマップブラシ](#cd2dbitmapbrush)|オーバーロードされます。 ファイルから CD2DBitmapBrush オブジェクトを構築します。|
|[CD2D ビットマップブラシ:~CD2D ビットマップブラシ](#dtor)|デストラクターです。 D2D ビットマップ ブラシ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dビットマップブラシ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dビットマップブラシ::作成](#create)|CD2D ビットマップブラシを作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dビットマップブラシ::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2Dブラシ::Dエストロイ](../../mfc/reference/cd2dbrush-class.md#destroy)をオーバーライドします。|
|[CD2Dビットマップブラシ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dビットマップブラシ::取得](#get)|インターフェイスを返します。|
|[ビットマップブラシを取得します。](#getbitmap)|このブラシが描画に使用するビットマップ ソースを取得します。|
|[を使用します。](#getextendmodex)|ブラシがビットマップを越えて伸びる領域を水平方向に並べて表示するメソッドを取得します。|
|[CD2Dビットマップブラシ::GetExtendModeY](#getextendmodey)|ブラシがビットマップを越えて伸びる領域を垂直方向に並べて表示するメソッドを取得します。|
|[CD2Dビットマップブラシ::補間モードを取得します。](#getinterpolationmode)|ブラシ ビットマップの拡大縮小または回転時に使用される補間方法を取得します。|
|[CD2D ビットマップブラシ::ビットマップを設定します。](#setbitmap)|このブラシが描画に使用するビットマップ ソースを指定します。|
|[を使用します。](#setextendmodex)|ブラシがビットマップを越えて伸びる領域を水平に並べて表示する方法を指定します。|
|[CD2Dビットマップブラシ::セットエクステンドモード](#setextendmodey)|ブラシがビットマップを越えて伸びる領域を垂直方向に並べて表示する方法を指定します。|
|[CD2Dビットマップブラシ::補間モードの設定](#setinterpolationmode)|ブラシ ビットマップの拡大/縮小または回転時に使用する補間モードを指定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dビットマップブラシ::コモンイニト](#commoninit)|オブジェクトを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2D ビットマップブラシ::演算子 ID2D1ビットマップブラシ*](#operator_id2d1bitmapbrush_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dビットマップブラシ::m_pBitmap](#m_pbitmap)|CD2DBitmap オブジェクトへのポインターを格納します。|
|[CD2Dビットマップブラシ::m_pBitmapBrush](#m_pbitmapbrush)|オブジェクトを指すポインターを格納します。|
|[CD2Dビットマップブラシ::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|ビットマップ ブラシのプロパティ。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[CD2Dブラシ](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a>CD2D ビットマップブラシ:~CD2D ビットマップブラシ

デストラクターです。 D2D ビットマップ ブラシ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DBitmapBrush();
```

## <a name="cd2dbitmapbrushattach"></a><a name="attach"></a>CD2Dビットマップブラシ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a>CD2D ビットマップブラシ::CD2D ビットマップブラシ

オブジェクトを構築します。

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

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*プロパティ*<br/>
ビットマップ ブラシの拡張モードと補間モードへのポインター。

*プロパティ*<br/>
ブラシの不透明度と変換へのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

*UIResID*<br/>
リソースのリソース ID 番号。

*lpsz タイプ*<br/>
リソースの種類を含む null で終わる文字列へのポインター。

*サイズ最も大きな*<br/>
ビットマップのコピー先のサイズ。

*パス*<br/>
ファイル名を含む null で終わる文字列へのポインター。

## <a name="cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a>CD2Dビットマップブラシ::コモンイニト

オブジェクトを初期化します。

```
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>パラメーター

*プロパティ*<br/>
ビットマップ ブラシのプロパティへのポインター。

## <a name="cd2dbitmapbrushcreate"></a><a name="create"></a>CD2Dビットマップブラシ::作成

CD2D ビットマップブラシを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dbitmapbrushdestroy"></a><a name="destroy"></a>CD2Dビットマップブラシ::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dbitmapbrushdetach"></a><a name="detach"></a>CD2Dビットマップブラシ::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dbitmapbrushget"></a><a name="get"></a>CD2Dビットマップブラシ::取得

インターフェイスを返します。

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>戻り値

ID2D1BitmapBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a>ビットマップブラシを取得します。

このブラシが描画に使用するビットマップ ソースを取得します。

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>戻り値

CD2DBitmap オブジェクトへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a>を使用します。

ブラシがビットマップを越えて伸びる領域を水平方向に並べて表示するメソッドを取得します。

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>戻り値

ビットマップを越えて伸びる領域をブラシで水平に並べて表示する方法を指定する値

## <a name="cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a>CD2Dビットマップブラシ::GetExtendModeY

ブラシがビットマップを越えて伸びる領域を垂直方向に並べて表示するメソッドを取得します。

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>戻り値

ビットマップを越えて伸びる領域をブラシで上下に並べて表示する方法を指定する値

## <a name="cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a>CD2Dビットマップブラシ::補間モードを取得します。

ブラシ ビットマップの拡大縮小または回転時に使用される補間方法を取得します。

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>戻り値

ブラシ ビットマップの拡大縮小または回転時に使用する補間方法

## <a name="cd2dbitmapbrushm_pbitmap"></a><a name="m_pbitmap"></a>CD2Dビットマップブラシ::m_pBitmap

CD2DBitmap オブジェクトへのポインターを格納します。

```
CD2DBitmap* m_pBitmap;
```

## <a name="cd2dbitmapbrushm_pbitmapbrush"></a><a name="m_pbitmapbrush"></a>CD2Dビットマップブラシ::m_pBitmapBrush

オブジェクトを指すポインターを格納します。

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

## <a name="cd2dbitmapbrushm_pbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a>CD2Dビットマップブラシ::m_pBitmapBrushProperties

ビットマップ ブラシのプロパティ。

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

## <a name="cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a>CD2D ビットマップブラシ::演算子 ID2D1ビットマップブラシ*

インターフェイスを返します。

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>戻り値

ID2D1BitmapBrush インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a>CD2D ビットマップブラシ::ビットマップを設定します。

このブラシが描画に使用するビットマップ ソースを指定します。

```
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
ブラシで使用されるビットマップ ソース

## <a name="cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a>を使用します。

ブラシがビットマップを越えて伸びる領域を水平に並べて表示する方法を指定します。

```
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>パラメーター

*拡張モードX*<br/>
ビットマップを越えて伸びる領域をブラシで水平に並べて表示する方法を指定する値

## <a name="cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a>CD2Dビットマップブラシ::セットエクステンドモード

ブラシがビットマップを越えて伸びる領域を垂直方向に並べて表示する方法を指定します。

```
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>パラメーター

*拡張モード*<br/>
ビットマップを越えて伸びる領域をブラシで上下に並べて表示する方法を指定する値

## <a name="cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a>CD2Dビットマップブラシ::補間モードの設定

ブラシ ビットマップの拡大/縮小または回転時に使用する補間モードを指定します。

```
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>パラメーター

*補間モード*<br/>
ブラシ ビットマップの拡大縮小または回転時に使用する補間モード

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
