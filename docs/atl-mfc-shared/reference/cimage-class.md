---
title: CImage クラス
ms.date: 02/01/2018
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
ms.openlocfilehash: a62919ebd6b2aba54aa8003743b0006571cdedf4
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419671"
---
# <a name="cimage-class"></a>CImage クラス

`CImage` 読み込み、JPEG、GIF、BMP、およびポータブル ネットワーク グラフィックス (PNG) 形式で画像を保存する機能など、ビットマップの拡張サポートを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CImage
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CImage::CImage](#cimage)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CImage::AlphaBlend](#alphablend)|透明または半透明ピクセルのビットマップを表示します。|
|[CImage::Attach](#attach)|HBITMAP へのアタッチ、`CImage`オブジェクト。 非 DIB セクション ビットマップや DIB セクションのビットマップのいずれかで使用できます。|
|[CImage::BitBlt](#bitblt)|現在のデバイス コンテキストを元のデバイス コンテキストからビットマップをコピーします。|
|[CImage::Create](#create)|DIB セクション ビットマップを作成し、構築済みにアタッチします。`CImage`オブジェクト。|
|[CImage::CreateEx](#createex)|追加のパラメーター) を持つ DIB セクション ビットマップを作成し、構築済みにアタッチします。`CImage`オブジェクト。|
|[CImage::Destroy](#destroy)|ビットマップからのデタッチ、`CImage`オブジェクトし、ビットマップを破棄します。|
|[CImage::Detach](#detach)|ビットマップからのデタッチ、`CImage`オブジェクト。|
|[CImage::Draw](#draw)|先の四角形に、元の四角形からビットマップをコピーします。 `Draw` 拡大または必要に応じて、移行先の四角形の大きさに合わせてビットマップを圧縮し、アルファ ブレンドおよび透明な色を処理します。|
|[CImage::GetBits](#getbits)|ビットマップの実際のピクセル値へのポインターを取得します。|
|[CImage::GetBPP](#getbpp)|1 ピクセルあたりのビットを取得します。|
|[CImage::GetColorTable](#getcolortable)|カラー テーブル内のエントリの範囲から赤、緑、青 (RGB) の色の値を取得します。|
|[CImage::GetDC](#getdc)|先の現在のビットマップが選択されているデバイス コンテキストを取得します。|
|[CImage::GetExporterFilterString](#getexporterfilterstring)|使用可能なイメージ形式とその説明を検索します。|
|[CImage::GetHeight](#getheight)|現在のピクセル単位でイメージの高さを取得します。|
|[CImage::GetImporterFilterString](#getimporterfilterstring)|使用可能なイメージ形式とその説明を検索します。|
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|カラー テーブル内のエントリの最大数を取得します。|
|[CImage::GetPitch](#getpitch)|現在のイメージには、バイトのピッチを取得します。|
|[CImage::GetPixel](#getpixel)|指定されたピクセルの色を取得*x*と*y*します。|
|[CImage::GetPixelAddress](#getpixeladdress)|特定のピクセルのアドレスを取得します。|
|[CImage::GetTransparentColor](#gettransparentcolor)|透明色のカラー テーブル内の位置を取得します。|
|[CImage::GetWidth](#getwidth)|現在のピクセル単位でイメージの幅を取得します。|
|[CImage::IsDIBSection](#isdibsection)|アタッチされているビットマップが DIB セクションであるかどうかを判断します。|
|[CImage::IsIndexed](#isindexed)|インデックス付きのパレットに、ビットマップの色がマップされていることを示します。|
|[CImage::IsNull](#isnull)|ソース ビットマップが現在読み込まれているかどうかを示します。|
|[CImage::IsTransparencySupported](#istransparencysupported)|アプリケーションが透明なビットマップをサポートしているかどうかを示します。|
|[CImage::Load](#load)|指定したファイルからイメージを読み込みます。|
|[CImage::LoadFromResource](#loadfromresource)|指定されたリソースからイメージを読み込みます。|
|[CImage::MaskBlt](#maskblt)|指定したマスクとラスター オペレーションを使用してソースと変換先のビットマップのカラー データを結合します。|
|[CImage::PlgBlt](#plgblt)|コピー先のデバイス コンテキストでの平行四辺形には、ソース デバイス コンテキスト内の四角形からビット ブロック転送を実行します。|
|[CImage::ReleaseDC](#releasedc)|取得したデバイス コンテキストを解放[CImage::GetDC](#getdc)します。|
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI + で使用されるリソースを解放します。 グローバルで作成した無料のリソースを呼び出す必要がある`CImage`オブジェクト。|
|[CImage::Save](#save)|指定した型と、イメージを保存します。 `Save` イメージのオプションを指定することはできません。|
|[CImage::SetColorTable](#setcolortable)|赤、緑、青の RGB の設定) DIB セクションのカラー テーブル内のエントリの範囲内の値の色します。|
|[CImage::SetPixel](#setpixel)|指定した色の指定した座標にあるピクセルに設定します。|
|[CImage::SetPixelIndexed](#setpixelindexed)|色パレットの指定したインデックス位置に指定した座標のピクセルを設定します。|
|[CImage::SetPixelRGB](#setpixelrgb)|指定された赤、緑、青 (RGB) の値を指定した座標のピクセルを設定します。|
|[CImage::SetTransparentColor](#settransparentcolor)|透明色として処理する色のインデックスを設定します。 パレットの色が 1 つだけを透明になることができます。|
|[CImage::StretchBlt](#stretchblt)|元の四角形から先の四角形を拡大または必要な場合は、先の四角形の寸法に合わせてビットマップを縮小にビットマップをコピーします。|
|[CImage::TransparentBlt](#transparentblt)|元のデバイス コンテキストからビットマップを透過色を現在のデバイス コンテキストにコピーします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CImage::operator HBITMAP](#operator_hbitmap)|アタッチされている Windows ハンドルを返します、`CImage`オブジェクト。|

## <a name="remarks"></a>Remarks

`CImage` いずれかのデバイスに依存しないビットマップ (DIB) セクションにあるか。 ビットマップを受け取るただし、使用することができます[作成](#create)または[CImage::Load](#load) DIB セクションのみを使用します。 非 DIB セクション ビットマップをアタッチすることができます、`CImage`オブジェクトを使用して[アタッチ](#attach)、次を使用することはできませんが、`CImage`メソッドで、DIB セクション ビットマップのみをサポートします。

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

添付のビットマップが DIB セクションを確認するには、呼び出す[IsDibSection](#isdibsection)します。

> [!NOTE]
> Visual Studio .NET 2003 でこのクラスは、数のカウントを保持`CImage`オブジェクトを作成します。 カウントが 0 の場合、関数に移動するたびに`GdiplusShutdown`は GDI + で使用されるリソースを解放する自動的に呼び出されます。 これにより、 `CImage` Dll によって直接的または間接的に作成されるオブジェクトが正しく破棄は常に、`GdiplusShutdown`からは呼び出されません`DllMain`します。

> [!NOTE]
> グローバルを使用して`CImage`DLL 内のオブジェクトはお勧めしません。 グローバルを使用する必要がある場合`CImage`呼び出し、DLL 内のオブジェクト[CImage::ReleaseGDIPlus](#releasegdiplus) GDI + で使用されるリソースを明示的に解放します。

`CImage` 新しい選択できない[CDC](../../mfc/reference/cdc-class.md)します。 `CImage` イメージの独自の HDC を作成します。 HBITMAP を 1 つ HDC を選択するには、一度に、ため、HBITMAP に関連付けられている、`CImage`別 HDC を選択することはできません。 HDC をな CDC の場合は、取得、`CImage`し [CDC::FromHandle] を付けます (../../mfc/reference/cdc-class.md#cdc__fromhandle します。

## <a name="example"></a>例

```cpp
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```

使用すると`CImage`MFC プロジェクトで、プロジェクトのメンバー関数へのポインターの期待に注意してください、 [CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクト。 使用する場合`CImage`のような関数は、のような[CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)を使用して、 [CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle)、渡す、 `CImage` HBITMAP、して、返された`CBitmap*`します。

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

を通じて`CImage`、DIB セクションの実際のビットへのアクセスがあります。 使用することができます、 `CImage` Win32 HBITMAP または DIB のセクションを使用していたオブジェクトの任意の場所。

使用することができます`CImage`MFC または ATL のいずれかから

> [!NOTE]
> 使用してプロジェクトを作成すると`CImage`を定義する必要があります`CString`インクルードする前に`atlimage.h`します。 プロジェクトでは、MFC を使用せずに ATL を使用する場合は、`atlstr.h`インクルードする前に`atlimage.h`します。 プロジェクトでは、MFC (または、これは MFC サポートを ATL プロジェクトであるかどうか) を使用する場合は、`afxstr.h`インクルードする前に`atlimage.h`します。<br/>
> <br/>
> 同様に、含める必要がある`atlimage.h`インクルードする前に`atlimpl.cpp`します。 簡単にこれを実現するには含める`atlimage.h`で、`stdafx.h`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlimage.h

##  <a name="alphablend"></a>  CImage::AlphaBlend

透明または半透明ピクセルのビットマップを表示します。

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

*hDestDC*<br/>
コピー先のデバイス コンテキストへのハンドルします。

*xDest*<br/>
X 座標、先の四角形の左上隅の論理単位です。

*yDest*<br/>
Y 座標、先の四角形の左上隅の論理単位です。

*bSrcAlpha*<br/>
元のビットマップ全体で使用するアルファ透明度値。 既定値 0 xff (255) には、イメージが不透明であると、ピクセル単位のアルファ値のみを使用することが想定しています。

*bBlendOp*<br/>
アルファ ブレンドのソースとコピー先ビットマップ、グローバルのアルファ値全体の元のビットマップと元のビットマップの書式情報に適用する関数。 ソースと宛先の blend 関数は、ビットマップに制限されています。

*pointDest*<br/>
参照を[ポイント](/previous-versions/dd162805\(v=vs.85\))論理単位で、先の四角形の左上隅を識別する構造体。

*nDestWidth*<br/>
論理ユニットは、先の四角形の幅。

*nDestHeight*<br/>
論理ユニットは、先の四角形の高さ。

*xSrc*<br/>
元の四角形の左上隅の論理 x 座標。

*ySrc*<br/>
元の四角形の左上隅の論理 y 座標。

*nSrcWidth*<br/>
論理ユニットは、元の四角形の幅。

*nSrcHeight*<br/>
論理ユニットは、元の四角形の高さ。

*rectDest*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))構造体、変換先を識別します。

*rectSrc*<br/>
参照を`RECT`構造体、ソースを特定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

アルファ ブレンド ビットマップでは、色は、ピクセル単位で描画をサポートします。

ときに*bBlendOp*設定されているソース ビットマップをコピー先のビットマップ ソース ピクセルのアルファ値に基づいてその上にビットマップの既定値にします。

##  <a name="attach"></a>  CImage::Attach

アタッチ*hBitmap*を`CImage`オブジェクト。

```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```

### <a name="parameters"></a>パラメーター

*hBitmap*<br/>
HBITMAP ハンドル。

*eOrientation*<br/>
ビットマップの向きを指定します。 次のいずれかの値を指定します。

- DIBOR_DEFAULT ビットマップの向きは、オペレーティング システムによって決定されます。

- DIBOR_BOTTOMUP ビットマップの行は逆の順序で。 これにより、 [CImage::GetBits](#getbits)ビットマップ バッファーの末尾付近のポインターを返すと[CImage::GetPitch](#getpitch)を負の数を返します。

- DIBOR_TOPDOWN ビットマップの行は、上から下へのです。 これにより、 [CImage::GetBits](#getbits)ビットマップ バッファーの最初のバイトへのポインターを返すと[CImage::GetPitch](#getpitch)正の数を取得します。

### <a name="remarks"></a>Remarks

ビットマップには、非 DIB セクション ビットマップや DIB セクション ビットマップのいずれかを指定できます。 参照してください[IsDIBSection](#isdibsection) DIB でのみ使用できるメソッドの一覧については、ビットマップをセクションします。

##  <a name="bitblt"></a>  CImage::BitBlt

現在のデバイス コンテキストを元のデバイス コンテキストからビットマップをコピーします。

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

*hDestDC*<br/>
HDC 先。

*xDest*<br/>
先の四角形の左上隅の論理 x 座標。

*yDest*<br/>
先の四角形の左上隅の論理 y 座標。

*dwROP*<br/>
実行するラスター操作。 ラスター オペレーション コードは、変換先を形成するソース、変換先、およびパターンのビット (現在選択されているブラシによって定義される) とを組み合わせる方法を定義します。 参照してください[BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt)他ラスター オペレーション コードとその説明の一覧については、Windows sdk。

*pointDest*<br/>
A[ポイント](/previous-versions/dd162805\(v=vs.85\))先の四角形の左上隅を示す構造体。

*nDestWidth*<br/>
論理ユニットは、先の四角形の幅。

*nDestHeight*<br/>
論理ユニットは、先の四角形の高さ。

*xSrc*<br/>
元の四角形の左上隅の論理 x 座標。

*ySrc*<br/>
元の四角形の左上隅の論理 y 座標。

*rectDest*<br/>
A [RECT](/previous-versions/dd162897\(v=vs.85\))先の四角形を示す構造体。

*pointSrc*<br/>
A`POINT`ソース四角形の左上隅を示す構造体。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt) Windows SDK に含まれています。

##  <a name="cimage"></a>  CImage::CImage

`CImage` オブジェクトを構築します。

```
CImage() throw();
```

### <a name="remarks"></a>Remarks

オブジェクトが構築されると、呼び出す[作成](#create)、[ロード](#load)、 [LoadFromResource](#loadfromresource)、または[アタッチ](#attach)ビットマップをオブジェクトにアタッチします。

**注**Visual Studio では、このクラスは、数のカウントを保持`CImage`オブジェクトを作成します。 カウントが 0 の場合、関数に移動するたびに`GdiplusShutdown`は GDI + で使用されるリソースを解放する自動的に呼び出されます。 これにより、 `CImage` Dll によって直接的または間接的に作成されるオブジェクトが正しく破棄は常に、 `GdiplusShutdown` DllMain からは呼び出されません。

グローバルを使用して`CImage`DLL 内のオブジェクトはお勧めしません。 グローバルを使用する必要がある場合`CImage`呼び出し、DLL 内のオブジェクト[CImage::ReleaseGDIPlus](#releasegdiplus) GDI + で使用されるリソースを明示的に解放します。

##  <a name="create"></a>  CImage::Create

作成、`CImage`ビットマップし、構築済みにアタッチ`CImage`オブジェクト。

```
BOOL Create(
    int nWidth,
    int nHeight,
    int nBPP,
    DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
幅、 `CImage` (ピクセル単位) のビットマップ。

*nHeight*<br/>
高さ、 `CImage` (ピクセル単位) のビットマップ。 場合*パラメーター nHeight*が正、ビットマップはボトムアップ DIB と原点は左下隅。 場合*パラメーター nHeight*が負の場合、ビットマップは、上から下へ DIB と、原点は左上隅。

*nBPP*<br/>
ビットマップのピクセルあたりのビット数。 通常、4、8、16、24、または 32。 モノクロ ビットマップまたはマスクの 1 にすることができます。

*dwFlags*<br/>
Bitmap オブジェクトがアルファ チャネルを持つかどうかを指定します。 次の値の 0 個以上の組み合わせになります。

- *createAlphaChannel*場合にのみ使用できます*nBPP* 32、および*eCompression*値です。 指定した場合 (英数字以外の 32 ビット イメージで使用されていない) の各ピクセルの第 4 バイトに格納されている、各ピクセルのアルファ (透明度) 値を作成されたイメージがあります。 呼び出すときに、このアルファ チャネルは自動的に使用[CImage::AlphaBlend](#alphablend)します。

> [!NOTE]
> 呼び出しで[:draw](#draw)、アルファ チャネルを持つイメージが自動的にアルファ先にブレンドします。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="createex"></a>  CImage::CreateEx

作成、`CImage`ビットマップし、構築済みにアタッチ`CImage`オブジェクト。

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

*nWidth*<br/>
幅、 `CImage` (ピクセル単位) のビットマップ。

*nHeight*<br/>
高さ、 `CImage` (ピクセル単位) のビットマップ。 場合*パラメーター nHeight*が正、ビットマップはボトムアップ DIB と原点は左下隅。 場合*パラメーター nHeight*が負の場合、ビットマップは、上から下へ DIB と、原点は左上隅。

*nBPP*<br/>
ビットマップのピクセルあたりのビット数。 通常、4、8、16、24、または 32。 モノクロ ビットマップまたはマスクの 1 にすることができます。

*eCompression*<br/>
(上から下への Dib を圧縮することはできません)、圧縮されたボトムアップ ビットマップの圧縮の種類を指定します。 次のいずれかの値になります。

- 値の形式は、圧縮ではありません。 呼び出すときに、この値を指定する`CImage::CreateEx`呼び出しと同じですが`CImage::Create`します。

- BI_BITFIELDS 形式が圧縮されていないと、各ピクセルの赤、緑、および青のコンポーネントをそれぞれ指定する 3 つの DWORD 色マスクのカラー テーブルで構成されます。 これは、16、32 bpp のビットマップを使用すると有効です。

*pdwBitfields*<br/>
場合にのみ使用*eCompression*設定に BI_BITFIELDS、それ以外の場合があります NULL。 各ピクセルのビットが、色の赤、緑、および青のコンポーネントをそれぞれ使用されますを指定する、3 つの DWORD ビットマスクの配列へのポインター。 ビット フィールドの制限については、次を参照してください。 [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376) Windows SDK に含まれています。

*dwFlags*<br/>
Bitmap オブジェクトがアルファ チャネルを持つかどうかを指定します。 次の値の 0 個以上の組み合わせになります。

- *createAlphaChannel*場合にのみ使用できます*nBPP* 32、および*eCompression*値です。 指定した場合 (英数字以外の 32 ビット イメージで使用されていない) の各ピクセルの第 4 バイトに格納されている、各ピクセルのアルファ (透明度) 値を作成されたイメージがあります。 呼び出すときに、このアルファ チャネルは自動的に使用[CImage::AlphaBlend](#alphablend)します。

   > [!NOTE]
   > 呼び出しで[:draw](#draw)、アルファ チャネルを持つイメージが自動的にアルファ先にブレンドします。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。 それ以外の場合は FALSE です。

### <a name="example"></a>例

次の例では、ピクセルごとに 16 ビットを使用して、100 x 100 ピクセルのビットマップを作成します。 指定された 16 ビットのピクセルでは、ビット 0 ~ 3 は赤のコンポーネントをエンコード、4 ~ 7 ビット エンコード緑、および 8 ~ 11 ビットは青をエンコードします。 残りの 4 ビットは、使用されません。

```cpp
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```

##  <a name="destroy"></a>  CImage::Destroy

ビットマップからのデタッチ、`CImage`オブジェクトし、ビットマップを破棄します。

```
void Destroy() throw();
```

##  <a name="detach"></a>  CImage::Detach

ビットマップからのデタッチ、`CImage`オブジェクト。

```
HBITMAP Detach() throw();
```

### <a name="return-value"></a>戻り値

デタッチするには、ビットマップを識別するハンドルまたはビットマップが添付されていない場合は NULL です。

##  <a name="draw"></a>  :Draw

現在のデバイス コンテキストを元のデバイス コンテキストからビットマップをコピーします。

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

*hDestDC*<br/>
コピー先のデバイス コンテキストへのハンドル。

*xDest*<br/>
X 座標、先の四角形の左上隅の論理単位です。

*yDest*<br/>
Y 座標、先の四角形の左上隅の論理単位です。

*nDestWidth*<br/>
論理ユニットは、先の四角形の幅。

*nDestHeight*<br/>
論理ユニットは、先の四角形の高さ。

*xSrc*<br/>
X 座標、元の四角形の左上隅の論理単位で。

*ySrc*<br/>
Y 座標、元の四角形の左上隅の論理単位で。

*nSrcWidth*<br/>
論理ユニットは、元の四角形の幅。

*nSrcHeight*<br/>
論理ユニットは、元の四角形の高さ。

*rectDest*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))構造体、変換先を識別します。

*rectSrc*<br/>
参照を`RECT`構造体、ソースを特定します。

*pointDest*<br/>
参照を[ポイント](/previous-versions/dd162805\(v=vs.85\))論理単位で、先の四角形の左上隅を識別する構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

`Draw` 同じ操作を実行します。 [StretchBlt](#stretchblt)透明色またはアルファ チャネル イメージが含まれていない場合、します。 その場合は、`Draw`いずれかと同じ操作を実行します。 [TransparentBlt](#transparentblt)または[AlphaBlend](#alphablend)必要に応じて。

バージョンの`Draw`元の四角形を指定をしない場合、ソース イメージ全体が既定値。 バージョンの`Draw`先の四角形のサイズを指定するは、ソース イメージのサイズは、既定または縮小が行われます。

##  <a name="getbits"></a>  CImage::GetBits

ビットマップのピクセルの実際のビット値へのポインターを取得します。

```
void* GetBits() throw();
```

### <a name="return-value"></a>戻り値

ビットマップ バッファーへのポインター。 ビットマップがボトムアップ DIB の場合は、バッファーの末尾に近く、ポインター。 ビットマップが上から下へ DIB の場合は、ポインターは、バッファーの最初のバイトを指します。

### <a name="remarks"></a>Remarks

によって返される値と共に、このポインターを使用して[GetPitch](#getpitch)を検索し、個々 のピクセルにイメージを変更できます。

> [!NOTE]
> このメソッドは、DIB セクション ビットマップのみをサポートしています。ピクセルにアクセスする、その結果、 `CImage` DIB セクションのピクセルのと同様のオブジェクトします。 返されるポインターは、ピクセル位置 (0, 0) を指します。

##  <a name="getbpp"></a>  CImage::GetBPP

ピクセルあたりのビット値を取得します。

```
int GetBPP() const throw();
```

### <a name="return-value"></a>戻り値

1 ピクセルあたりのビット数。

### <a name="remarks"></a>Remarks

この値は、各ピクセルを定義するビットの数と、ビットマップの色の最大数を決定します。

1、4、8、16、24、または 32 ビット/ピクセルは通常は。 参照してください、`biBitCount`のメンバー [BITMAPINFOHEADER](https://msdn.microsoft.com/library/windows/desktop/dd183376)この値の詳細については、Windows SDK に含まれています。

##  <a name="getcolortable"></a>  CImage::GetColorTable

DIB セクションのパレット内のエントリの範囲から赤、緑、青 (RGB) の色の値を取得します。

```
void GetColorTable(
    UINT iFirstColor,
    UINT nColors,
    RGBQUAD* prgbColors) const throw();
```

### <a name="parameters"></a>パラメーター

*iFirstColor*<br/>
取得する最初のエントリのカラー テーブルのインデックス。

*nColors*<br/>
取得するカラー テーブル エントリの数。

*prgbColors*<br/>
配列へのポインター [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad)構造体の色を取得するテーブルのエントリ。

##  <a name="getdc"></a>  CImage::GetDC

現在選択されているイメージを保持しているデバイス コンテキストを取得します。

```
HDC GetDC() const throw();
```

### <a name="return-value"></a>戻り値

デバイス コンテキストを識別するハンドル。

### <a name="remarks"></a>Remarks

呼び出しごとに`GetDC`、後続の呼び出しが必要[ReleaseDC](#releasedc)します。

##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString

イメージを保存するためには、使用可能なイメージ形式を検索します。

```
static HRESULT GetExporterFilterString(
    CSimpleString& strExporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultSave,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>パラメーター

*strExporters*<br/>
`CSimpleString` オブジェクトへの参照。 参照してください**解説**詳細についてはします。

*aguidFileTypes*<br/>
文字列内のファイルの種類のいずれかに対応する各要素に、Guid の配列。 例では、 *pszAllFilesDescription*以下、 *aguidFileTypes*[0] GUID_ は、残りの配列値は、現在のオペレーティング システムでサポートされているイメージ ファイル形式。

> [!NOTE]
> 定数の完全な一覧を参照してください。**イメージ ファイル形式の定数**Windows SDK に含まれています。

*pszAllFilesDescription*<br/>
このパラメーターが NULL でない場合、フィルター文字列は、一覧の先頭に 1 つの追加フィルターがあります。 このフィルターの現在の値になります*pszAllFilesDescription*説明の一覧で、その他のエクスポーターでサポートされている任意の拡張機能のファイルを受け取るとします。

例:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
一覧から除外するファイルの種類を指定するビット フラグのセット。 使用できるフラグは次のとおりです。

- `excludeGIF` 0x01 除外 GIF ファイルを = です。

- `excludeBMP` 0x02 (Windows ビットマップ) を除く BMP ファイルを = です。

- `excludeEMF` 0x04 除外 EMF (拡張メタファイル) ファイルを = です。

- `excludeWMF` 0x08 除外 WMF (Windows メタファイル) ファイルを = です。

- `excludeJPEG` 0x10 除外 JPEG ファイルを = です。

- `excludePNG` 0x20 除外 PNG ファイルを = です。

- `excludeTIFF` 除外の TIFF ファイルの 0x40 を = です。

- `excludeIcon` 0x80 除外 ICO (Windows アイコン) ファイルを = です。

- `excludeOther` = 0x80000000 に記載されていないその他のファイルの種類を除外します。

- `excludeDefaultLoad` 負荷の種類は、既定で含まれるすべてのファイルの場合は 0 を =

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` これらのファイルは、保存、するため特別な要件があるため、既定で除外されます。

*chSeparator*<br/>
イメージ形式の間で使用する区切り記号。 参照してください**解説**詳細についてはします。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>Remarks

Mfc の結果の書式指定文字列を渡すことができます[CFileDialog](../../mfc/reference/cfiledialog-class.md)ファイル名を付けて保存 ダイアログ ボックスで使用可能なイメージ ファイルの拡張機能を公開するオブジェクトが書式設定します。

パラメーター *strExporter*形式します。

ファイルの description0&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;... .file 説明*n*&#124;\*.ext *n*&#124;&#124;

場所 '&#124;' で指定された区切り記号文字`chSeparator`します。 例:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

既定の区切り記号を使用して '&#124;' MFC にこの文字列を渡す場合`CFileDialog`オブジェクト。 一般的な名前を付けて保存 ダイアログ ボックスにこの文字列を渡す場合は、null の区切り記号 '\0' を使用します。

##  <a name="getheight"></a>  CImage::GetHeight

イメージのピクセルの高さを取得します。

```
int GetHeight() const throw();
```

### <a name="return-value"></a>戻り値

イメージのピクセル単位の高さ。

##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString

イメージを読み込むためには、使用可能なイメージ形式を検索します。

```
static HRESULT GetImporterFilterString(
    CSimpleString& strImporters,
    CSimpleArray<GUID>& aguidFileTypes,
    LPCTSTR pszAllFilesDescription = NULL,
    DWORD dwExclude = excludeDefaultLoad,
    TCHAR chSeparator = _T('|'));
```

### <a name="parameters"></a>パラメーター

*strImporters*<br/>
`CSimpleString` オブジェクトへの参照。 参照してください**解説**詳細についてはします。

*aguidFileTypes*<br/>
文字列内のファイルの種類のいずれかに対応する各要素に、Guid の配列。 例では、 *pszAllFilesDescription*以下、 *aguidFileTypes*[0] は残りの配列の値を持つ GUID_ は現在のオペレーティング システムでサポートされているイメージ ファイル形式。

> [!NOTE]
> 定数の完全な一覧を参照してください。**イメージ ファイル形式の定数**Windows SDK に含まれています。

*pszAllFilesDescription*<br/>
このパラメーターが NULL でない場合、フィルター文字列は、一覧の先頭に 1 つの追加フィルターがあります。 このフィルターの現在の値になります*pszAllFilesDescription*説明の一覧で、その他のエクスポーターでサポートされている任意の拡張機能のファイルを受け取るとします。

例:

```cpp
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes,
_T("All Image Files"));
```

*dwExclude*<br/>
一覧から除外するファイルの種類を指定するビット フラグのセット。 使用できるフラグは次のとおりです。

- `excludeGIF` 0x01 除外 GIF ファイルを = です。

- `excludeBMP` 0x02 (Windows ビットマップ) を除く BMP ファイルを = です。

- `excludeEMF` 0x04 除外 EMF (拡張メタファイル) ファイルを = です。

- `excludeWMF` 0x08 除外 WMF (Windows メタファイル) ファイルを = です。

- `excludeJPEG` 0x10 除外 JPEG ファイルを = です。

- `excludePNG` 0x20 除外 PNG ファイルを = です。

- `excludeTIFF` 除外の TIFF ファイルの 0x40 を = です。

- `excludeIcon` 0x80 除外 ICO (Windows アイコン) ファイルを = です。

- `excludeOther` = 0x80000000 に記載されていないその他のファイルの種類を除外します。

- `excludeDefaultLoad` 負荷の種類は、既定で含まれるすべてのファイルの場合は 0 を =

- `excludeDefaultSave` = `excludeIcon &#124; excludeEMF &#124; excludeWMF` これらのファイルは、保存、するため特別な要件があるため、既定で除外されます。

*chSeparator*<br/>
イメージ形式の間で使用する区切り記号。 参照してください**解説**詳細についてはします。

### <a name="remarks"></a>Remarks

Mfc の結果の書式指定文字列を渡すことができます[CFileDialog](../../mfc/reference/cfiledialog-class.md)に使用可能なイメージ ファイルの拡張機能を公開するオブジェクトの書式、**ファイルを開く** ダイアログ ボックス。

パラメーター *strImporter*形式します。

ファイルの description0&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;... .file 説明*n*&#124;\*.ext *n*&#124;&#124;

場所 '&#124;' で指定された区切り記号*chSeparator*します。 例:

`"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`

既定の区切り記号を使用して '&#124;' MFC にこの文字列を渡す場合`CFileDialog`オブジェクト。 Null の区切り記号 '\0' を使用して、一般的にこの文字列を渡す場合**ファイルを開く** ダイアログ ボックス。

##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries

カラー テーブル内のエントリの最大数を取得します。

```
int GetMaxColorTableEntries() const throw();
```

### <a name="return-value"></a>戻り値

カラー テーブル内のエントリの数。

### <a name="remarks"></a>Remarks

このメソッドは、DIB セクション ビットマップのみをサポートします。

##  <a name="getpitch"></a>  CImage::GetPitch

イメージのピッチを取得します。

```
int GetPitch() const throw();
```

### <a name="return-value"></a>戻り値

イメージのピッチです。 戻り値が負の場合、ビットマップはボトムアップ DIB と、原点は左下隅。 戻り値が正の場合、ビットマップは、上から下へ DIB と、原点は左上隅。

### <a name="remarks"></a>Remarks

ピッチは、1 つのビットマップの行の先頭を表す 2 つのメモリ アドレスとビットマップの次の行の先頭の間のバイト単位の距離です。 ピッチはバイト単位で計測され、ため、イメージのピッチで ピクセル形式を判断できます。 ピッチでは、ビットマップ用に予約の追加のメモリを含めることもできます。

使用`GetPitch`で[GetBits](#getbits)を個々 のピクセルのイメージを検索します。

> [!NOTE]
> このメソッドは、DIB セクション ビットマップのみをサポートします。

##  <a name="getpixel"></a>  CImage::GetPixel

指定された場所にあるピクセルの色を取得*x*と*y*します。

```
COLORREF GetPixel(int x, int y) const throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
ピクセルの x 座標。

*y*<br/>
ピクセルの y 座標。

### <a name="return-value"></a>戻り値

赤、緑、青 (RGB) の値はピクセル。 ピクセルが現在のクリップ領域の外部にある場合は、値を返します。

##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress

ピクセルの正確なアドレスを取得します。

```
void* GetPixelAddress(int x, int y) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
ピクセルの x 座標。

*y*<br/>
ピクセルの y 座標。

### <a name="remarks"></a>Remarks

アドレスは、ピクセルの座標、ビットマップとピクセルあたりのビットのピッチに従って決定されます。

1 ピクセルあたり 8 ビット未満のある形式の場合は、このメソッドは、ピクセルを含むバイトのアドレスを返します。 たとえば、イメージの形式に 1 ピクセルあたり 4 ビット`GetPixelAddress`返しますバイトごとにそれぞれ 2 ピクセルの最初のピクセルにして、バイトのアドレスを計算する必要があります。

> [!NOTE]
> このメソッドは、DIB セクション ビットマップのみをサポートします。

##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor

透明色カラー パレット内のインデックス位置を取得します。

```
LONG GetTransparentColor() const throw();
```

### <a name="return-value"></a>戻り値

透明色のインデックス。

##  <a name="getwidth"></a>  CImage::GetWidth

イメージのピクセルの幅を取得します。

```
int GetWidth() const throw();
```

### <a name="return-value"></a>戻り値

ピクセル単位で、ビットマップの幅。

##  <a name="isdibsection"></a>  CImage::IsDIBSection

アタッチされているビットマップが DIB セクションであるかどうかを判断します。

```
bool IsDIBSection() const throw();
```

### <a name="return-value"></a>戻り値

TRUE の場合、アタッチされているビットマップは DIB セクション。 それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

ビットマップが DIB セクションでない場合は、以下を使用することはできません`CImage`メソッドで、DIB セクション ビットマップのみをサポートします。

- [GetBits](#getbits)

- [GetColorTable](#getcolortable)

- [GetMaxColorTableEntries](#getmaxcolortableentries)

- [GetPitch](#getpitch)

- [GetPixelAddress](#getpixeladdress)

- [IsIndexed](#isindexed)

- [SetColorTable](#setcolortable)

##  <a name="isindexed"></a>  CImage::IsIndexed

ビットマップのピクセルを色パレットにマップするかどうかを判断します。

```
bool IsIndexed() const throw();
```

### <a name="return-value"></a>戻り値

インデックス付けする場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、ビットマップが 8 ビットである場合にのみ、TRUE を返します (256 色) 以下です。

> [!NOTE]
> このメソッドは、DIB セクション ビットマップのみをサポートします。

##  <a name="isnull"></a>  CImage::IsNull

ビットマップが現在読み込まれているかどうかを決定します。

```
bool IsNull() const throw();
```

### <a name="remarks"></a>Remarks

ビットマップが現在読み込まれていない; 場合このメソッドは TRUE を返しますそれ以外の場合は FALSE です。

##  <a name="istransparencysupported"></a>  CImage::IsTransparencySupported

アプリケーションが透明なビットマップをサポートしているかどうかを示します。

```
static BOOL IsTransparencySupported() throw();
```

### <a name="return-value"></a>戻り値

以外の場合は、現在のプラットフォームは、透明性をサポートします。 それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

戻り値は 0 以外の場合、および透明度がサポートされている場合の呼び出しを[AlphaBlend](#alphablend)、 [TransparentBlt](#transparentblt)、または[描画](#draw)透明色を処理します。

##  <a name="load"></a>  CImage::Load

イメージを読み込みます。

```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```

### <a name="parameters"></a>パラメーター

*pszFileName*<br/>
読み込むイメージ ファイルの名前を含む文字列へのポインター。

*pStream*<br/>
読み込むイメージ ファイルの名前を含むストリームへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>Remarks

指定されたイメージを読み込んで*pszFileName*または*pStream*します。

有効なイメージの種類は、BMP、GIF、JPEG、PNG、TIFF です。

##  <a name="loadfromresource"></a>  CImage::LoadFromResource

ビットマップ リソースからイメージを読み込みます。

```
void LoadFromResource(
    HINSTANCE hInstance,
    LPCTSTR pszResourceName) throw();

void LoadFromResource(
    HINSTANCE hInstance,
    UINT nIDResource) throw();
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
読み込まれるイメージが含まれるモジュールのインスタンスへのハンドルします。

*pszResourceName*<br/>
読み込むイメージを格納しているリソースの名前を含む文字列へのポインター。

*可能*<br/>
読み込むリソースの ID。

### <a name="remarks"></a>Remarks

ビットマップの種類のリソースがある必要があります。

##  <a name="maskblt"></a>  CImage::MaskBlt

指定したマスクとラスター オペレーションを使用してソースと変換先のビットマップのカラー データを結合します。

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

*hDestDC*<br/>
実行可能ファイルは、リソースを含むモジュールへのハンドル。

*xDest*<br/>
X 座標、先の四角形の左上隅の論理単位です。

*yDest*<br/>
Y 座標、先の四角形の左上隅の論理単位です。

*nDestWidth*<br/>
論理ユニットは、コピー先の四角形と元のビットマップの幅。

*nDestHeight*<br/>
論理ユニットは、コピー先の四角形と元のビットマップの高さ。

*xSrc*<br/>
ソース ビットマップの左上隅の論理 x 座標。

*ySrc*<br/>
ソース ビットマップの左上隅の論理 y 座標。

*hbmMask*<br/>
元のデバイス コンテキストのカラー ビットマップと組み合わせて、モノクロ マスク ビットマップへのハンドルします。

*xMask*<br/>
指定されたマスク ビットマップのピクセルを水平方向のオフセット、 *hbmMask*パラメーター。

*yMask*<br/>
指定されたマスク ビットマップの垂直方向のピクセルのオフセット、 *hbmMask*パラメーター。

*dwROP*<br/>
ソースと変換先のデータの組み合わせを制御するメソッドを使用する前景と背景の三項ラスター オペレーション コードを指定します。 バック グラウンドのラスター オペレーション コードがこの値の上位ワードの高位バイトに格納されています。フォア グラウンドのラスター オペレーション コードがこの値の上位ワードの下位バイトに格納されています。この値の下位ワードは無視され、0 にする必要があります。 前景色と背景では、このメソッドのコンテキストの詳細については、次を参照してください。 `MaskBlt` Windows SDK に含まれています。 共通のラスター オペレーション コードの一覧は、次を参照してください。 `BitBlt` Windows SDK に含まれています。

*rectDest*<br/>
参照を`RECT`構造体、変換先を識別します。

*pointSrc*<br/>
A`POINT`ソース四角形の左上隅を示す構造体。

*pointMask*<br/>
A`POINT`マスク ビットマップの左上隅を示す構造体。

*pointDest*<br/>
参照を`POINT`論理単位で、先の四角形の左上隅を識別する構造体。

### <a name="return-value"></a>戻り値

成功した場合、0 以外。 それ以外の場合に 0 です。

### <a name="remarks"></a>Remarks

このメソッドは、Windows NT では、バージョン 4.0 以降のみに適用されます。

##  <a name="operator_hbitmap"></a>  CImage::operator HBITMAP

接続されている Windows GDI ハンドルを取得するこの演算子を使用して、`CImage`オブジェクト。 この演算子は、キャスト演算子です。

##  <a name="plgblt"></a>  CImage::PlgBlt

コピー先のデバイス コンテキストでの平行四辺形には、ソース デバイス コンテキスト内の四角形からビット ブロック転送を実行します。

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

*hDestDC*<br/>
コピー先のデバイス コンテキストへのハンドル。

*pPoints*<br/>
先の平行四辺形の 3 つの角を識別する論理空間内の 3 つの点の配列へのポインター。 元の四角形の左上隅は、この配列、2 番目の点で、この配列に右上隅および 3 番目のポイントを左下隅の最初の要素にマップされます。 元の四角形の右上隅にあるは、暗黙の 4 番目のポイント、平行四辺形内にマップされます。

*hbmMask*<br/>
元の四角形の色をマスクするために使用するオプションのモノクロ ビットマップへのハンドル。

*xSrc*<br/>
X 座標、元の四角形の左上隅の論理単位で。

*ySrc*<br/>
Y 座標、元の四角形の左上隅の論理単位で。

*nSrcWidth*<br/>
論理ユニットは、元の四角形の幅。

*nSrcHeight*<br/>
論理ユニットは、元の四角形の高さ。

*xMask*<br/>
モノクロのビットマップの左上隅の x 座標。

*yMask*<br/>
モノクロのビットマップの左上隅の y 座標。

*rectSrc*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))ソース四角形の座標を指定する構造体。

*pointMask*<br/>
A[ポイント](/previous-versions/dd162805\(v=vs.85\))マスク ビットマップの左上隅を示す構造体。

### <a name="return-value"></a>戻り値

成功した場合、0 以外。 それ以外の場合に 0 です。

### <a name="remarks"></a>Remarks

場合*hbmMask*モノクロのビットマップが有効な`PlgBit`このビットマップを使用して、元の四角形の色データのビット マスクします。

このメソッドは、Windows NT では、バージョン 4.0 以降のみに適用されます。 参照してください[PlgBlt](/windows/desktop/api/wingdi/nf-wingdi-plgblt)より詳細な情報の Windows SDK に含まれています。

##  <a name="releasedc"></a>  CImage::ReleaseDC

デバイス コンテキストを解放します。

```
void ReleaseDC() const throw();
```

### <a name="remarks"></a>Remarks

呼び出す必要があるため、1 つだけのビットマップは、一度にデバイス コンテキストに選択することができます、`ReleaseDC`呼び出しごとに[GetDC](#getdc)します。

##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus

GDI + で使用されるリソースを解放します。

```
void ReleaseGDIPlus() throw();
```

### <a name="remarks"></a>Remarks

このメソッドは、グローバルによって割り当てられる無料のリソースを呼び出す必要があります`CImage`オブジェクト。 参照してください[CImage::CImage](#cimage)します。

##  <a name="save"></a>  CImage::Save

指定したストリーム、ディスク上のファイルにイメージを保存します。

```
HRESULT Save(
    IStream* pStream,
    REFGUID guidFileType) const throw();

HRESULT Save(
    LPCTSTR pszFileName,
    REFGUID guidFileType = GUID_NULL) const throw();
```

### <a name="parameters"></a>パラメーター

*pStream*<br/>
ファイルのイメージ データを含む COM IStream オブジェクトへのポインター。

*pszFileName*<br/>
イメージのファイル名へのポインター。

*guidFileType*<br/>
イメージを保存するファイルの種類。 次のいずれかの値を指定します。

- `ImageFormatBMP` 圧縮されていないビットマップ イメージです。

- `ImageFormatPNG` ポータブル ネットワーク グラフィックス (PNG) 圧縮されたイメージ。

- `ImageFormatJPEG` JPEG イメージを圧縮します。

- `ImageFormatGIF` Gif 形式では、イメージを圧縮します。

> [!NOTE]
> 定数の完全な一覧を参照してください。**イメージ ファイル形式の定数**Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>Remarks

指定した名前と型を使用してイメージを保存するには、この関数を呼び出します。 場合、 *guidFileType*パラメーターが含まれていない、ファイル名のファイルの拡張機能を使用してイメージ形式が決定されます。 拡張機能が指定されていない場合、イメージが BMP 形式で保存されます。

##  <a name="setcolortable"></a>  CImage::SetColorTable

DIB セクションのパレットで、エントリの範囲の赤、緑、青 (RGB) の色値を設定します。

```
void SetColorTable(
    UINT iFirstColor,
    UINT nColors,
    const RGBQUAD* prgbColors) throw();
```

### <a name="parameters"></a>パラメーター

*iFirstColor*<br/>
設定する最初のエントリのカラー テーブルのインデックス。

*nColors*<br/>
設定するカラー テーブル エントリの数。

*prgbColors*<br/>
配列へのポインター [RGBQUAD](/windows/desktop/api/wingdi/ns-wingdi-tagrgbquad)テーブル エントリの色を設定する構造体。

### <a name="remarks"></a>Remarks

このメソッドは、DIB セクション ビットマップのみをサポートします。

##  <a name="setpixel"></a>  CImage::SetPixel

ビットマップ内で指定した位置には、ピクセルの色を設定します。

```
void SetPixel(int x, int y, COLORREF color) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
設定するピクセルの水平方向の位置。

*y*<br/>
設定するピクセルの垂直方向の位置。

*色*<br/>
ピクセルを設定する色です。

### <a name="remarks"></a>Remarks

このメソッドは、ピクセルの座標が選択されたクリッピング領域の外にある場合に失敗します。

##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed

ある色にピクセルの色を設定*iIndex*色パレット。

```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
設定するピクセルの水平方向の位置。

*y*<br/>
設定するピクセルの垂直方向の位置。

*iIndex*<br/>
色パレットの色のインデックス。

##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB

指定された場所にあるピクセル設定*x*と*y*で示される色を*r*、 *g*、および*b*、赤、緑、青 (RGB) のイメージ。

```
void SetPixelRGB(
    int x,
    int y,
    BYTE r,
    BYTE g,
    BYTE b) throw();
```

### <a name="parameters"></a>パラメーター

*x*<br/>
設定するピクセルの水平方向の位置。

*y*<br/>
設定するピクセルの垂直方向の位置。

*r*<br/>
赤の色の彩度。

*g*<br/>
緑の色の彩度。

*b*<br/>
青の色の彩度。

### <a name="remarks"></a>Remarks

赤、緑、および青のパラメーターは、それぞれ 0 から 255 までの数値で表されます。 すべての 3 つのパラメーターを 0 に設定した場合、色は黒です。 すべての 3 つのパラメーターを 255 に設定した場合、色は白です。

##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor

透明色として指定したインデックス位置にある色を設定します。

```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```

### <a name="parameters"></a>パラメーター

*iTransparentColor*<br/>
透過色に設定する色のカラー パレット内のインデックス。 -1 の場合、色が設定されていない透過的です。

### <a name="return-value"></a>戻り値

以前の色のインデックスに透明色として設定します。

##  <a name="stretchblt"></a>  CImage::StretchBlt

現在のデバイス コンテキストを元のデバイス コンテキストからビットマップをコピーします。

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

*hDestDC*<br/>
コピー先のデバイス コンテキストへのハンドル。

*xDest*<br/>
X 座標、先の四角形の左上隅の論理単位です。

*yDest*<br/>
Y 座標、先の四角形の左上隅の論理単位です。

*nDestWidth*<br/>
論理ユニットは、先の四角形の幅。

*nDestHeight*<br/>
論理ユニットは、先の四角形の高さ。

*dwROP*<br/>
実行するラスター操作。 ラスター オペレーション コードは、変換先を形成するソース、変換先、およびパターンのビット (現在選択されているブラシによって定義される) とを組み合わせる方法を定義します。 参照してください[BitBlt](/windows/desktop/api/wingdi/nf-wingdi-bitblt)他ラスター オペレーション コードとその説明の一覧については、Windows sdk。

*rectDest*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))構造体、変換先を識別します。

*xSrc*<br/>
X 座標、元の四角形の左上隅の論理単位で。

*ySrc*<br/>
Y 座標、元の四角形の左上隅の論理単位で。

*nSrcWidth*<br/>
論理ユニットは、元の四角形の幅。

*nSrcHeight*<br/>
論理ユニットは、元の四角形の高さ。

*rectSrc*<br/>
参照を`RECT`構造体、ソースを特定します。

### <a name="return-value"></a>戻り値

成功した場合、0 以外。 それ以外の場合に 0 です。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [StretchBlt](/windows/desktop/api/wingdi/nf-wingdi-stretchblt) Windows SDK に含まれています。

##  <a name="transparentblt"></a>  CImage::TransparentBlt

現在のデバイス コンテキストを元のデバイス コンテキストからビットマップをコピーします。

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

*hDestDC*<br/>
コピー先のデバイス コンテキストへのハンドル。

*xDest*<br/>
X 座標、先の四角形の左上隅の論理単位です。

*yDest*<br/>
Y 座標、先の四角形の左上隅の論理単位です。

*nDestWidth*<br/>
論理ユニットは、先の四角形の幅。

*nDestHeight*<br/>
論理ユニットは、先の四角形の高さ。

*crTransparent*<br/>
透明色として処理するソース ビットマップの色。 既定では、CLR_INVALID は、現在のイメージの透明色として設定されている色を使用することを指定します。

*rectDest*<br/>
参照を[RECT](/previous-versions/dd162897\(v=vs.85\))構造体、変換先を識別します。

*xSrc*<br/>
X 座標、元の四角形の左上隅の論理単位で。

*ySrc*<br/>
Y 座標、元の四角形の左上隅の論理単位で。

*nSrcWidth*<br/>
論理ユニットは、元の四角形の幅。

*nSrcHeight*<br/>
論理ユニットは、元の四角形の高さ。

*rectSrc*<br/>
参照を`RECT`構造体、ソースを特定します。

### <a name="return-value"></a>戻り値

TRUE の場合は成功しましたが、それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

`TransparentBlt` ソース ビットマップのピクセルごと、およびピクセルあたり 8 ビット 4 ビット サポートされます。 使用[CImage::AlphaBlend](#alphablend)透明度が 32 ビット/ピクセルのビットマップを指定します。

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

[MMXSwarm サンプル](../../visual-cpp-samples.md)<br/>
[SimpleImage サンプル](../../visual-cpp-samples.md)<br/>
[デバイスに依存しないビットマップ](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)<br/>
[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)<br/>
[デバイスに依存しないビットマップ](/windows/desktop/gdi/device-independent-bitmaps)<br/>
[CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibsection)
