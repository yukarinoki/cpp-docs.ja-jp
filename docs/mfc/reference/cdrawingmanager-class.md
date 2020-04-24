---
title: クラス
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
ms.openlocfilehash: 73c5775c2cb83dea79401615b31f2194094fac8e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753241"
---
# <a name="cdrawingmanager-class"></a>クラス

この`CDrawingManager`クラスは、複雑な描画アルゴリズムを実装します。

## <a name="syntax"></a>構文

```
class CDrawingManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の手順を実行します。](#cdrawingmanager)|`CDrawingManager` オブジェクトを構築します。|
|`CDrawingManager::~CDrawingManager`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CreateBitmap_32](#createbitmap_32)|アプリケーションが直接書き込むことができる 32 ビットのデバイスに依存しないビットマップ (DIB) を作成します。|
|[:Dローアルファ](#drawalpha)|透明または半透明のピクセルを持つビットマップを表示します。|
|[:Dロー回転](#drawrotated)|指定された四角形内のソース DC コンテンツを +/- 90 度回転します。|
|[:Dロー楕円](#drawellipse)|指定された塗りつぶしと境界線の色で楕円を描画します。|
|[:Dローグラデーションリング](#drawgradientring)|リングを描画し、カラー グラデーションで塗りつぶします。|
|[:Dローライン、コネプトマネージャー::DローラインA](#drawline_cdrawingmanager__drawlinea)|線を描画します。|
|[:Dローレク](#drawrect)|指定された塗りつぶし色と境界線の色で四角形を描画します。|
|[クリッピングマネージャー::Dローシャドウ](#drawshadow)|四角形の領域の影を描画します。|
|[コントロール::フィル4カラーズグラデーション](#fill4colorsgradient)|四角形の領域を 2 色のグラデーションで塗りつぶします。|
|[次の項目を使用します。](#fillgradient)|指定した色のグラデーションで四角形の領域を塗りつぶします。|
|[次の項目を使用します。](#fillgradient2)|指定した色のグラデーションで四角形の領域を塗りつぶします。 グラデーションの色の変更方向も指定されます。|
|[Cドローイングマネージャー::グレイレック](#grayrect)|指定したグレーの色で四角形を塗りつぶします。|
|[Cドローイングマネージャー::ハイライトレック](#highlightrect)|矩形領域をハイライトします。|
|[コドロープマネージャー:HLStoRGB_ONE](#hlstorgb_one)|カラーを HLS 表現から RGB 表現に変換します。|
|[マネージャー:HLStoRGB_TWO](#hlstorgb_two)|カラーを HLS 表現から RGB 表現に変換します。|
|[マネージャー::HSVtoRGB](#hsvtorgb)|色を HSV 表現から RGB 表現に変換します。|
|[次の情報を使用します。](#huetorgb)|色相の値を赤、緑、または青の成分に変換するヘルパー メソッド。|
|[::ミラーレクト](#mirrorrect)|矩形領域を反転します。|
|[クエクスペックマネージャー::Pケルアルファ](#pixelalpha)|半透明ピクセルの最終的な色を決定するヘルパー メソッド。|
|[:Pレパレシャドウマスク](#prepareshadowmask)|影として使用できるビットマップを作成します。|
|[コブトマネージャー::RGBtoHSL](#rgbtohsl)|カラーを RGB 表現から HSL 表現に変換します。|
|[コブトマネージャー::RGBtoHSV](#rgbtohsv)|カラーを RGB 表現から HSV 表現に変換します。|
|[コントロールマネージャー::セットアルファピクセル](#setalphapixel)|ビットマップ内の部分的に透明なピクセルを色分けするヘルパー メソッド。|
|[コントロール マネージャー::ピクセルを設定します。](#setpixel)|ビットマップ内の単一ピクセルを指定した色に変更するヘルパー メソッド。|
|[::スマートミックスカラー](#smartmixcolors)|加重比に基づいて 2 つの色を結合します。|

## <a name="remarks"></a>解説

この`CDrawingManager`クラスには、影、色のグラデーション、および強調表示された四角形を描画するための関数が用意されています。 また、アルファブレンドも行います。 このクラスを使用して、アプリケーションの UI を直接変更できます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdrawmanager.h

## <a name="cdrawingmanagercdrawingmanager"></a><a name="cdrawingmanager"></a>次の手順を実行します。

[オブジェクトを](../../mfc/reference/cdrawingmanager-class.md)構築します。

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
[in]デバイス コンテキストへの参照。 この`CDrawingManager`コンテキストを描画に使用します。

## <a name="cdrawingmanagercreatebitmap_32"></a><a name="createbitmap_32"></a>CreateBitmap_32

アプリケーションが直接書き込むことができる 32 ビットのデバイスに依存しないビットマップ (DIB) を作成します。

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
|*size*|[in]ビットマップのサイズを示す[CSize](../../atl-mfc-shared/reference/csize-class.md)パラメーター。|
|*pビット*|[アウト]DIB のビット値の位置を受け取るデータ ポインターへのポインター。|
|*ビットマップ*|元のビットマップへのハンドル|
|*clr透明*|元のビットマップの透明色を指定する RGB 値。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、新しく作成された DIB ビットマップへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

DIB ビットマップの作成方法の詳細については、 [CreateDIBSection](/windows/win32/api/wingdi/nf-wingdi-createdibitmap)を参照してください。

## <a name="cdrawingmanagerdrawalpha"></a><a name="drawalpha"></a>:Dローアルファ

透明または半透明のピクセルを持つビットマップを表示します。

```cpp
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>パラメーター

*pDstDC*<br/>
[in]宛先のデバイス コンテキストへのポインター。

*レクトドスト*<br/>
[in]コピー先の四角形。

*pSrcDC*<br/>
[in]ソースのデバイス コンテキストへのポインター。

*レクトスrc*<br/>
[in]ソースの四角形。

### <a name="remarks"></a>解説

このメソッドは、2 つのビットマップに対してアルファ ブレンドを実行します。 アルファ ブレンドの詳細については、Windows SDK の[「アルファブレンド](/windows/win32/api/wingdi/nf-wingdi-alphablend)」を参照してください。

## <a name="cdrawingmanagerdrawellipse"></a><a name="drawellipse"></a>:Dロー楕円

指定された塗りつぶしと境界線の色で楕円を描画します。

```cpp
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]楕円の外接する四角形。

*clrフィル*<br/>
[in]このメソッドが楕円を塗りつぶすために使用する色。

*clrLine*<br/>
[in]このメソッドが楕円の境界線として使用する色。

### <a name="remarks"></a>解説

このメソッドは、いずれかの色が -1 に設定されている場合、楕円を描画せずに戻ります。 外接する四角形のいずれかの寸法が 0 の場合は、楕円を描画せずに戻ります。

## <a name="cdrawingmanagerdrawgradientring"></a><a name="drawgradientring"></a>:Dローグラデーションリング

リングを描画し、カラー グラデーションで塗りつぶします。

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

*Rect*<br/>
[in]グラデーション リングの境界を指定する[CRect](../../atl-mfc-shared/reference/crect-class.md)パラメーター。

*カラースタート*<br/>
[in]グラデーションの最初の色。

*カラー仕上げ*<br/>
[in]グラデーションの最後の色。

*カラーボーダー*<br/>
[in]境界線の色。

*nアングル*<br/>
[in]グラデーションの初期描画角度を指定するパラメータ。 この値は 0 ~ 360 の間にする必要があります。

*n幅*<br/>
[in]リングの境界線の幅。

*clrFace*<br/>
[in]リングの内部の色。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*rect*によって定義される四角形は、幅が 5 ピクセル以上、高さ 5 ピクセル以上である必要があります。

## <a name="cdrawingmanagerdrawline-cdrawingmanagerdrawlinea"></a><a name="drawline_cdrawingmanager__drawlinea"></a>:Dローライン、コネプトマネージャー::DローラインA

線を描画します。

```cpp
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
|*x1*|[in]線の始点となる x 座標。|
|*y1*|[in]線の始点となる y 座標。|
|*x2*|[in]線の終わり位置の x 座標。|
|*y2*|[in]線の終わり位置の y 座標。|
|*clrLine*|[in]線の色。|

### <a name="remarks"></a>解説

*clrLine*が -1 の場合、このメソッドは失敗します。

## <a name="cdrawingmanagerdrawrect"></a><a name="drawrect"></a>:Dローレク

指定された塗りつぶし色と境界線の色で四角形を描画します。

```cpp
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]四角形の境界。

*clrフィル*<br/>
[in]このメソッドが四角形を塗りつぶすために使用する色。

*clrLine*<br/>
[in]このメソッドが四角形の境界線に使用する色。

### <a name="remarks"></a>解説

このメソッドは、いずれかの色が -1 に設定されている場合、四角形を描画せずに戻ります。 また、四角形の次元が 0 の場合にも返されます。

## <a name="cdrawingmanagerdrawshadow"></a><a name="drawshadow"></a>クリッピングマネージャー::Dローシャドウ

四角形の領域の影を描画します。

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

*Rect*<br/>
[in]アプリケーション内の四角形領域。 描画マネージャはこの領域の下に影を描画します。

*n深さ*<br/>
[in]影の幅と高さ。

*iMin明るさ*<br/>
[in]影の最小輝度。

*iマックスブライトネス*<br/>
[in]影の最大輝度。

*下書き*<br/>
[in]シャドウの下端のイメージを含むビットマップへのポインター。

*右に保存します。*<br/>
[in]四角形の右側に描画される影のイメージを含むビットマップへのポインター。

*clrベース*<br/>
[in]影の色。

*ブラライトシャドウ*<br/>
[in]シャドウの描画方法を示すブール値パラメーター。 *bRightShadow*が`TRUE``DrawShadow`の場合、四角形の右側に影を描画します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

パラメーター *pBmpSaveBottom と pBmpSaveRight*を使用して、下と右*pBmpSaveRight*の影に対して 2 つの有効なビットマップを指定できます。 これらの[CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクトに GDI オブジェクト`DrawShadow`がアタッチされている場合、これらのビットマップはシャドウとして使用されます。 パラメータに`CBitmap`GDI オブジェクトがアタッチされていない場合は`DrawShadow`、シャドウを描画し、ビットマップをパラメータにアタッチします。 今後の`DrawShadow`呼び出しでは、これらのビットマップを提供して描画プロセスを高速化できます。 クラスおよび GDI`CBitmap`オブジェクトの詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。

これらのパラメータのいずれかが の`NULL``DrawShadow`場合、自動的に影が描画されます。

*bRightShadow*を FALSE に設定すると、影は矩形領域の下と左に描画されます。

### <a name="example"></a>例

クラスのメソッドの使用方法を`DrawShadow`次の例に示します`CDrawingManager`。 このコード スニペットは[、プロップ シート デモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

## <a name="cdrawingmanagerfill4colorsgradient"></a><a name="fill4colorsgradient"></a>コントロール::フィル4カラーズグラデーション

四角形の領域を 2 色のグラデーションで塗りつぶします。

```cpp
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

*Rect*<br/>
[in]塗りつぶす四角形。

*カラースタート1*<br/>
[in]最初の色のグラデーションの初期色。

*カラーフィニッシュ1*<br/>
[in]最初の色のグラデーションの最終色。

*カラースタート2*<br/>
[in]2 番目の色のグラデーションの初期色。

*カラーフィニッシュ2*<br/>
[in]2 番目の色のグラデーションの最終色。

*bHorz*<br/>
[in]グラデーションの色を水平または`Fill4ColorsGradient`垂直のどちらにするかを示すブール値パラメーター。 TRUE は、水平方向のグラデーションを示します。

*nパーセント*<br/>
[in]0 から 100 までの整数。 この値は、最初の色のグラデーションで塗りつぶす四角形の割合を示します。

### <a name="remarks"></a>解説

四角形が 2 つの色のグラデーションで塗りつぶされている場合、*それらは bHorz*の値に応じて、互いの上または隣に配置されます。 各色のグラデーションは、メソッド[CDrawingManager::FillGradient](#fillgradient)で個別に計算されます。

このメソッドは *、nPercentage*が 0 未満または 100 を超える場合にアサーション エラーを生成します。

## <a name="cdrawingmanagerfillgradient"></a><a name="fillgradient"></a>次の項目を使用します。

指定した色のグラデーションで四角形の領域を塗りつぶします。

```cpp
void FillGradient(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    BOOL bHorz = TRUE,
    int nStartFlatPercentage = 0,
    int nEndFlatPercentage = 0);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]塗りつぶす四角形の領域。

*カラースタート*<br/>
[in]グラデーションの最初の色。

*カラー仕上げ*<br/>
[in]グラデーションの最終色。

*bHorz*<br/>
[in]水平または垂直のグラデーションを`FillGradient`描画するかどうかを指定するブール値パラメーター。

*フラットパーセンテージを開始*<br/>
[in]グラデーションを開始する前に`FillGradient` *colorStart*で塗りつぶす四角形の割合。

*エンドフラットパーセンテージ*<br/>
[in]グラデーションが終了した後に`FillGradient`塗りつぶす四角形の割合*を*示します。

### <a name="example"></a>例

クラスのメソッドの使用方法を`FillGradient`次の例に示します`CDrawingManager`。 このコード スニペットは、 [MS Office 2007 デモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

## <a name="cdrawingmanagerfillgradient2"></a><a name="fillgradient2"></a>次の項目を使用します。

指定した色のグラデーションで四角形の領域を塗りつぶします。

```cpp
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]塗りつぶす四角形の領域。

*カラースタート*<br/>
[in]グラデーションの最初の色。

*カラー仕上げ*<br/>
[in]グラデーションの最後の色。

*nアングル*<br/>
[in]0 ~ 360 の整数。 このパラメーターは、色のグラデーションの方向を指定します。

### <a name="remarks"></a>解説

nAngle*を*使用して、カラー グラデーションの方向を指定します。 色のグラデーションの方向を指定する場合は、色のグラデーションの開始位置も指定します。 *nAngle*の値が 0 の場合、グラデーションは四角形の上端から開始することを示します。 *nAngle*が大きくなると、グラデーションの開始位置は角度に基づいて反時計回りに移動します。

### <a name="example"></a>例

クラスのメソッドの使用方法を`FillGradient2`次の例に示します`CDrawingManager`。 このコード スニペットは、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

## <a name="cdrawingmanagergrayrect"></a><a name="grayrect"></a>Cドローイングマネージャー::グレイレック

指定したグレーの色で四角形を塗りつぶします。

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]塗りつぶす四角形の領域。

*nパーセント*<br/>
[in]四角形に含める灰色の割合。

*clr透明*<br/>
[in]透明色。

*無効な clr*<br/>
[in]*nPercentage*が -1 に設定されている場合に、このメソッドが彩度を解除するために使用する色。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

パラメータ*nPercentage*の場合、低い値は暗い色を示します。

*nPercentage*の最大値は 200 です。 200 より大きい値を指定しても、四角形の外観は変わりません。 値が -1 の場合、このメソッドは*clrDisabled*を使用して四角形の彩度を制限します。

## <a name="cdrawingmanagerhighlightrect"></a><a name="highlightrect"></a>Cドローイングマネージャー::ハイライトレック

矩形領域をハイライトします。

```
BOOL HighlightRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    int nTolerance = 0,
    COLORREF clrBlend = (COLORREF)-1);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]ハイライトする矩形領域。

*nパーセント*<br/>
[in]強調表示の透明度を示す割合。

*clr透明*<br/>
[in]透明色。

*n許容範囲*<br/>
[in]色の許容度を示す 0 ~ 255 の整数。

*clrブレンド*<br/>
[in]ブレンドの基本色。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*nPercentage が*0 ~ 99 の場合は、`HighlightRect`アルファ ブレンド アルゴリズムを使用します。 アルファ ブレンドの詳細については、「アルファ[ブレンドの線と塗りつぶし](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills)」を参照してください。 *nPercentage が*-1 の場合、このメソッドは既定の強調表示レベルを使用します。 *nPercentage が*100 の場合、このメソッドは何も実行せず、TRUE を返します。

このメソッドは、パラメータ*nTolerance*を使用して、矩形領域をハイライトするかどうかを決定します。 四角形を強調表示するには、アプリケーションの背景色と*clrTransparent*の差が各色コンポーネント (赤、緑、青) の*nTolerance*未満である必要があります。

## <a name="cdrawingmanagerhlstorgb_one"></a><a name="hlstorgb_one"></a>コドロープマネージャー:HLStoRGB_ONE

カラーを HLS 表現から RGB 表現に変換します。

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
[in]色の色相を表す 0 ~ 1 の数値。

*L*<br/>
[in]色の明るさを示す 0 ~ 1 の数値。

*S*<br/>
[in]色の彩度を示す 0 ~ 1 の数値。

### <a name="return-value"></a>戻り値

提供される HLS カラーの RGB 表現。

### <a name="remarks"></a>解説

色は HSV (色相、彩度、および値)、HSL (色相、彩度、明度)、または RGB (赤、緑、青) で表すことができます。 色の表現の詳細については、「[色](/windows/win32/uxguide/vis-color)」を参照してください。

このメソッドとメソッド`CDrawingManager::HLStoRGB_TWO`は同じ操作を実行しますが *、H*パラメーターに異なる値を必要とします。 この方法では *、H*は円のパーセンテージです。 この方法`CDrawingManager::HLStoRGB_TWO`では *、H*は 0 ~ 360 の角度値で、どちらも赤を表します。 たとえば、 で`HLStoRGB_ONE`の*H*の値 0.25 は、 の値 90 と`HLStoRGB_TWO`同じです。

## <a name="cdrawingmanagerhlstorgb_two"></a><a name="hlstorgb_two"></a>マネージャー:HLStoRGB_TWO

カラーを HLS 表現から RGB 表現に変換します。

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
[in]色の色相を表す 0 ~ 360 の数値。

*L*<br/>
[in]色の明るさを示す 0 ~ 1 の数値。

*S*<br/>
[in]色の彩度を示す 0 ~ 1 の数値。

### <a name="return-value"></a>戻り値

提供される HLS カラーの RGB 表現。

### <a name="remarks"></a>解説

色は HSV (色相、彩度、および値)、HSL (色相、彩度、明度)、または RGB (赤、緑、青) で表すことができます。 色の表現の詳細については、「[色](/windows/win32/uxguide/vis-color)」を参照してください。

このメソッドと[CDrawingManager:HLStoRGB_ONE](#hlstorgb_one)メソッドは同じ操作を実行しますが *、H*パラメーターに異なる値を必要とします。 この方法では *、H*は 0 ~ 360 の角度値で、どちらも赤を表します。 [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)メソッドでは *、H*は円のパーセンテージです。 たとえば、 で`HLStoRGB_ONE`の*H*の値 0.25 は、 の値 90 と`HLStoRGB_TWO`同じです。

## <a name="cdrawingmanagerhsvtorgb"></a><a name="hsvtorgb"></a>マネージャー::HSVtoRGB

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
|*H*|[in]色の色相を示す 0 ~ 360 の数値。|
|*S*|[in]色の彩度を示す 0 ~ 1 の数値。|
|*V*|[in]色の値を示す 0 ~ 1 の数値。|

### <a name="return-value"></a>戻り値

提供される HSV カラーの RGB 表現。

### <a name="remarks"></a>解説

色は HSV (色相、彩度、および値)、HSL (色相、彩度、明度)、または RGB (赤、緑、青) で表すことができます。 色の表現の詳細については、「[色](/windows/win32/uxguide/vis-color)」を参照してください。

## <a name="cdrawingmanagerhuetorgb"></a><a name="huetorgb"></a>次の情報を使用します。

色相の値を赤、緑、または青の成分に変換します。

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

*H*<br/>
[in]「解説」を参照してください。

*rm1*<br/>
[in]「解説」を参照してください。

*rm2*<br/>
[in]「解説」を参照してください。

*Rh*<br/>
[in]「解説」を参照してください。

### <a name="return-value"></a>戻り値

指定された色相の個々の赤、緑、または青のコンポーネント。

### <a name="remarks"></a>解説

このメソッドは、HSV または`CDrawingManager`HSL 表現の色の個々の赤、緑、青のコンポーネントを計算するためにクラスが使用するヘルパー メソッドです。 このメソッドは、プログラマが直接呼び出すものではありません。 入力パラメーターは、変換アルゴリズムに依存する値です。

HSV または HSL カラーを RGB 表現に変換するには、次のいずれかのメソッドを呼び出します。

- [マネージャー::HSVtoRGB](#hsvtorgb)

- [コドロープマネージャー:HLStoRGB_ONE](#hlstorgb_one)

- [マネージャー:HLStoRGB_TWO](#hlstorgb_two)

## <a name="cdrawingmanagermirrorrect"></a><a name="mirrorrect"></a>::ミラーレクト

矩形領域を反転します。

```cpp
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]反転する領域の外接する四角形。

*bHorz*<br/>
[in]四角形が水平方向または垂直方向に反転するかどうかを示すブール値パラメーター。

### <a name="remarks"></a>解説

このメソッドは、クラスが所有するデバイス コンテキストの任意`CDrawingManager`の領域を反転できます。 *bHorz*が TRUE に設定されている場合、このメソッドは領域を水平方向に反転します。 それ以外の場合は、領域を垂直方向に反転します。

## <a name="cdrawingmanagerpixelalpha"></a><a name="pixelalpha"></a>クエクスペックマネージャー::Pケルアルファ

半透明のピクセルの最終色を計算します。

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

*srcピクセル*<br/>
[in]ピクセルの初期色。

*パーセント*<br/>
[in]透過性のパーセンテージを表す 0 ~ 100 の数値。 値 100 は、初期色が完全に透明であることを示します。

*パーセントR*<br/>
[in]赤コンポーネントの透明度の割合を表す 0 ~ 100 の数値。

*パーセントG*<br/>
[in]緑のコンポーネントの透明度の割合を表す 0 ~ 100 の数値。

*パーセントB*<br/>
[in]青コンポーネントの透明度の割合を表す 0 ~ 100 の数値。

*ピクセル数*<br/>
[in]ピクセルの基本色。

### <a name="return-value"></a>戻り値

半透明ピクセルの最終色。

### <a name="remarks"></a>解説

これは、半透明のビットマップを色分けするためのヘルパー クラスであり、プログラマが直接呼び出すデザインではありません。

*dstPixel*を持つメソッドのバージョンを使用すると、最終的な色は*dstPixel*と*srcPixel*の組み合わせになります。 *srcPixel カラー*は *、dstPixel*のベース カラーに対して部分的に透明な色です。

## <a name="cdrawingmanagerprepareshadowmask"></a><a name="prepareshadowmask"></a>:Pレパレシャドウマスク

影として使用できるビットマップを作成します。

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>パラメーター

*n深さ*<br/>
[in]影の幅と高さ。

*clrベース*<br/>
[in]影の色。

*iMin明るさ*<br/>
[in]影の最小輝度。

*iマックスブライトネス*<br/>
[in]影の最大輝度。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、作成されたビットマップへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

*nDepth*が 0 に設定されている場合、このメソッドは終了し、NULL を返します。 *nDepth*が 3 未満の場合、影の幅と高さは 3 ピクセルに設定されます。

## <a name="cdrawingmanagerrgbtohsl"></a><a name="rgbtohsl"></a>コブトマネージャー::RGBtoHSL

色を赤、緑、青 (RGB) 表現から色相、彩度、明度 (HSL) 表現に変換します。

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
|*Rgb*|[in]RGB 値で表した色。|
|*H*|[アウト]メソッドが色の色相を格納する倍精度浮動小数点型へのポインター。|
|*S*|[アウト]メソッドが色の彩度を格納する倍精度浮動小数点型へのポインター。|
|*L*|[アウト]メソッドが色の明度を格納する倍精度へのポインター。|

### <a name="remarks"></a>解説

色は HSV (色相、彩度、および値)、HSL (色相、彩度、明度)、または RGB (赤、緑、青) で表すことができます。 色の表現の詳細については、「[色](/windows/win32/uxguide/vis-color)」を参照してください。

*H*の戻り値は、0 と 1 の両方が赤を表す 0 と 1 の間の分数として表されます。 *S*と*L*の戻り値は、0 から 1 までの数値です。

## <a name="cdrawingmanagerrgbtohsv"></a><a name="rgbtohsv"></a>コブトマネージャー::RGBtoHSV

カラーを RGB 表現から HSV 表現に変換します。

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>パラメーター

*Rgb*<br/>
[in]RGB 表現で変換する色。

*H*<br/>
[アウト]このメソッドが結果の色相を格納する倍精度浮動小数点型へのポインター。

*S*<br/>
[アウト]このメソッドが結果として得られる色の彩度を格納する倍精度浮動小数点型へのポインター。

*V*<br/>
[アウト]このメソッドが色の結果の値を格納する倍精度浮動小数点型へのポインター。

### <a name="remarks"></a>解説

色は HSV (色相、彩度、および値)、HSL (色相、彩度、明度)、または RGB (赤、緑、青) で表すことができます。 色の表現の詳細については、「[色](/windows/win32/uxguide/vis-color)」を参照してください。

*H*の戻り値は 0 から 360 の間の数値で、0 と 360 の両方が赤を示します。 *S*と*V*の戻り値は、0 ~ 1 の数値です。

## <a name="cdrawingmanagersetalphapixel"></a><a name="setalphapixel"></a>コントロールマネージャー::セットアルファピクセル

ビットマップ内の透明ピクセルを色分けします。

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

*pビット*<br/>
[in]ビットマップのビット値へのポインター。

*Rect*<br/>
[in]アプリケーション内の四角形領域。 描画マネージャは、この領域の下と右に影を描画します。

*x*<br/>
[in]カラーに対するピクセルの水平座標。

*Y*<br/>
[in]カラーに対するピクセルの垂直方向の座標。

*パーセント*<br/>
[in]透明度の割合。

*サイズ*<br/>
[in]影の幅と高さ。

*clrベース*<br/>
[in]影の色。

*ビスライト*<br/>
[in]色を付けるピクセルを示すブール値パラメーター。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

このメソッドは、メソッドによって使用されるヘルパー メソッド[:Dです](#drawshadow)。 シャドウを描画する場合は、代わりに呼び出`CDrawingManager::DrawShadow`すことをお勧めします。

*bIsRight*が TRUE に設定されている場合、色のピクセルは*rect*の右端から*x*ピクセルで測定されます。 FALSE の場合、色のカラーは *、直辺*の左端から*x*ピクセル単位で測定されます。

## <a name="cdrawingmanagersetpixel"></a><a name="setpixel"></a>コントロール マネージャー::ピクセルを設定します。

ビットマップ内の 1 ピクセルを指定した色に変更します。

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
|*pビット*|[in]ビットマップのビット値へのポインター。|
|*Cx*|[in]ビットマップの幅の合計。|
|*Cy*|[in]ビットマップの合計の高さ。|
|*x*|[in]変更するビットマップ内のピクセルの x 座標。|
|*Y*|[in]変更するビットマップ内のピクセルの y 座標。|
|*色*|[in]指定された座標で識別されるピクセルの新しい色。|

## <a name="cdrawingmanagersmartmixcolors"></a><a name="smartmixcolors"></a>::スマートミックスカラー

加重比に基づいて 2 つの色を結合します。

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
|*color1*|[in]最初に混ぜる色。|
|*カラー2*|[in]ミックスする 2 番目の色。|
|*ドブルラム比*|[in]新しい色の明るさの比率。 `SmartMixColors`最終的な色を決定する前に、混合カラーの明度をこの比率で乗算します。|
|*k1*|[in]最初の色の重み付け比率。|
|*k2*|[in]2 番目の色の重み付け比率。|

### <a name="return-value"></a>戻り値

指定された色の加重混合を表す色。

### <a name="remarks"></a>解説

*k1*または*k2*がゼロより小さい場合、このメソッドはエラーで失敗します。 両方のパラメータが 0 に設定されている場合、メソッド`RGB(0, 0, 0)`は を返します。

加重比は、次の式で計算されます: (\*色1 k1 \* + color2 k2)/(k1 + k2)。 重み付け比率が決定された後、混合色の明度を計算します。 次に、輝度を*dblLumRatio*で乗算します。 値が 1.0 より大きい場合、メソッドは混合色の明度を新しい値に設定します。 それ以外の場合、明度は 1.0 に設定されます。

## <a name="cdrawingmanagerdrawrotated"></a><a name="drawrotated"></a>:Dロー回転

指定された四角形の内部にあるソース DC コンテンツを 90 度回転します。

```cpp
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>パラメーター

*レクトデスト*<br/>
コピー先の四角形。

*dcSrc*<br/>
ソース デバイス コンテキスト。

*回り時計回り*<br/>
TRUE は+90 度回転を示します。FALSE は -90 度回転を示します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
