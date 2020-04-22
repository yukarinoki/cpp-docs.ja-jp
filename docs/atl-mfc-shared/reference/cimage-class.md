---
title: Cイメージクラス
ms.date: 08/19/2019
f1_keywords:
- CImage
- ATLIMAGE/ATL::CImage
- ATLIMAGE/ATL::CImage::CImage
- ATLIMAGE/ATL::CImage::AlphaBlend
- ATLIMAGE/ATL::CImage::Attach
- ATLIMAGE/ATL::CImage::BitBlt
- ATLIMAGE/ATL::CImage::Create
- ATLIMAGE/ATL::CImage::CreateEx
- ATLIMAGE/ATL::CImage::Destroy
- ATLIMAGE/ATL::CImage::Detach
- ATLIMAGE/ATL::CImage::Draw
- ATLIMAGE/ATL::CImage::GetBits
- ATLIMAGE/ATL::CImage::GetBPP
- ATLIMAGE/ATL::CImage::GetColorTable
- ATLIMAGE/ATL::CImage::GetDC
- ATLIMAGE/ATL::CImage::GetExporterFilterString
- ATLIMAGE/ATL::CImage::GetHeight
- ATLIMAGE/ATL::CImage::GetImporterFilterString
- ATLIMAGE/ATL::CImage::GetMaxColorTableEntries
- ATLIMAGE/ATL::CImage::GetPitch
- ATLIMAGE/ATL::CImage::GetPixel
- ATLIMAGE/ATL::CImage::GetPixelAddress
- ATLIMAGE/ATL::CImage::GetTransparentColor
- ATLIMAGE/ATL::CImage::GetWidth
- ATLIMAGE/ATL::CImage::IsDIBSection
- ATLIMAGE/ATL::CImage::IsIndexed
- ATLIMAGE/ATL::CImage::IsNull
- ATLIMAGE/ATL::CImage::IsTransparencySupported
- ATLIMAGE/ATL::CImage::Load
- ATLIMAGE/ATL::CImage::LoadFromResource
- ATLIMAGE/ATL::CImage::MaskBlt
- ATLIMAGE/ATL::CImage::PlgBlt
- ATLIMAGE/ATL::CImage::ReleaseDC
- ATLIMAGE/ATL::CImage::ReleaseGDIPlus
- ATLIMAGE/ATL::CImage::Save
- ATLIMAGE/ATL::CImage::SetColorTable
- ATLIMAGE/ATL::CImage::SetPixel
- ATLIMAGE/ATL::CImage::SetPixelIndexed
- ATLIMAGE/ATL::CImage::SetPixelRGB
- ATLIMAGE/ATL::CImage::SetTransparentColor
- ATLIMAGE/ATL::CImage::StretchBlt
- ATLIMAGE/ATL::CImage::TransparentBlt
helpviewer_keywords:
- jpeg files
- bitmaps [C++], ATL and MFC support for
- images [C++], ATL and MFC support for
- gif files, ATL and MFC support
- .gif files, ATL and MFC support
- PNG files, ATL and MFC support
- CImage class
- transparent color
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
ms.openlocfilehash: a6d20e1bf12f5fe7d1e9b41d88b088ca9fad35ed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747182"
---
# <a name="cimage-class"></a>Cイメージクラス

`CImage`は、JPEG、GIF、BMP、および PNG (ポータブル ネットワーク グラフィックス) 形式で画像を読み込んで保存する機能など、ビットマップのサポートを強化します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CImage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[イメージ::CImage](#cimage)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イメージ::アルファブレンド](#alphablend)|透明または半透明のピクセルを持つビットマップを表示します。|
|[CImage::アタッチ](#attach)|オブジェクトに HBITMAP を`CImage`アタッチします。 DIB セクション以外のビットマップまたは DIB セクション ビットマップと共に使用できます。|
|[イメージ::ビットブレット](#bitblt)|ソース デバイス コンテキストからこの現在のデバイス コンテキストにビットマップをコピーします。|
|[CImage::作成](#create)|DIB セクション ビットマップを作成し、以前に構築`CImage`されたオブジェクトにアタッチします。|
|[イメージ::作成します。](#createex)|DIB セクション ビットマップを作成し(追加のパラメータを使用して)、以前`CImage`に構築したオブジェクトにアタッチします。|
|[CImage::Dエストロイ](#destroy)|`CImage`オブジェクトからビットマップをデタッチし、ビットマップを破棄します。|
|[CImage::Dエタッハ](#detach)|`CImage`ビットマップをオブジェクトからデタッチします。|
|[イメージ::Dロー](#draw)|コピー元の四角形からコピー先の四角形にビットマップをコピーします。 `Draw`必要に応じて、ビットマップを描画先の四角形のサイズに合わせて伸縮し、アルファ ブレンディングと透明色を処理します。|
|[イメージ::ゲットビット](#getbits)|ビットマップの実際のピクセル値へのポインターを取得します。|
|[イメージ::ゲットブップ](#getbpp)|ピクセルあたりのビットを取得します。|
|[を見る](#getcolortable)|カラー テーブル内のエントリの範囲から、赤、緑、青 (RGB) のカラー値を取得します。|
|[イメージ::ゲットDC](#getdc)|現在のビットマップが選択されているデバイス コンテキストを取得します。|
|[を使用します。](#getexporterfilterstring)|使用可能な画像形式とその説明を検索します。|
|[を取得します。](#getheight)|現在のイメージの高さをピクセル単位で取得します。|
|[を使用します。](#getimporterfilterstring)|使用可能な画像形式とその説明を検索します。|
|[をクリックします。](#getmaxcolortableentries)|カラー テーブル内のエントリの最大数を取得します。|
|[イメージ::ゲットピッチ](#getpitch)|現在のイメージのピッチをバイト単位で取得します。|
|[イメージ::ゲットピクセル](#getpixel)|*x*および*y*で指定されたピクセルの色を取得します。|
|[を見る](#getpixeladdress)|指定したピクセルのアドレスを取得します。|
|[透明色を取得します。](#gettransparentcolor)|カラー テーブル内の透明色の位置を取得します。|
|[イメージ::取得幅](#getwidth)|現在のイメージの幅をピクセル単位で取得します。|
|[イメージ::イズイブセクション](#isdibsection)|アタッチされたビットマップが DIB セクションかどうかを判断します。|
|[インデックス付け](#isindexed)|ビットマップの色がインデックス付きパレットにマップされることを示します。|
|[を使用します。](#isnull)|ソース ビットマップが現在読み込まれているかどうかを示します。|
|[をサポートしています。](#istransparencysupported)|アプリケーションが透明なビットマップをサポートするかどうかを示します。|
|[読み込み](#load)|指定したファイルからイメージを読み込みます。|
|[リソースから読み込む](#loadfromresource)|指定したリソースからイメージを読み込みます。|
|[イメージ::マスクブラット](#maskblt)|指定したマスクとラスター操作を使用して、変換元とコピー先のビットマップのカラー データを結合します。|
|[CImage::PlgBlt](#plgblt)|転送元のデバイス コンテキスト内の四角形から、ターゲット デバイス コンテキストの並列表示へのビット ブロック転送を実行します。|
|[CImage::リリースDC](#releasedc)|[CImage::GetDC](#getdc)で取得されたデバイス コンテキストを解放します。|
|[イメージ::リリースGDIプラス](#releasegdiplus)|GDI+ によって使用されるリソースを解放します。 グローバル`CImage`オブジェクトによって作成されたリソースを解放するには、呼び出す必要があります。|
|[CImage::保存](#save)|イメージを指定した型として保存します。 `Save`イメージ オプションを指定できません。|
|[を設定します。](#setcolortable)|DIB セクションのカラー テーブルのエントリ範囲に、赤、緑、青の RGB) カラー値を設定します。|
|[イメージ::セットピクセル](#setpixel)|指定した座標のピクセルを指定した色に設定します。|
|[イメージ::セットピクセルインデックス](#setpixelindexed)|指定した座標のピクセルを、パレットの指定したインデックス位置の色に設定します。|
|[を設定します。](#setpixelrgb)|指定した座標のピクセルを、指定した赤、緑、青 (RGB) の値に設定します。|
|[カラーカラーを設定します。](#settransparentcolor)|透明として扱われる色のインデックスを設定します。 パレット内の 1 色だけが透明にできます。|
|[CImage::ストレッチブラット](#stretchblt)|必要に応じて、コピー元の四角形からコピー先の四角形にビットマップをコピーし、必要に応じて、ビットマップを拡大または圧縮して、目的の四角形のサイズに合わせます。|
|[CImage::トランスペアレントブレット](#transparentblt)|ソース デバイス コンテキストからこの現在のデバイス コンテキストに透明な色を持つビットマップをコピーします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を使用します。](#operator_hbitmap)|オブジェクトにアタッチされた Windows`CImage`ハンドルを返します。|

## <a name="remarks"></a>解説

`CImage`は、デバイスに依存しないビットマップ (DIB) セクションであるビットマップを取ります。ただし、DIB セクションのみで[作成](#create)または[CImage::Load を](#load)使用できます。 [[アタッチ]](#attach)を使用して DIB セクション`CImage`以外のビットマップをオブジェクトにアタッチできますが、次`CImage`の方法は使用できません。

- [ゲットビット](#getbits)

- [カラー テーブルを取得します。](#getcolortable)

- [テーブルエントリ](#getmaxcolortableentries)

- [ゲットピッチ](#getpitch)

- [ピクセルアドレスを取得します。](#getpixeladdress)

- [IsIndexed](#isindexed)

- [カラーテーブルを設定します。](#setcolortable)

アタッチされたビットマップが DIB セクションかどうかを確認するには[、IsDibSection](#isdibsection)を呼び出します。

> [!NOTE]
> Visual Studio .NET 2003 では、このクラスは作成された`CImage`オブジェクトの数を保持します。 カウントが 0 になるたびに、`GdiplusShutdown`関数は自動的に呼び出され、GDI+ によって使用されるリソースが解放されます。 これにより、DLL`CImage`によって直接または間接的に作成されたオブジェクトは常に適切に破棄され`GdiplusShutdown`、から呼び`DllMain`出されません。

> [!NOTE]
> DLL`CImage`でグローバル オブジェクトを使用することはお勧めしません。 DLL でグローバル`CImage`オブジェクトを使用する必要がある場合は[、CImage::ReleaseGDIPlus](#releasegdiplus)を呼び出して、GDI+ で使用されるリソースを明示的に解放します。

`CImage`新しい[CDC](../../mfc/reference/cdc-class.md)に選択することはできません。 `CImage`は、イメージ用に独自の HDC を作成します。 HBITMAP は一度に 1 つの HDC にしか選択できないため、に関連`CImage`付けられた HBITMAP を別の HDC に選択することはできません。 CDC が必要な場合は、 から HDC を`CImage`取得し、 [CDC::FromHandle](../../mfc/reference/cdc-class.md#fromhandle)に渡します。

## <a name="example"></a>例

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

MFC プロジェクト`CImage`で使用する場合は、プロジェクトのどのメンバー関数が[CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクトへのポインターを必要とするかをメモします。 `CImage` [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)のような関数で使用する場合は[、CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle)を使用し、HBITMAP`CImage`を渡し、返された`CBitmap*`を使用します。

## <a name="example"></a>例

```cpp
void CMyDlg::OnRButtonDown(UINT nFlags, CPoint point)
{
    UNREFERENCED_PARAMETER(nFlags);

    CBitmap* pBitmap = CBitmap::FromHandle(m_myImage);
    m_pmenuPop->AppendMenu(0, ID_BMPCOMMAND, pBitmap);
    ClientToScreen(&point);
    m_pmenuPop->TrackPopupMenu(TPM_RIGHTBUTTON | TPM_LEFTALIGN, point.x,
    point.y, this);
}
```

を`CImage`通じて、DIB セクションの実際のビットにアクセスできます。 以前に`CImage`Win32 HBITMAP または DIB セクションを使用した場所であれば、オブジェクトを使用できます。

MFC または`CImage`ATL から使用できます。

> [!NOTE]
> を使用して`CImage`プロジェクトを作成する場合は、 `CString` *atlimage.h*をインクルードする前に定義する必要があります。 プロジェクトで MFC を使用せずに ATL を使用する場合は *、atlimage.h*をインクルードする前に*atlstr.h を*インクルードします。 プロジェクトで MFC を使用している場合 (または MFC サポートを持つ ATL プロジェクトの場合 *)、atlimage.h*をインクルードする前に*afxstr.h*をインクルードします。<br/>
> <br/>
> 同様に *、atlimpl.cpp*を含める前に*atlimage.h*を含める必要があります。 これを簡単に行うには *、pch.h* (Visual Studio 2017 以前の*stdafx.h)* に*atlimage.h*を含めます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlimage.h

## <a name="cimagealphablend"></a><a name="alphablend"></a>イメージ::アルファブレンド

透明または半透明のピクセルを持つビットマップを表示します。

```
BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    const POINT& pointDest,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER) const throw();

BOOL AlphaBlend(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);

BOOL AlphaBlend(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    BYTE bSrcAlpha = 0xff,
    BYTE bBlendOp = AC_SRC_OVER);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ターゲット デバイス コンテキストへのハンドル。

*xDest*<br/>
移動先の四角形の左上隅の x 座標 (論理単位)。

*イデスト*<br/>
移動先の四角形の左上隅の y 座標 (論理単位)。

*bSrcアルファ*<br/>
ソース ビットマップ全体で使用されるアルファ透明度の値。 デフォルトの 0xff (255) では、イメージが不透明であり、ピクセル単位のアルファ値のみを使用することを前提としています。

*ブブレンドオップ*<br/>
ソースビットマップとターゲットビットマップのアルファブレンド関数、ソースビットマップ全体に適用されるグローバルアルファ値、およびソースビットマップのフォーマット情報。 ソースとターゲットのブレンド関数は現在、AC_SRC_OVERに制限されています。

*ポイントデスト*<br/>
移動先の四角形の左上隅を論理単位で識別する[POINT](/windows/win32/api/windef/ns-windef-point)構造体への参照。

*幅*<br/>
コピー先の四角形の幅 (論理単位)。

*最も高い*<br/>
コピー先の四角形の高さ (論理単位)。

*xSrc*<br/>
ソース四角形の左上隅の論理 x 座標。

*ySrc*<br/>
ソース四角形の左上隅の論理 y 座標。

*幅*<br/>
ソース四角形の幅 (論理単位)。

*NSrcHeight*<br/>
ソース四角形の高さ (論理単位)。

*レクトデスト*<br/>
宛先を識別する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*レクトスrc*<br/>
ソースを識別する`RECT`構造体への参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

アルファ ブレンド ビットマップは、ピクセル単位でのカラー ブレンドをサポートします。

*bBlendOp*がデフォルトの AC_SRC_OVER に設定されている場合、ソース ビットマップは、ソース ピクセルのアルファ値に基づいて、ターゲット ビットマップの上に配置されます。

## <a name="cimageattach"></a><a name="attach"></a>CImage::アタッチ

オブジェクトに*hBitmap* `CImage`をアタッチします。

```cpp
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>パラメーター

*hビットマップ*<br/>
HBITMAP へのハンドル。

*eオリエンテーション*<br/>
ビットマップの方向を指定します。 以下のいずれかを指定できます。

- DIBOR_DEFAULT ビットマップの向きは、オペレーティング システムによって決まります。

- DIBOR_BOTTOMUP ビットマップの行は逆の順序です。 これにより[、CImage::GetBits は](#getbits)ビットマップ バッファーの末尾付近にポインターを返し[、CImage::GetPitch は](#getpitch)負の数を返します。

- DIBOR_TOPDOWN ビットマップの行は上から下の順に並びます。 これにより[、CImage::GetBits は](#getbits)ビットマップ バッファーの最初のバイトへのポインターを返し[、CImage::GetPitch は](#getpitch)正の数を返します。

### <a name="remarks"></a>解説

ビットマップは、DIB セクション以外のビットマップまたは DIB セクション ビットマップのいずれかです。 DIB セクション ビットマップでのみ使用できるメソッドの一覧については[、IsDIBSection](#isdibsection)を参照してください。

## <a name="cimagebitblt"></a><a name="bitblt"></a>イメージ::ビットブレット

ソース デバイス コンテキストからこの現在のデバイス コンテキストにビットマップをコピーします。

```
BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const POINT& pointDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    DWORD dwROP = SRCCOPY) const throw();

BOOL BitBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
宛先 HDC。

*xDest*<br/>
移動先の四角形の左上隅の論理 x 座標。

*イデスト*<br/>
移動先の四角形の左上隅の論理 y 座標。

*Dwrop*<br/>
実行するラスター操作。 ラスターオペレーション コードは、ソース、出力先、および (現在選択されているブラシで定義されている) パターンのビットを組み合わせて、目的地を形成する方法を正確に定義します。 その他のラスター オペレーション コードとその説明については、Windows SDK の[BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt)を参照してください。

*ポイントデスト*<br/>
移動先の四角形の左上隅を示す[POINT](/windows/win32/api/windef/ns-windef-point)構造体。

*幅*<br/>
コピー先の四角形の幅 (論理単位)。

*最も高い*<br/>
コピー先の四角形の高さ (論理単位)。

*xSrc*<br/>
ソース四角形の左上隅の論理 x 座標。

*ySrc*<br/>
ソース四角形の左上隅の論理 y 座標。

*レクトデスト*<br/>
コピー先の四角形を示す[RECT](/windows/win32/api/windef/ns-windef-rect)構造体。

*ポイントスrc*<br/>
ソース`POINT`四角形の左上隅を示す構造体。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[「ビットブレット](/windows/win32/api/wingdi/nf-wingdi-bitblt)」を参照してください。

## <a name="cimagecimage"></a><a name="cimage"></a>イメージ::CImage

`CImage` オブジェクトを構築します。

```
CImage() throw();
```

### <a name="remarks"></a>解説

オブジェクトを構築したら、[作成](#create)、[読み込み](#load)[、LoadFromResource、](#loadfromresource)または[アタッチ](#attach)を呼び出して、オブジェクトにビットマップをアタッチします。

**注**Visual Studio では、このクラスは作成されたオブジェクトの`CImage`数を保持します。 カウントが 0 になるたびに、`GdiplusShutdown`関数は自動的に呼び出され、GDI+ によって使用されるリソースが解放されます。 これにより、DLL`CImage`によって直接または間接的に作成されたオブジェクトは常に適切に破棄され`GdiplusShutdown`、DllMain から呼び出されません。

DLL`CImage`でグローバル オブジェクトを使用することはお勧めしません。 DLL でグローバル`CImage`オブジェクトを使用する必要がある場合は[、CImage::ReleaseGDIPlus](#releasegdiplus)を呼び出して、GDI+ で使用されるリソースを明示的に解放します。

## <a name="cimagecreate"></a><a name="create"></a>CImage::作成

ビットマップを`CImage`作成し、以前に構築`CImage`したオブジェクトにアタッチします。

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
ビットマップの`CImage`幅 (ピクセル単位)。

*nHeight*<br/>
ビットマップの`CImage`高さ (ピクセル単位)。 *nHeight が*正の場合、ビットマップはボトムアップ DIB で、原点は左下隅になります。 *nHeight が*負の場合、ビットマップはトップダウン DIB で、原点は左上隅です。

*nBPP*<br/>
ビットマップ内のピクセルあたりのビット数。 通常4、8、16、24、または32。 モノクロビットマップまたはマスクの場合は 1 を指定できます。

*dwFlags*<br/>
ビットマップ オブジェクトにアルファ チャネルがあるかどうかを指定します。 0 個以上の次の値を組み合わせることができます。

- *アルファチャンネルを作成します。**nBPP*が 32 で *、eCompression*がBI_RGB場合にのみ使用できます。 指定した場合、作成されたイメージは各ピクセルのアルファ (透明度) 値を持ち、各ピクセルの 4 バイト目に格納されます (非アルファ 32 ビット イメージでは使用されません)。 このアルファ チャネルは[、CImage::AlphaBlend](#alphablend)を呼び出すときに自動的に使用されます。

> [!NOTE]
> [CImage::Draw](#draw)の呼び出しでは、アルファ チャネルを持つイメージは自動的にアルファブレンドされて宛先に合成されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="cimagecreateex"></a><a name="createex"></a>イメージ::作成します。

ビットマップを`CImage`作成し、以前に構築`CImage`したオブジェクトにアタッチします。

```
BOOL CreateEx(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD eCompression,
    const DWORD* pdwBitmasks = NULL,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
ビットマップの`CImage`幅 (ピクセル単位)。

*nHeight*<br/>
ビットマップの`CImage`高さ (ピクセル単位)。 *nHeight が*正の場合、ビットマップはボトムアップ DIB で、原点は左下隅になります。 *nHeight が*負の場合、ビットマップはトップダウン DIB で、原点は左上隅です。

*nBPP*<br/>
ビットマップ内のピクセルあたりのビット数。 通常4、8、16、24、または32。 モノクロビットマップまたはマスクの場合は 1 を指定できます。

*e圧縮*<br/>
圧縮ボトムアップビットマップの圧縮タイプを指定します(上から下のDDBは圧縮できません)。 次の値のいずれかです。

- BI_RGB 形式が圧縮解除されます。 呼び出し`CImage::CreateEx`時にこの値を指定`CImage::Create`することは、 を呼び出すのと同じです。

- BI_BITFIELDSフォーマットは非圧縮で、カラーテーブルは、各ピクセルの赤、緑、青の各要素をそれぞれ指定する 3 つの DWORD カラーマスクで構成されます。 これは、16 bpp および 32 bpp ビットマップで使用する場合に有効です。

*pdw ビットフィールド*<br/>
*eCompression*が BI_BITFIELDS に設定されている場合にのみ使用され、それ以外の場合は NULL にする必要があります。 色の赤、緑、青の各要素に使用される各ピクセルのビットを指定する 3 つの DWORD ビットマスクの配列へのポインター。 ビットフィールドの制限については、Windows SDK の[BITMAPINFOHEADER](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader)を参照してください。

*dwFlags*<br/>
ビットマップ オブジェクトにアルファ チャネルがあるかどうかを指定します。 0 個以上の次の値を組み合わせることができます。

- *アルファチャンネルを作成します。**nBPP*が 32 で *、eCompression*がBI_RGB場合にのみ使用できます。 指定した場合、作成されたイメージは各ピクセルのアルファ (透明度) 値を持ち、各ピクセルの 4 バイト目に格納されます (非アルファ 32 ビット イメージでは使用されません)。 このアルファ チャネルは[、CImage::AlphaBlend](#alphablend)を呼び出すときに自動的に使用されます。

   > [!NOTE]
   > [CImage::Draw](#draw)の呼び出しでは、アルファ チャネルを持つイメージは自動的にアルファブレンドされて宛先に合成されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。 それ以外の場合は FALSE。

### <a name="example"></a>例

次の例では、16 ビットを使用して各ピクセルをエンコードする 100x100 ピクセルビットマップを作成します。 指定された 16 ビット ピクセルでは、ビット 0 から 3 が赤のコンポーネントをエンコードし、ビット 4 から 7 が緑色をエンコードし、ビット 8 から 11 が青をエンコードします。 残りの 4 ビットは使用されていません。

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

## <a name="cimagedestroy"></a><a name="destroy"></a>CImage::Dエストロイ

`CImage`オブジェクトからビットマップをデタッチし、ビットマップを破棄します。

```cpp
void Destroy() throw();
```

## <a name="cimagedetach"></a><a name="detach"></a>CImage::Dエタッハ

`CImage`オブジェクトからビットマップをデタッチします。

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>戻り値

ビットマップをデタッチするハンドル。

## <a name="cimagedraw"></a><a name="draw"></a>イメージ::Dロー

ソース デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。

```
BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest) const throw();

BOOL Draw(
    HDC hDestDC,
    const POINT& pointDest) const throw();

BOOL Draw(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight) const throw();

BOOL Draw(
    HDC hDestDC,
    const RECT& rectDest) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ターゲット デバイス コンテキストへのハンドル。

*xDest*<br/>
移動先の四角形の左上隅の x 座標 (論理単位)。

*イデスト*<br/>
移動先の四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
コピー先の四角形の幅 (論理単位)。

*最も高い*<br/>
コピー先の四角形の高さ (論理単位)。

*xSrc*<br/>
ソース四角形の左上隅の x 座標 (論理単位)。

*ySrc*<br/>
ソース四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
ソース四角形の幅 (論理単位)。

*NSrcHeight*<br/>
ソース四角形の高さ (論理単位)。

*レクトデスト*<br/>
宛先を識別する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*レクトスrc*<br/>
ソースを識別する`RECT`構造体への参照。

*ポイントデスト*<br/>
移動先の四角形の左上隅を論理単位で識別する[POINT](/windows/win32/api/windef/ns-windef-point)構造体への参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`Draw`画像に透明なカラーまたはアルファチャンネルが含まれている場合を除き[、StretchBlt](#stretchblt)と同じ操作を実行します。 その場合は、`Draw`必要に応じて[トランスペアレントまたは](#transparentblt)[アルファブレンド](#alphablend)と同じ操作を実行します。

ソース矩形`Draw`を指定しないバージョンの場合、ソースイメージ全体がデフォルトです。 のバージョンで、`Draw`コピー先の四角形のサイズを指定していない場合、ソース イメージのサイズは既定であり、拡大または縮小は行われません。

## <a name="cimagegetbits"></a><a name="getbits"></a>イメージ::ゲットビット

ビットマップ内の指定されたピクセルの実際のビット値へのポインターを取得します。

```cpp
void* GetBits() throw();
```

### <a name="return-value"></a>戻り値

ビットマップ バッファーへのポインター。 ビットマップがボトムアップ DIB の場合、ポインターはバッファーの末尾付近を指します。 ビットマップがトップダウン DIB の場合、ポインターはバッファーの最初のバイトを指します。

### <a name="remarks"></a>解説

このポインターを使用すると[、GetPitch](#getpitch)によって返される値と共に、イメージ内の個々のピクセルを検索して変更できます。

> [!NOTE]
> このメソッドは、DIB セクションビットマップのみをサポートします。したがって、DIB セクションのピクセルと`CImage`同じ方法でオブジェクトのピクセルにアクセスします。 返されたポインターは、位置 (0, 0) のピクセルを指しています。

## <a name="cimagegetbpp"></a><a name="getbpp"></a>イメージ::ゲットブップ

ピクセルあたりのビット数を取得します。

```
int GetBPP() const throw();
```

### <a name="return-value"></a>戻り値

ピクセルあたりのビット数。

### <a name="remarks"></a>解説

この値によって、各ピクセルを定義するビット数とビットマップの最大色数が決まります。

ピクセルあたりのビットは通常 1、4、8、16、24、または 32 です。 この値`biBitCount`の詳細については、Windows SDK の[BITMAPINFOHEADER](/windows/win32/api/wingdi/ns-wingdi-bitmapinfoheader)のメンバーを参照してください。

## <a name="cimagegetcolortable"></a><a name="getcolortable"></a>を見る

DIB セクションのパレット内のエントリの範囲から、赤、緑、青 (RGB) の色の値を取得します。

```cpp
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>パラメーター

*最初の色*<br/>
取得する最初のエントリのカラー テーブル インデックス。

*nカラー*<br/>
取得するカラー テーブル エントリの数。

*プルグカラー*<br/>
カラー テーブルエントリを取得するための[RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad)構造体の配列へのポインター。

## <a name="cimagegetdc"></a><a name="getdc"></a>イメージ::ゲットDC

現在選択されているイメージがあるデバイス コンテキストを取得します。

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>戻り値

デバイス コンテキストを識別するハンドル。

### <a name="remarks"></a>解説

への呼び出`GetDC`しごとに[、ReleaseDC](#releasedc)への後続の呼び出しが必要です。

## <a name="cimagegetexporterfilterstring"></a><a name="getexporterfilterstring"></a>を使用します。

画像の保存に使用できる画像形式を検索します。

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>パラメーター

*ストルファー*<br/>
`CSimpleString` オブジェクトへの参照です。 詳細については **、「解説」** を参照してください。

*ファイルの種類*<br/>
文字列内のファイルの種類のいずれかに対応する各要素を持つ GUID の配列。 以下の*pszAllFiles 説明*の例では *、aguidFileTypes*[0] はGUID_NULLされ、残りの配列値は現在のオペレーティング システムでサポートされているイメージ ファイル形式です。

> [!NOTE]
> 定数の完全な一覧については、Windows SDK の **「イメージ ファイル形式の定数**」を参照してください。

*説明*<br/>
このパラメーターが NULL でない場合、フィルター文字列はリストの先頭に 1 つの追加フィルターを持ちます。 このフィルターは、その説明に*pszAllFilesDescription*の現在の値を持ち、リスト内の他のエクスポータでサポートされている任意の拡張子のファイルを受け入れます。

次に例を示します。

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dw除外*<br/>
リストから除外するファイルの種類を指定するビット フラグのセット。 許可されるフラグは次のとおりです。

- `excludeGIF`= 0x01 GIF ファイルを除外します。

- `excludeBMP`= 0x02 BMP (Windows ビットマップ) ファイルを除外します。

- `excludeEMF`= 0x04 EMF (拡張メタファイル) ファイルを除外します。

- `excludeWMF`= 0x08 WMF (Windows メタファイル) ファイルを除外します。

- `excludeJPEG`= 0x10 JPEG ファイルを除外します。

- `excludePNG`= 0x20 PNG ファイルを除外します。

- `excludeTIFF`= 0x40 TIFF ファイルを除外します。

- `excludeIcon`= 0x80 ICO (Windows アイコン) ファイルを除外します。

- `excludeOther`= 0x8000000 上記以外のファイルタイプを除外します。

- `excludeDefaultLoad`= 0 読み込みでは、すべてのファイルタイプがデフォルトで含まれます。

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`保存のために、これらのファイルは通常特別な要件を持つため、デフォルトで除外されます。

*chセパレータ*<br/>
イメージ形式の間で使用される区切り記号。 詳細については **、「解説」** を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

結果の形式文字列を MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md)オブジェクトに渡して、[ファイル名を付けて保存] ダイアログ ボックスで使用可能なイメージ形式のファイル拡張子を公開できます。

パラメータ*strExporter*の形式は次のとおりです。

ファイルの\*説明0&#124;.ext0&#124;\*ファイル説明1&#124;.ext1&#124;..ファイルの*n*説明\*n&#124;.ext *n*&#124;&#124;

ここで '&#124;' は で指定`chSeparator`される区切り文字です。 次に例を示します。

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

MFC`CFileDialog`オブジェクトにこの文字列を渡す場合は、既定の区切り文字 '&#124;' を使用します。 この文字列を [ファイルの保存] ダイアログ ボックスに渡す場合は、null 区切り文字 '\0' を使用します。

## <a name="cimagegetheight"></a><a name="getheight"></a>を取得します。

イメージの高さをピクセル単位で取得します。

```
int GetHeight() const throw();
```

### <a name="return-value"></a>戻り値

イメージの高さ (ピクセル単位)。

## <a name="cimagegetimporterfilterstring"></a><a name="getimporterfilterstring"></a>を使用します。

イメージの読み込みに使用できるイメージ形式を検索します。

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>パラメーター

*str輸入者*<br/>
`CSimpleString` オブジェクトへの参照です。 詳細については **、「解説」** を参照してください。

*ファイルの種類*<br/>
文字列内のファイルの種類のいずれかに対応する各要素を持つ GUID の配列。 以下の*pszAllFiles 説明*の例では、aguidFileTypes [0] は、残りの配列値と共にGUID_NULLされ、現在のオペレーティング システムでサポートされているイメージ ファイル形式です。 *aguidFileTypes*

> [!NOTE]
> 定数の完全な一覧については、Windows SDK の **「イメージ ファイル形式の定数**」を参照してください。

*説明*<br/>
このパラメーターが NULL でない場合、フィルター文字列はリストの先頭に 1 つの追加フィルターを持ちます。 このフィルターは、その説明に*pszAllFilesDescription*の現在の値を持ち、リスト内の他のエクスポータでサポートされている任意の拡張子のファイルを受け入れます。

次に例を示します。

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dw除外*<br/>
リストから除外するファイルの種類を指定するビット フラグのセット。 許可されるフラグは次のとおりです。

- `excludeGIF`= 0x01 GIF ファイルを除外します。

- `excludeBMP`= 0x02 BMP (Windows ビットマップ) ファイルを除外します。

- `excludeEMF`= 0x04 EMF (拡張メタファイル) ファイルを除外します。

- `excludeWMF`= 0x08 WMF (Windows メタファイル) ファイルを除外します。

- `excludeJPEG`= 0x10 JPEG ファイルを除外します。

- `excludePNG`= 0x20 PNG ファイルを除外します。

- `excludeTIFF`= 0x40 TIFF ファイルを除外します。

- `excludeIcon`= 0x80 ICO (Windows アイコン) ファイルを除外します。

- `excludeOther`= 0x8000000 上記以外のファイルタイプを除外します。

- `excludeDefaultLoad`= 0 読み込みでは、すべてのファイルタイプがデフォルトで含まれます。

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF`保存のために、これらのファイルは通常特別な要件を持つため、デフォルトで除外されます。

*chセパレータ*<br/>
イメージ形式の間で使用される区切り記号。 詳細については **、「解説」** を参照してください。

### <a name="remarks"></a>解説

結果の形式文字列を MFC [CFileDialog](../../mfc/reference/cfiledialog-class.md)オブジェクトに渡して、[**ファイルを開く**] ダイアログ ボックスで使用可能なイメージ形式のファイル拡張子を公開できます。

パラメータ*strImporter*の形式は次のとおりです。

ファイルの\*説明0&#124;.ext0&#124;\*ファイル説明1&#124;.ext1&#124;..ファイルの*n*説明\*n&#124;.ext *n*&#124;&#124;

ここで '&#124;' は *、chSeparator*で指定される区切り文字です。 次に例を示します。

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

MFC`CFileDialog`オブジェクトにこの文字列を渡す場合は、既定の区切り文字 '&#124;' を使用します。 この文字列を [**ファイルを開く]** ダイアログ ボックスに渡す場合は、null 区切り文字 '\0' を使用します。

## <a name="cimagegetmaxcolortableentries"></a><a name="getmaxcolortableentries"></a>をクリックします。

カラー テーブル内のエントリの最大数を取得します。

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>戻り値

カラー テーブルのエントリ数。

### <a name="remarks"></a>解説

このメソッドは、DIB セクション ビットマップのみをサポートします。

## <a name="cimagegetpitch"></a><a name="getpitch"></a>イメージ::ゲットピッチ

イメージのピッチを取得します。

```
int GetPitch() const throw();
```

### <a name="return-value"></a>戻り値

イメージのピッチ。 戻り値が負の場合、ビットマップはボトムアップ DIB で、原点は左下隅になります。 戻り値が正の場合、ビットマップは上から下の DIB で、原点は左上隅です。

### <a name="remarks"></a>解説

ピッチは、1 つのビットマップ行の先頭と次のビットマップ行の先頭を表す 2 つのメモリ アドレス間の距離 (バイト単位) です。 ピッチはバイト単位で測定されるため、画像のピッチはピクセル形式を決定するのに役立ちます。 ピッチには、ビットマップ用に予約された追加のメモリを含めることもできます。

`GetPitch` [GetBits](#getbits)と共に使用すると、画像の個々のピクセルを検索できます。

> [!NOTE]
> このメソッドは、DIB セクション ビットマップのみをサポートします。

## <a name="cimagegetpixel"></a><a name="getpixel"></a>イメージ::ゲットピクセル

*x*および*y*で指定された位置にあるピクセルの色を取得します。

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
ピクセルの x 座標。

*Y*<br/>
ピクセルの y 座標。

### <a name="return-value"></a>戻り値

ピクセルの赤、緑、青 (RGB) の値。 ピクセルが現在のクリッピング領域の外側にある場合、戻り値はCLR_INVALID。

## <a name="cimagegetpixeladdress"></a><a name="getpixeladdress"></a>を見る

ピクセルの正確なアドレスを取得します。

```cpp
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
ピクセルの x 座標。

*Y*<br/>
ピクセルの y 座標。

### <a name="remarks"></a>解説

アドレスは、ピクセルの座標、ビットマップのピッチ、およびピクセルあたりのビット数に従って決定されます。

ピクセルあたりのビット数が 8 ビット未満の形式の場合、このメソッドはピクセルを含むバイトのアドレスを返します。 たとえば、イメージ形式がピクセルあたり 4 ビットの場合`GetPixelAddress`、バイトの最初のピクセルのアドレスを返し、1 バイトあたり 2 ピクセルを計算する必要があります。

> [!NOTE]
> このメソッドは、DIB セクション ビットマップのみをサポートします。

## <a name="cimagegettransparentcolor"></a><a name="gettransparentcolor"></a>透明色を取得します。

カラー パレット内の透過色のインデックス付きの位置を取得します。

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>戻り値

透明色のインデックス。

## <a name="cimagegetwidth"></a><a name="getwidth"></a>イメージ::取得幅

イメージの幅 (ピクセル単位) を取得します。

```
int GetWidth() const throw();
```

### <a name="return-value"></a>戻り値

ビットマップの幅 (ピクセル単位)。

## <a name="cimageisdibsection"></a><a name="isdibsection"></a>イメージ::イズイブセクション

アタッチされたビットマップが DIB セクションかどうかを判断します。

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>戻り値

アタッチされたビットマップが DIB セクションの場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ビットマップが DIB セクションでない場合、DIB セクション`CImage`ビットマップのみをサポートする以下のメソッドは使用できません。

- [ゲットビット](#getbits)

- [カラー テーブルを取得します。](#getcolortable)

- [テーブルエントリ](#getmaxcolortableentries)

- [ゲットピッチ](#getpitch)

- [ピクセルアドレスを取得します。](#getpixeladdress)

- [IsIndexed](#isindexed)

- [カラーテーブルを設定します。](#setcolortable)

## <a name="cimageisindexed"></a><a name="isindexed"></a>インデックス付け

ビットマップのピクセルをカラー パレットにマップするかどうかを決定します。

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>戻り値

インデックスが作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ビットマップが 8 ビット (256 色) 以下の場合にのみ TRUE を返します。

> [!NOTE]
> このメソッドは、DIB セクション ビットマップのみをサポートします。

## <a name="cimageisnull"></a><a name="isnull"></a>を使用します。

ビットマップが現在読み込まれているかどうかを判断します。

```
bool IsNull() const throw();
```

### <a name="remarks"></a>解説

ビットマップが現在読み込まれていない場合、このメソッドは TRUE を返します。それ以外の場合は FALSE。

## <a name="cimageistransparencysupported"></a><a name="istransparencysupported"></a>をサポートしています。

アプリケーションが透明なビットマップをサポートするかどうかを示します。

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>戻り値

現在のプラットフォームが透過性をサポートする場合は、0 以外の値を指定します。 それ以外の場合は 0。

### <a name="remarks"></a>解説

戻り値が 0 以外で、透過性がサポートされている場合は[、AlphaBlend](#alphablend) [、TransparentBlt、](#transparentblt)または[Draw](#draw)を呼び出すと、透明な色が処理されます。

## <a name="cimageload"></a><a name="load"></a>読み込み

画像を読み込みます。

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
読み込むイメージ ファイルの名前を含む文字列へのポインター。

*pストリーム*<br/>
読み込むイメージ ファイルの名前を含むストリームへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

指定されたイメージを*読*み込*みます。*

有効な画像の種類は、BMP、GIF、JPEG、PNG、および TIFF です。

## <a name="cimageloadfromresource"></a><a name="loadfromresource"></a>リソースから読み込む

ビットマップ リソースからイメージを読み込みます。

```cpp
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
読み込むイメージを含むモジュールのインスタンスへのハンドル。

*リソース名*<br/>
読み込むイメージを含むリソースの名前を含む文字列へのポインター。

*リソース*<br/>
読み込むリソースの ID です。

### <a name="remarks"></a>解説

リソースは BITMAP 型である必要があります。

## <a name="cimagemaskblt"></a><a name="maskblt"></a>イメージ::マスクブラット

指定したマスクとラスター操作を使用して、変換元とコピー先のビットマップのカラー データを結合します。

```
BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    HBITMAP hbmMask,
    int xMask,
    int yMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const POINT& pointSrc,
    HBITMAP hbmMask,
    const POINT& pointMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();

BOOL MaskBlt(
    HDC hDestDC,
    const POINT& pointDest,
    HBITMAP hbmMask,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
実行可能ファイルにリソースが含まれているモジュールへのハンドル。

*xDest*<br/>
移動先の四角形の左上隅の x 座標 (論理単位)。

*イデスト*<br/>
移動先の四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
コピー先の四角形とソース ビットマップの幅 (論理単位)。

*最も高い*<br/>
コピー先の四角形と元のビットマップの高さ (論理単位)。

*xSrc*<br/>
ソース ビットマップの左上隅の論理 x 座標。

*ySrc*<br/>
ソース ビットマップの左上隅の論理 y 座標。

*hbmマスク*<br/>
ソース デバイス コンテキストでカラー ビットマップと組み合わせたモノクロ マスク ビットマップへのハンドル。

*xマスク*<br/>
*hbmMask*パラメーターで指定されたマスク ビットマップの水平方向のピクセル オフセット。

*yマスク*<br/>
*hbmMask*パラメーターで指定されたマスク ビットマップの垂直ピクセル オフセット。

*Dwrop*<br/>
ソース データとターゲット データの組み合わせを制御するためにメソッドが使用する、前景と背景の 3 項ラスター オペレーション コードを指定します。 バックグラウンド ラスターオペレーション コードは、この値の上位ワードの上位バイトに格納されます。前景ラスターオペレーションコードは、この値の上位ワードの下位バイトに格納されます。この値の下位ワードは無視され、ゼロでなければなりません。 このメソッドのコンテキストでのフォアグラウンドとバックグラウンドの説明については、Windows `MaskBlt` SDK を参照してください。 一般的なラスター オペレーション コードの一`BitBlt`覧については、Windows SDK を参照してください。

*レクトデスト*<br/>
宛先を識別する`RECT`構造体への参照。

*ポイントスrc*<br/>
ソース`POINT`四角形の左上隅を示す構造体。

*ポイントマスク*<br/>
マスク`POINT`ビットマップの左上隅を示す構造体。

*ポイントデスト*<br/>
移動先の`POINT`四角形の左上隅を論理単位で識別する構造体への参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

この方法は、Windows NT バージョン 4.0 以降にのみ適用されます。

## <a name="cimageoperator-hbitmap"></a><a name="operator_hbitmap"></a>を使用します。

この演算子を使用して、オブジェクトの添付された Windows `CImage` GDI ハンドルを取得します。 この演算子はキャスト演算子で、HBITMAP オブジェクトの直接使用をサポートします。

## <a name="cimageplgblt"></a><a name="plgblt"></a>CImage::PlgBlt

転送元のデバイス コンテキスト内の四角形から、ターゲット デバイス コンテキストの並列表示へのビット ブロック転送を実行します。

```
BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    HBITMAP hbmMask = NULL) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    HBITMAP hbmMask = NULL,
    int xMask = 0,
    int yMask = 0) const throw();

BOOL PlgBlt(
    HDC hDestDC,
    const POINT* pPoints,
    const RECT& rectSrc,
    HBITMAP hbmMask = NULL,
    const POINT& pointMask = CPoint(0, 0)) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ターゲット デバイス コンテキストへのハンドル。

*ポイント*<br/>
変換先平行四辺形の 3 つのコーナーを識別する論理空間内の 3 つのポイントの配列へのポインター。 ソース四角形の左上隅は、この配列の最初の点、この配列の 2 番目のポイントに右上隅、3 番目の点に左下隅にマップされます。 ソース四角形の右下隅は、平行四辺形の 4 番目の暗黙的なポイントにマップされます。

*hbmマスク*<br/>
ソース四角形の色をマスクするために使用されるオプションのモノクロ ビットマップへのハンドル。

*xSrc*<br/>
ソース四角形の左上隅の x 座標 (論理単位)。

*ySrc*<br/>
ソース四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
ソース四角形の幅 (論理単位)。

*NSrcHeight*<br/>
ソース四角形の高さ (論理単位)。

*xマスク*<br/>
モノクロ ビットマップの左上隅の x 座標。

*yマスク*<br/>
モノクロ ビットマップの左上隅の y 座標。

*レクトスrc*<br/>
ソース四角形の座標を指定する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*ポイントマスク*<br/>
マスク ビットマップの左上隅を示す[POINT](/windows/win32/api/windef/ns-windef-point)構造体。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

*hbmMask*が有効なモノクロ ビットマップを識別`PlgBit`する場合は、このビットマップを使用して、ソースの四角形からカラー データのビットをマスクします。

この方法は、Windows NT バージョン 4.0 以降にのみ適用されます。 詳細については、Windows SDK の[PlgBlt](/windows/win32/api/wingdi/nf-wingdi-plgblt)を参照してください。

## <a name="cimagereleasedc"></a><a name="releasedc"></a>CImage::リリースDC

デバイス コンテキストを解放します。

```cpp
void ReleaseDC() const throw();
```

### <a name="remarks"></a>解説

デバイス コンテキストに選択できるビットマップは一度に 1 つだけなので、呼`ReleaseDC`び出しごとに[GetDC](#getdc)を呼び出す必要があります。

## <a name="cimagereleasegdiplus"></a><a name="releasegdiplus"></a>イメージ::リリースGDIプラス

GDI+ によって使用されるリソースを解放します。

```cpp
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>解説

このメソッドは、グローバル`CImage`オブジェクトによって割り当てられたリソースを解放するために呼び出す必要があります。 [「CImage::CImage」](#cimage)を参照してください。

## <a name="cimagesave"></a><a name="save"></a>CImage::保存

イメージをディスク上の指定されたストリームまたはファイルに保存します。

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
ファイル イメージ データを含む COM IStream オブジェクトへのポインター。

*ファイル名*<br/>
イメージのファイル名へのポインター。

*ファイルの種類*<br/>
イメージを保存するファイルの種類。 以下のいずれかを指定できます。

- `ImageFormatBMP`非圧縮ビットマップ イメージ。

- `ImageFormatPNG`ポータブル ネットワーク グラフィック (PNG) 圧縮イメージ。

- `ImageFormatJPEG`JPEG 圧縮イメージ。

- `ImageFormatGIF`GIF 圧縮イメージ。

> [!NOTE]
> 定数の完全な一覧については、Windows SDK の **「イメージ ファイル形式の定数**」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT。

### <a name="remarks"></a>解説

指定した名前と型を使用してイメージを保存します。 *guidFileType*パラメーターが含まれていない場合は、ファイル名のファイル拡張子を使用してイメージ形式を決定します。 拡張子が指定されていない場合、イメージは BMP 形式で保存されます。

## <a name="cimagesetcolortable"></a><a name="setcolortable"></a>を設定します。

DIB セクションのパレット内のエントリの範囲に対して、赤、緑、青 (RGB) の色の値を設定します。

```cpp
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>パラメーター

*最初の色*<br/>
設定する最初のエントリのカラー テーブル インデックス。

*nカラー*<br/>
設定するカラー テーブル エントリの数。

*プルグカラー*<br/>
カラー テーブルエントリを設定する[RGBQUAD](/windows/win32/api/wingdi/ns-wingdi-rgbquad)構造体の配列へのポインター。

### <a name="remarks"></a>解説

このメソッドは、DIB セクション ビットマップのみをサポートします。

## <a name="cimagesetpixel"></a><a name="setpixel"></a>イメージ::セットピクセル

ビットマップ内の指定された位置にあるピクセルの色を設定します。

```cpp
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
設定するピクセルの水平位置。

*Y*<br/>
設定するピクセルの垂直方向の位置。

*色*<br/>
ピクセルを設定する色。

### <a name="remarks"></a>解説

ピクセル座標が選択したクリップ領域の外側にある場合、このメソッドは失敗します。

## <a name="cimagesetpixelindexed"></a><a name="setpixelindexed"></a>イメージ::セットピクセルインデックス

カラー パレットの*iIndex*にある色にピクセルカラーを設定します。

```cpp
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
設定するピクセルの水平位置。

*Y*<br/>
設定するピクセルの垂直方向の位置。

*をクリックします。*<br/>
カラー パレット内の色のインデックス。

## <a name="cimagesetpixelrgb"></a><a name="setpixelrgb"></a>を設定します。

*x*および*y*で指定された位置のピクセルを *、r*、 *g*、および*b*で示される色に赤、緑、青 (RGB) のイメージで設定します。

```cpp
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
設定するピクセルの水平位置。

*Y*<br/>
設定するピクセルの垂直方向の位置。

*r*<br/>
赤の色の強度。

*G*<br/>
緑の色の強度。

*B*<br/>
青の色の強度。

### <a name="remarks"></a>解説

赤、緑、青の各パラメーターは、0 から 255 の間の数値で表されます。 3 つのパラメータすべてを 0 に設定すると、結果の色が黒になります。 3 つのパラメータすべてを 255 に設定すると、結果の色は白になります。

## <a name="cimagesettransparentcolor"></a><a name="settransparentcolor"></a>カラーカラーを設定します。

指定したインデックス位置の色を透明として設定します。

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>パラメーター

*透明な色*<br/>
透明に設定する色のインデックスを、カラー パレットで指定します。 1 の場合、透明に設定された色はありません。

### <a name="return-value"></a>戻り値

以前に透明に設定された色のインデックス。

## <a name="cimagestretchblt"></a><a name="stretchblt"></a>CImage::ストレッチブラット

ソース デバイス コンテキストからこの現在のデバイス コンテキストにビットマップをコピーします。

```
BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    DWORD dwROP = SRCCOPY) const throw();

BOOL StretchBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    DWORD dwROP = SRCCOPY) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ターゲット デバイス コンテキストへのハンドル。

*xDest*<br/>
移動先の四角形の左上隅の x 座標 (論理単位)。

*イデスト*<br/>
移動先の四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
コピー先の四角形の幅 (論理単位)。

*最も高い*<br/>
コピー先の四角形の高さ (論理単位)。

*Dwrop*<br/>
実行するラスター操作。 ラスターオペレーション コードは、ソース、出力先、および (現在選択されているブラシで定義されている) パターンのビットを組み合わせて、目的地を形成する方法を正確に定義します。 その他のラスター オペレーション コードとその説明については、Windows SDK の[BitBlt](/windows/win32/api/wingdi/nf-wingdi-bitblt)を参照してください。

*レクトデスト*<br/>
宛先を識別する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*xSrc*<br/>
ソース四角形の左上隅の x 座標 (論理単位)。

*ySrc*<br/>
ソース四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
ソース四角形の幅 (論理単位)。

*NSrcHeight*<br/>
ソース四角形の高さ (論理単位)。

*レクトスrc*<br/>
ソースを識別する`RECT`構造体への参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の「ストレッチブラット](/windows/win32/api/wingdi/nf-wingdi-stretchblt)」を参照してください。

## <a name="cimagetransparentblt"></a><a name="transparentblt"></a>CImage::トランスペアレントブレット

ソース デバイス コンテキストからこの現在のデバイス コンテキストにビットマップをコピーします。

```
BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    int xDest,
    int yDest,
    int nDestWidth,
    int nDestHeight,
    int xSrc,
    int ySrc,
    int nSrcWidth,
    int nSrcHeight,
    UINT crTransparent = CLR_INVALID) const throw();

BOOL TransparentBlt(
    HDC hDestDC,
    const RECT& rectDest,
    const RECT& rectSrc,
    UINT crTransparent = CLR_INVALID) const throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ターゲット デバイス コンテキストへのハンドル。

*xDest*<br/>
移動先の四角形の左上隅の x 座標 (論理単位)。

*イデスト*<br/>
移動先の四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
コピー先の四角形の幅 (論理単位)。

*最も高い*<br/>
コピー先の四角形の高さ (論理単位)。

*透明*<br/>
透明として扱うソース ビットマップの色。 既定では、CLR_INVALID、現在イメージの透明色として設定されている色を使用する必要があることを示します。

*レクトデスト*<br/>
宛先を識別する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*xSrc*<br/>
ソース四角形の左上隅の x 座標 (論理単位)。

*ySrc*<br/>
ソース四角形の左上隅の y 座標 (論理単位)。

*幅*<br/>
ソース四角形の幅 (論理単位)。

*NSrcHeight*<br/>
ソース四角形の高さ (論理単位)。

*レクトスrc*<br/>
ソースを識別する`RECT`構造体への参照。

### <a name="return-value"></a>戻り値

TRUE が成功した場合は FALSE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

`TransparentBlt`は、4 ビット/ピクセルおよび 8 ビット/ピクセルのソース ビットマップでサポートされています。 [CImage::AlphaBlend](#alphablend)を使用して、透過性のあるピクセルあたり 32 ビットのビットマップを指定します。

### <a name="example"></a>例

```cpp
// Performs a transparent blit from the source image to the destination
// image using the images' current transparency settings
BOOL TransparentBlt(CImage* pSrcImage, CImage* pDstImage,
       int xDest, int yDest, int nDestWidth, int nDestHeight)
{
    HDC hDstDC = NULL;
    BOOL bResult;

    if(pSrcImage == NULL || pDstImage == NULL)
    {
        // Invalid parameter
        return FALSE;
    }

    // Obtain a DC to the destination image
    hDstDC = pDstImage->GetDC();
    // Perform the blit
    bResult = pSrcImage->TransparentBlt(hDstDC, xDest, yDest, nDestWidth, nDestHeight);

    // Release the destination DC
    pDstImage->ReleaseDC();

    return bResult;
}
```

## <a name="see-also"></a>関連項目

[MMXSwarm サンプル](../../overview/visual-cpp-samples.md)<br/>
[シンプルイメージのサンプル](../../overview/visual-cpp-samples.md)<br/>
[デバイスに依存しないビットマップ](/windows/win32/gdi/device-independent-bitmaps)<br/>
[セクションを作成します。](/windows/win32/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)<br/>
[デバイスに依存しないビットマップ](/windows/win32/gdi/device-independent-bitmaps)<br/>
[セクションを作成します。](/windows/win32/api/wingdi/nf-wingdi-createdibsection)
