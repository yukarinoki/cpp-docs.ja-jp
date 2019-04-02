---
title: CDrawingManager クラス
ms.date: 11/04/2016
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
helpviewer_keywords:
- CDrawingManager [MFC], CDrawingManager
- CDrawingManager [MFC], CreateBitmap_32
- CDrawingManager [MFC], DrawAlpha
- CDrawingManager [MFC], DrawRotated
- CDrawingManager [MFC], DrawEllipse
- CDrawingManager [MFC], DrawGradientRing
- CDrawingManager [MFC], DrawRect
- CDrawingManager [MFC], DrawShadow
- CDrawingManager [MFC], Fill4ColorsGradient
- CDrawingManager [MFC], FillGradient
- CDrawingManager [MFC], FillGradient2
- CDrawingManager [MFC], GrayRect
- CDrawingManager [MFC], HighlightRect
- CDrawingManager [MFC], HLStoRGB_ONE
- CDrawingManager [MFC], HLStoRGB_TWO
- CDrawingManager [MFC], HSVtoRGB
- CDrawingManager [MFC], HuetoRGB
- CDrawingManager [MFC], MirrorRect
- CDrawingManager [MFC], PixelAlpha
- CDrawingManager [MFC], PrepareShadowMask
- CDrawingManager [MFC], RGBtoHSL
- CDrawingManager [MFC], RGBtoHSV
- CDrawingManager [MFC], SetAlphaPixel
- CDrawingManager [MFC], SetPixel
- CDrawingManager [MFC], SmartMixColors
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
ms.openlocfilehash: 506ab7a06653942ecff05043a7e7efabd535115f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781693"
---
# <a name="cdrawingmanager-class"></a>CDrawingManager クラス

`CDrawingManager`クラスは、複雑な描画アルゴリズムを実装します。

## <a name="syntax"></a>構文

```
class CDrawingManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|`CDrawingManager` オブジェクトを構築します。|
|`CDrawingManager::~CDrawingManager`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|32 ビット版のデバイスに依存しないビットマップ (DIB) に直接書き込むことのできるアプリケーションを作成します。|
|[CDrawingManager::DrawAlpha](#drawalpha)|透明または半透明ピクセルのビットマップを表示します。|
|[CDrawingManager::DrawRotated](#drawrotated)|ソースで指定した四角形は、90 ° +/-内の DC のコンテンツを回転させます。|
|[CDrawingManager::DrawEllipse](#drawellipse)|指定された塗りつぶしと境界線の色を使用して楕円を描画します。|
|[CDrawingManager::DrawGradientRing](#drawgradientring)|リングを描画し、色のグラデーションで塗りつぶします。|
|[CDrawingManager::DrawLine、CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|線を描画します。|
|[CDrawingManager::DrawRect](#drawrect)|指定された塗りつぶしと境界線の色の四角形を描画します。|
|[CDrawingManager::DrawShadow](#drawshadow)|四角形の領域に影を描画します。|
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|2 つの色グラデーションの四角形の領域を塗りつぶします。|
|[CDrawingManager::FillGradient](#fillgradient)|指定した色のグラデーションを使用して四角形の領域を塗りつぶします。|
|[CDrawingManager::FillGradient2](#fillgradient2)|指定した色のグラデーションを使用して四角形の領域を塗りつぶします。 グラデーションの色の変更の方向が指定されてもします。|
|[CDrawingManager::GrayRect](#grayrect)|指定した色の灰色の四角形を塗りつぶします。|
|[CDrawingManager::HighlightRect](#highlightrect)|四角形の領域を強調表示されます。|
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|色を HLS 形式から RGB 表現に変換します。|
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|色を HLS 形式から RGB 表現に変換します。|
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|色を HSV 表現から RGB 表現に変換します。|
|[CDrawingManager::HuetoRGB](#huetorgb)|色合いの値を赤、緑、または青のコンポーネントに変換するヘルパー メソッドです。|
|[CDrawingManager::MirrorRect](#mirrorrect)|四角形の領域を反転します。|
|[CDrawingManager::PixelAlpha](#pixelalpha)|半透明ピクセルの最終的な色を決定するためのヘルパー メソッド。|
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|影に使用できるビットマップを作成します。|
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|色を RGB 表現から HSL 表現に変換します。|
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|色を RGB 表現から HSV 表現に変換します。|
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|ヘルパー メソッドはビットマップで部分的に透明なピクセルの色です。|
|[CDrawingManager::SetPixel](#setpixel)|ビットマップ内の 1 つのピクセルを指定した色に変更するヘルパー メソッドです。|
|[CDrawingManager::SmartMixColors](#smartmixcolors)|加重比率に基づいて 2 つの色を組み合わせ。|

## <a name="remarks"></a>Remarks

`CDrawingManager`クラス シャドウ、色のグラデーション、および強調表示された四角形を描画するための機能を提供します。 また、アルファ ブレンドを実行します。 アプリケーションの UI を直接変更するのには、このクラスを使用できます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdrawmanager.h

##  <a name="cdrawingmanager"></a>  CDrawingManager::CDrawingManager

構築、 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md)オブジェクト。

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
[in]デバイス コンテキストへの参照。 `CDrawingManager`描画のため、このコンテキストを使用します。

##  <a name="createbitmap_32"></a>  CDrawingManager::CreateBitmap_32

32 ビット版のデバイスに依存しないビットマップ (DIB) に直接書き込むことのできるアプリケーションを作成します。

```
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,
    void** pBits);

static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,
    COLORREF clrTransparent = -1);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*size*|[in]A [CSize](../../atl-mfc-shared/reference/csize-class.md)ビットマップのサイズを示すパラメーターです。|
|*pBits*|[out]DIB の場所を受信するデータ ポインターへのポインターのビット値。|
|*bitmap*|元のビットマップを識別するハンドル|
|*clrTransparent*|元のビットマップの透明色を指定する RGB 値。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、新しく作成された DIB ビットマップを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

DIB ビットマップを作成する方法の詳細については、次を参照してください。 [CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibitmap)します。

##  <a name="drawalpha"></a>  CDrawingManager::DrawAlpha

透明または半透明ピクセルのビットマップを表示します。

```
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>パラメーター

*pDstDC*<br/>
[in]コピー先のデバイス コンテキストへのポインター。

*rectDst*<br/>
[in]先の四角形。

*pSrcDC*<br/>
[in]ソースのデバイス コンテキストへのポインター。

*rectSrc*<br/>
[in]元の四角形。

### <a name="remarks"></a>Remarks

このメソッドは、アルファ ブレンドを実行の 2 つのビットマップ。 アルファ ブレンドの詳細については、次を参照してください。 [AlphaBlend](/windows/desktop/api/wingdi/nf-wingdi-alphablend) Windows SDK に含まれています。

##  <a name="drawellipse"></a>  CDrawingManager::DrawEllipse

指定された塗りつぶしと境界線の色を使用して楕円を描画します。

```
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]楕円の外接する四角形。

*clrFill*<br/>
[in]このメソッドは、楕円の塗りつぶしに使用する色です。

*clrLine*<br/>
[in]このメソッドでは、楕円の境界としての色。

### <a name="remarks"></a>Remarks

このメソッドは、どちらかの色が-1 に設定されている場合は、楕円を描画せず返します。 外接する四角形のいずれかのディメンションが 0 の場合は、楕円を描画せずも返されます。

##  <a name="drawgradientring"></a>  CDrawingManager::DrawGradientRing

リングを描画し、色のグラデーションで塗りつぶします。

```
BOOL DrawGradientRing(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    COLORREF colorBorder,
    int nAngle,
    int nWidth,
    COLORREF clrFace = (COLORREF)-1);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]A [CRect](../../atl-mfc-shared/reference/crect-class.md)グラデーションのリングの境界を指定するパラメーターです。

*colorStart*<br/>
[in]グラデーションの最初の色。

*colorFinish*<br/>
[in]グラデーションの最後の色。

*colorBorder*<br/>
[in]罫線の色。

*nAngle*<br/>
[in]グラデーションの描画の初期の角度を指定するパラメーター。 この値は、0 ~ 360 にする必要があります。

*nWidth*<br/>
[in]リングの境界線の幅。

*clrFace*<br/>
[in]リングの内部の色。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

によって定義された四角*rect*少なくとも 5 ピクセル高さ全体に適用され、5 ピクセルにする必要があります。

##  <a name="drawline_cdrawingmanager__drawlinea"></a>  CDrawingManager::DrawLine, CDrawingManager::DrawLineA

線を描画します。

```
void DrawLine(
    int x1,
    int y1,
    int x2,
    int y2,
    COLORREF clrLine);

void DrawLineA(
    double x1,
    double y1,
    double x2,
    double y2,
    COLORREF clrLine);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*x1*|[in]行の開始位置の x 座標。|
|*y1*|[in]行の開始位置の y 座標。|
|*x2*|[in]直線の終了位置の x 座標。|
|*y2*|[in]直線の終了位置の y 座標。|
|*clrLine*|[in]線の色。|

### <a name="remarks"></a>Remarks

このメソッドは失敗*clrLine* -1。

##  <a name="drawrect"></a>  CDrawingManager::DrawRect

指定された塗りつぶしと境界線の色の四角形を描画します。

```
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]四角形の境界。

*clrFill*<br/>
[in]このメソッドを使用すると、四角形の塗りつぶしの色。

*clrLine*<br/>
[in]このメソッドを使用して、四角形の境界線の色。

### <a name="remarks"></a>Remarks

このメソッドは、どちらかの色が-1 に設定されている場合は、四角形を描画せず返します。 また、四角形のいずれかのサイズは 0 を返します。

##  <a name="drawshadow"></a>  CDrawingManager::DrawShadow

四角形の領域に影を描画します。

```
BOOL DrawShadow(
    CRect rect,
    int nDepth,
    int iMinBrightness = 100,
    int iMaxBrightness = 50,
    CBitmap* pBmpSaveBottom = NULL,
    CBitmap* pBmpSaveRight = NULL,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bRightShadow = TRUE);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]アプリケーション内の四角形領域。 描画のマネージャーは、この領域の下に影を描画します。

*nDepth*<br/>
[in]幅と影の高さ。

*iMinBrightness*<br/>
[in]影の最小の明度をします。

*iMaxBrightness*<br/>
[in]影の最大の明るさです。

*pBmpSaveBottom*<br/>
[in]影の下の部分のイメージを含むビットマップへのポインター。

*pBmpSaveRight*<br/>
[in]四角形の右側に描画されているシャドウのイメージを含むビットマップへのポインター。

*clrBase*<br/>
[in]影の色。

*bRightShadow*<br/>
[in]影を描画する方法を示すブール値パラメーター。 場合*bRightShadow*は`TRUE`、`DrawShadow`右側にある四角形の影を描画します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

パラメーターを使用して、下および右の影の 2 つの有効なビットマップを行うことができます*pBmpSaveBottom*と*pBmpSaveRight*します。 これら[CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクトがアタッチされた GDI オブジェクトをある`DrawShadow`シャドウとしてこれらのビットマップを使用します。 場合、`CBitmap`パラメーターにアタッチされた GDI オブジェクトがない`DrawShadow`影を描画し、パラメーターに、ビットマップをアタッチします。 今後の呼び出しを`DrawShadow`、これらのビットマップ、描画プロセスを効率化を行うことができます。 詳細については、`CBitmap`クラスと GDI オブジェクトを参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。

これらのパラメーターのいずれかの場合`NULL`、`DrawShadow`は自動的に影を描画します。

設定した場合*bRightShadow*を FALSE に下にあると、四角形領域の左側に影が描画されます。

### <a name="example"></a>例

次の例では、使用する方法、`DrawShadow`のメソッド、`CDrawingManager`クラス。 このコード スニペットの一部、[プロパティ シートのデモ サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

##  <a name="fill4colorsgradient"></a>  CDrawingManager::Fill4ColorsGradient

2 つの色グラデーションの四角形の領域を塗りつぶします。

```
void Fill4ColorsGradient(
    CRect rect,
    COLORREF colorStart1,
    COLORREF colorFinish1,
    COLORREF colorStart2,
    COLORREF colorFinish2,
    BOOL bHorz = TRUE,
    int nPercentage = 50);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]塗りつぶす四角形。

*colorStart1*<br/>
[in]最初の色のグラデーションの初期の色。

*colorFinish1*<br/>
[in]最初の色グラデーションの終了色。

*colorStart2*<br/>
[in]2 番目の色のグラデーションの初期の色。

*colorFinish2*<br/>
[in]2 番目の色グラデーションの終了色。

*bHorz*<br/>
[in]示すブール値パラメーターかどうか`Fill4ColorsGradient`水平または垂直のグラデーションの色します。 TRUE は、水平方向のグラデーションを示します。

*nPercentage*<br/>
[in]0 ~ 100 の整数。 この値は、最初の色のグラデーションで塗りつぶす四角形の割合を示します。

### <a name="remarks"></a>Remarks

四角形が 2 つの色グラデーションにいっぱいになると、互いの上に配置されているかの値に応じて、[次へ] は*bHorz*します。 メソッドを使用して各色のグラデーションが個別に計算が[CDrawingManager::FillGradient](#fillgradient)します。

場合、このメソッドは、アサーション エラーを生成*nPercentage*が 0 未満か、100 を超える。

##  <a name="fillgradient"></a>  CDrawingManager::FillGradient

四角形の領域を指定した色のグラデーションで塗りつぶします。

```
void FillGradient(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    BOOL bHorz = TRUE,
    int nStartFlatPercentage = 0,
    int nEndFlatPercentage = 0);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]塗りつぶす四角形領域。

*colorStart*<br/>
[in]グラデーションの最初の色。

*colorFinish*<br/>
[in]グラデーションの終了色。

*bHorz*<br/>
[in]ブール型パラメーターを指定するかどうか`FillGradient`水平または垂直のグラデーションを描画する必要があります。

*nStartFlatPercentage*<br/>
[in]四角形の割合を`FillGradient`塗りつぶします*colorStart*グラデーションを開始する前にします。

*nEndFlatPercentage*<br/>
[in]四角形の割合を`FillGradient`塗りつぶします*colorFinish*グラデーションの終了後にします。

### <a name="example"></a>例

次の例では、使用する方法、`FillGradient`のメソッド、`CDrawingManager`クラス。 このコード スニペットの一部、 [MS Office 2007 のデモ サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

##  <a name="fillgradient2"></a>  CDrawingManager::FillGradient2

指定した色のグラデーションを使用して四角形の領域を塗りつぶします。

```
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]塗りつぶす四角形領域。

*colorStart*<br/>
[in]グラデーションの最初の色。

*colorFinish*<br/>
[in]グラデーションの最後の色。

*nAngle*<br/>
[in]0 ~ 360 の間の整数。 このパラメーターは、色のグラデーションの方向を指定します。

### <a name="remarks"></a>Remarks

使用*nAngle*色のグラデーションの方向を指定します。 色のグラデーションの方向を指定するときに指定することも、色のグラデーションの開始位置。 値 0 を*nAngle*四角形の上端からグラデーションの開始を示します。 として*nAngle*増加すると、グラデーションが角度に基づいて反時計回りの方向に移動の開始位置。

### <a name="example"></a>例

次の例では、使用する方法、`FillGradient2`のメソッド、`CDrawingManager`クラス。 このコード スニペットの一部、[新しいコントロール サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

##  <a name="grayrect"></a>  CDrawingManager::GrayRect

指定した色の灰色の四角形を塗りつぶします。

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]塗りつぶす四角形領域。

*nPercentage*<br/>
[in]灰色の四角形で目的の割合。

*clrTransparent*<br/>
[in]透明色。

*clrDisabled*<br/>
[in]場合、彩度のこのメソッドを使用する色*nPercentage*が-1 に設定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

パラメーターの*nPercentage*、下限の値が暗い色を示します。

最大値*nPercentage*は 200 です。 200 を超える値には、四角形の外観は変わりません。 このメソッドを使用して、値が-1 の場合は、 *clrDisabled*四角形の鮮やかさを制限します。

##  <a name="highlightrect"></a>  CDrawingManager::HighlightRect

四角形の領域を強調表示されます。

```
BOOL HighlightRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    int nTolerance = 0,
    COLORREF clrBlend = (COLORREF)-1);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]四角形の領域を強調表示します。

*nPercentage*<br/>
[in]透明度、強調表示する必要がありますかを示す割合。

*clrTransparent*<br/>
[in]透明色。

*nTolerance*<br/>
[in]色の許容範囲を示す 0 から 255 までの整数。

*clrBlend*<br/>
[in]ブレンドの基本の色です。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

場合*nPercentage*は 0 ~ 99、`HighlightRect`アルファ ブレンディング アルゴリズムを使用します。 アルファ ブレンドの詳細については、次を参照してください。[アルファ ブレンドの直線と塗りつぶし](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills)します。 場合*nPercentage* -1 で、このメソッドは、既定の強調表示のレベルを使用します。 場合*nPercentage* 100 は、このメソッドは何も実行し、TRUE を返します。

メソッド パラメーターを使用して*nTolerance*を四角形の領域を強調表示するかどうかを判断します。 四角形は、アプリケーションの背景色の違いを強調表示して*clrTransparent*必要がありますより小さい*nTolerance*各色コンポーネント (赤、緑、および青) にします。

##  <a name="hlstorgb_one"></a>  CDrawingManager::HLStoRGB_ONE

色を HLS 形式から RGB 表現に変換します。

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
[in]色の色合いを表す 0 ~ 1 の数値。

*L*<br/>
[in]0 ~ 1 の間の数値では、色の明るさを示します。

*S*<br/>
[in]0 ~ 1 の間の数値では、色の彩度を示します。

### <a name="return-value"></a>戻り値

指定された HLS 色の RGB 表現。

### <a name="remarks"></a>Remarks

色は、HSV (色合い、鮮やかさ、および値)、HSL (色相、彩度、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](/windows/desktop/uxguide/vis-color)します。

このメソッドと`CDrawingManager::HLStoRGB_TWO`メソッドは、同じ操作を実行しますの異なる値が必要です、 *H*パラメーター。 このメソッドで*H*円に占める割合です。 `CDrawingManager::HLStoRGB_TWO`メソッド、 *H*は 0 ~ 360 両方を表現する赤の間の角度の値。 たとえば、 `HLStoRGB_ONE`、値は 0.25 の*H*と 90 の値と等価`HLStoRGB_TWO`します。

##  <a name="hlstorgb_two"></a>  CDrawingManager::HLStoRGB_TWO

色を HLS 形式から RGB 表現に変換します。

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
[in]色の色合いを表す 0 ~ 360 の数値。

*L*<br/>
[in]0 ~ 1 の間の数値では、色の明るさを示します。

*S*<br/>
[in]0 ~ 1 の間の数値では、色の彩度を示します。

### <a name="return-value"></a>戻り値

指定された HLS 色の RGB 表現。

### <a name="remarks"></a>Remarks

色は、HSV (色合い、鮮やかさ、および値)、HSL (色相、彩度、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](/windows/desktop/uxguide/vis-color)します。

このメソッドと[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)メソッドは、同じ操作を実行しますの異なる値が必要です、 *H*パラメーター。 このメソッドで*H*は 0 ~ 360 両方を表現する赤の間の角度の値。 [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)メソッド、 *H*円に占める割合です。 たとえば、 `HLStoRGB_ONE`、値は 0.25 の*H*と 90 の値と等価`HLStoRGB_TWO`します。

##  <a name="hsvtorgb"></a>  CDrawingManager::HSVtoRGB

色を HSV 表現から RGB 表現に変換します。

```
static COLORREF __stdcall HSVtoRGB(
    double H,
    double S,
    double V);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*H*|[in]0 ~ 360 の数値では、色の色合いを示します。|
|*S*|[in]0 ~ 1 の間の数値では、色の彩度を示します。|
|*V*|[in]0 ~ 1 の間の数値では、色の値を示します。|

### <a name="return-value"></a>戻り値

提供される HSV 色の RGB 表現。

### <a name="remarks"></a>Remarks

色は、HSV (色合い、鮮やかさ、および値)、HSL (色相、彩度、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](/windows/desktop/uxguide/vis-color)します。

##  <a name="huetorgb"></a>  CDrawingManager::HuetoRGB

色合いの値を赤、緑、または青のコンポーネントに変換します。

```
static double __stdcall HuetoRGB(
    double m1,
    double m2,
    double h);

static BYTE __stdcall HueToRGB(
    float rm1,
    float rm2,
    float rh);
```

### <a name="parameters"></a>パラメーター

*m1*<br/>
[in]「解説」を参照してください。

*m2*<br/>
[in]「解説」を参照してください。

*h*<br/>
[in]「解説」を参照してください。

*rm1*<br/>
[in]「解説」を参照してください。

*rm2*<br/>
[in]「解説」を参照してください。

*rh*<br/>
[in]「解説」を参照してください。

### <a name="return-value"></a>戻り値

指定された色合いの個別赤、緑、または青コンポーネント。

### <a name="remarks"></a>Remarks

このメソッドは、ヘルパー メソッドを`CDrawingManager`クラス HSV または HSL の表現で使用する色の個々 の赤、緑、および青のコンポーネントを計算するために使用します。 このメソッドは、プログラマによって直接呼び出されるものではありません。 入力パラメーターは、変換アルゴリズムに依存する値です。

HSV または HSL の色を RGB 表現に変換するには、次の方法のいずれかを呼び出します。

- [CDrawingManager::HSVtoRGB](#hsvtorgb)

- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)

- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)

##  <a name="mirrorrect"></a>  CDrawingManager::MirrorRect

四角形の領域を反転します。

```
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
[in]反転対象の領域に外接する四角形。

*bHorz*<br/>
[in]四角形を水平方向または垂直方向に反転するかどうかを示すブール値パラメーター。

### <a name="remarks"></a>Remarks

このメソッドはによって所有されているデバイス コンテキストの任意の領域を反転させることができます、`CDrawingManager`クラス。 場合*bHorz*が TRUE に設定すると、このメソッドの領域を左右に反転します。 それ以外の場合、領域が垂直方向に反転します。

##  <a name="pixelalpha"></a>  CDrawingManager::PixelAlpha

半透明ピクセルの最終的な色を計算します。

```
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    int percent);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    double percentR,
    double percentG,
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    COLORREF dstPixel,
    int percent);
```

### <a name="parameters"></a>パラメーター

*srcPixel*<br/>
[in]ピクセルの初期の色。

*%*<br/>
[in]透明度の割合を表す 0 ~ 100 の数値。 100 の値は、初期の色が完全に透明であることを示します。

*percentR*<br/>
[in]赤の要素の透明度の割合を表す 0 ~ 100 の数値。

*percentG*<br/>
[in]緑の要素の透明度の割合を表す 0 ~ 100 の範囲数です。

*percentB*<br/>
[in]青のコンポーネントの透明度の割合を表す 0 ~ 100 の数値。

*dstPixel*<br/>
[in]ピクセルの基本の色。

### <a name="return-value"></a>戻り値

半透明のピクセルの最終的な色。

### <a name="remarks"></a>Remarks

これは半透明のビットマップを色分け表示するためのヘルパー クラスであり、プログラマが直接呼び出されるものではありません。

持つメソッドのバージョンを使用すると*dstPixel*、最終的な色の組み合わせは、 *dstPixel*と*srcPixel*します。 *SrcPixel*色が部分的に透明な色の基本色*dstPixel*します。

##  <a name="prepareshadowmask"></a>  CDrawingManager::PrepareShadowMask

影に使用できるビットマップを作成します。

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>パラメーター

*nDepth*<br/>
[in]幅と影の高さ。

*clrBase*<br/>
[in]影の色。

*iMinBrightness*<br/>
[in]影の最小の明度をします。

*iMaxBrightness*<br/>
[in]影の最大の明るさです。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、作成されたビットマップを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

場合*nDepth*はこのメソッドを 0 に設定するは終了し、NULL を返します。 場合*nDepth*が 3 未満の幅と影の高さが 3 ピクセルに設定されます場合、。

##  <a name="rgbtohsl"></a>  CDrawingManager::RGBtoHSL

色合い、鮮やかさ、および明るさ (HSL) 表現を色を赤、緑、および青 (RGB) 形式に変換します。

```
static void __stdcall RGBtoHSL(
    COLORREF rgb,
    double* H,
    double* S,
    double* L);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*rgb*|[in]RGB 値の色。|
|*H*|[out]メソッドが、色の色合いを格納する double 型へのポインター。|
|*S*|[out]メソッドが、色の彩度を格納する double 型へのポインター。|
|*L*|[out]メソッドが、色の輝度を格納する double 型へのポインター。|

### <a name="remarks"></a>Remarks

色は、HSV (色合い、鮮やかさ、および値)、HSL (色相、彩度、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](/windows/desktop/uxguide/vis-color)します。

返された値*H*は 0 ~ 1 が 0 と 1 の両方を表します赤の比率として表されます。 戻り値を*S*と*L* 0 から 1 までの数値します。

##  <a name="rgbtohsv"></a>  CDrawingManager::RGBtoHSV

色を RGB 表現から HSV 表現に変換します。

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>パラメーター

*rgb*<br/>
[in]RGB 表現に変換する色です。

*H*<br/>
[out]このメソッドが最終的な色の色合いを格納する double 型へのポインター。

*S*<br/>
[out]このメソッドが最終的な色の彩度を格納する double 型へのポインター。

*V*<br/>
[out]このメソッドが、色の結果として得られる値を格納する double 型へのポインター。

### <a name="remarks"></a>Remarks

色は、HSV (色合い、鮮やかさ、および値)、HSL (色相、彩度、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](/windows/desktop/uxguide/vis-color)します。

返された値*H* 0 ~ 360 の数値は、0 から 360 の両方が red 示すためです。 戻り値は、 *S*と*V* 0 から 1 までの数値します。

##  <a name="setalphapixel"></a>  CDrawingManager::SetAlphaPixel

ビットマップ内の透明なピクセルを色します。

```
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,
    CRect rect,
    int x,
    int y,
    int percent,
    int iShadowSize,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bIsRight = TRUE);
```

### <a name="parameters"></a>パラメーター

*pBits*<br/>
[in]ビットマップのビット値へのポインター。

*rect*<br/>
[in]アプリケーション内の四角形領域。 描画のマネージャーは、下にあると、この領域の右側に影を描画します。

*x*<br/>
[in]色にピクセルの水平座標。

*y*<br/>
[in]色にピクセルの垂直座標。

*%*<br/>
[in]透明度の割合。

*iShadowSize*<br/>
[in]幅と影の高さ。

*clrBase*<br/>
[in]影の色。

*bIsRight*<br/>
[in]どのピクセルに色を示すブール値パラメーター。 詳細については、次の「解説」を参照してください。

### <a name="remarks"></a>Remarks

このメソッドは、ヘルパー メソッドによって使用される、 [CDrawingManager::DrawShadow](#drawshadow)メソッド。 影を描画する場合を呼び出すことをお勧めします。`CDrawingManager::DrawShadow`代わりにします。

場合*bIsRight*が TRUE に設定の色にピクセルが測定されます*x*の右端からピクセル*rect*します。 FALSE の場合は、ピクセルの色に、測定*x*の左端からピクセル*rect*します。

##  <a name="setpixel"></a>  CDrawingManager::SetPixel

ビットマップ内の 1 つのピクセルを指定した色に変更します。

```
static void __stdcall SetPixel(
    COLORREF* pBits,
    int cx,
    int cy,
    int x,
    int y,
    COLORREF color);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*pBits*|[in]ビットマップのビット値へのポインター。|
|*cx*|[in]ビットマップの幅の合計。|
|*cy*|[in]ビットマップの高さの合計。|
|*x*|[in]変更するビットマップのピクセルの x 座標。|
|*y*|[in]変更するビットマップのピクセルの y 座標。|
|*色*|[in]指定された座標で識別されるピクセルの新しい色。|

##  <a name="smartmixcolors"></a>  CDrawingManager::SmartMixColors

加重比率に基づいて 2 つの色を組み合わせ。

```
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,
    COLORREF color2,
    double dblLumRatio = 1.,
    int k1 = 1,
    int k2 = 1);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*color1*|[in]最初の色を混在させる。|
|*color2*|[in]2 番目の色を混在させる。|
|*dblLumRatio*|[in]新しい色の明るさの比率。 `SmartMixColors` 最終的な色を決定する前に、この比率で混合の色の明るさを乗算します。|
|*k1*|[in]最初の色の加重比率です。|
|*k2*|[in]2 番目の色の加重比率です。|

### <a name="return-value"></a>戻り値

指定された色の加重の組み合わせを表す色。

### <a name="remarks"></a>Remarks

このメソッドは、どちらの場合はエラーで失敗*k1*または*k2* 0 未満です。 かどうかは、0 に設定がこれらのパラメーターを両方とも、メソッドを返します`RGB(0, 0, 0)`します。

次の式で加重比率が計算されます: (color1 \* k1 + color2 \* k2)/(k1 + k2) します。 加重比率が決定した後、メソッドは、混合の色の明るさを計算します。 掛けたして光度*dblLumRatio*します。 値が 1.0 よりも大きい場合は、メソッドは、新しい値に混合の色の明るさを設定します。 それ以外の場合、明るさは 1.0 に設定されます。

##  <a name="drawrotated"></a>  CDrawingManager::DrawRotated

指定した四角形内の DC のコンテンツ ソースを 90 度回転します。

```
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>パラメーター

*rectDest*<br/>
先の四角形。

*dcSrc*<br/>
元のデバイス コンテキスト。

*bClockWise*<br/>
True の場合 +90 度の回転。FALSE では、回転-90 度を示します。

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
