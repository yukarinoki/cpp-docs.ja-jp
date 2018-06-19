---
title: CImage クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 02/01/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 762941834820edda09970750af752d4c8a9df61c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366316"
---
# <a name="cimage-class"></a>CImage クラス
`CImage` 読み込み、JPEG、GIF、BMP、およびポータブル ネットワーク グラフィックス (PNG) 形式で画像を保存する機能を含む、ビットマップの拡張サポートを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
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
|[CImage::Attach](#attach)|アタッチ、`HBITMAP`を`CImage`オブジェクト。 非 DIB セクション ビットマップや DIB セクション ビットマップのいずれかで使用できます。|  
|[CImage::BitBlt](#bitblt)|コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。|  
|[CImage::Create](#create)|DIB セクション ビットマップを作成し、構築済みにアタッチします。`CImage`オブジェクト。|  
|[CImage::CreateEx](#createex)|パラメーターを持つ追加 DIB セクション ビットマップを作成し、構築済みにアタッチします。`CImage`オブジェクト。|  
|[CImage::Destroy](#destroy)|ビットマップからのデタッチ、`CImage`オブジェクトをビットマップを破棄します。|  
|[CImage::Detach](#detach)|ビットマップからのデタッチ、`CImage`オブジェクト。|  
|[CImage::Draw](#draw)|元の四角形から転送先の四角形にビットマップをコピーします。 **描画**拡大または必要に応じて、対象の四角形の寸法に合わせてビットマップの圧縮し、処理アルファ ブレンド透明色。|  
|[CImage::GetBits](#getbits)|ビットマップの実際のピクセル値へのポインターを取得します。|  
|[CImage::GetBPP](#getbpp)|ピクセルごとのビットを取得します。|  
|[CImage::GetColorTable](#getcolortable)|カラー テーブル内のエントリの範囲から赤、緑、青 (RGB) の色の値を取得します。|  
|[CImage::GetDC](#getdc)|現在のビットマップが選択されているデバイス コンテキストを取得します。|  
|[CImage::GetExporterFilterString](#getexporterfilterstring)|使用可能なイメージ形式とその説明を検索します。|  
|[CImage::GetHeight](#getheight)|現在のイメージの高さ (ピクセル単位) を取得します。|  
|[CImage::GetImporterFilterString](#getimporterfilterstring)|使用可能なイメージ形式とその説明を検索します。|  
|[CImage::GetMaxColorTableEntries](#getmaxcolortableentries)|カラー テーブル内のエントリの最大数を取得します。|  
|[CImage::GetPitch](#getpitch)|(バイト単位)、現在のイメージの声の高さを取得します。|  
|[CImage::GetPixel](#getpixel)|指定されたピクセルの色を取得*x*と*y*です。|  
|[CImage::GetPixelAddress](#getpixeladdress)|特定のピクセルのアドレスを取得します。|  
|[CImage::GetTransparentColor](#gettransparentcolor)|透明色のカラー テーブル内の位置を取得します。|  
|[CImage::GetWidth](#getwidth)|現在のイメージの幅 (ピクセル単位) を取得します。|  
|[CImage::IsDIBSection](#isdibsection)|割り当てられているビットマップが DIB セクションであるかどうかを判断します。|  
|[CImage::IsIndexed](#isindexed)|インデックス付きのパレットにビットマップの色がマップされていることを示します。|  
|[CImage::IsNull](#isnull)|元のビットマップが現在読み込まれているかどうかを示します。|  
|[CImage::IsTransparencySupported](#istransparencysupported)|アプリケーションが透明なビットマップをサポートするかどうかを示します。|  
|[CImage::Load](#load)|指定したファイルからイメージを読み込みます。|  
|[CImage::LoadFromResource](#loadfromresource)|指定されたリソースからイメージを読み込みます。|  
|[CImage::MaskBlt](#maskblt)|指定したマスクとラスター オペレーションを使用する元とコピー先のビットマップの色のデータを結合します。|  
|[CImage::PlgBlt](#plgblt)|コピー先デバイス コンテキストで指定した平行四辺形に元のデバイス コンテキスト内の四角形からのビット ブロック転送を実行します。|  
|[CImage::ReleaseDC](#releasedc)|取得されたデバイス コンテキストを解放[CImage::GetDC](#getdc)です。|  
|[CImage::ReleaseGDIPlus](#releasegdiplus)|GDI + で使用されるリソースを解放します。 グローバルによって作成されたリソースの解放を呼び出す必要がある`CImage`オブジェクト。|  
|[CImage::Save](#save)|指定した型と、イメージを保存します。 **保存**イメージのオプションを指定することはできません。|  
|[CImage::SetColorTable](#setcolortable)|赤、緑、青の RGB を設定します)、DIB セクションのカラー テーブル内のエントリの範囲内の値の色します。|  
|[CImage::SetPixel](#setpixel)|指定した色の指定した座標にあるピクセルに設定します。|  
|[CImage::SetPixelIndexed](#setpixelindexed)|色パレットの指定したインデックス位置に指定した座標にあるピクセルに設定します。|  
|[CImage::SetPixelRGB](#setpixelrgb)|指定された赤、緑、青 (RGB) の値を指定した座標にあるピクセルに設定します。|  
|[CImage::SetTransparentColor](#settransparentcolor)|透明として扱われる色のインデックスを設定します。 パレットの 1 つだけの色を透明にすることができます。|  
|[CImage::StretchBlt](#stretchblt)|元の四角形から変換先に四角形を拡大または移行先の四角形の寸法に合わせてビットマップを縮小して必要な場合にビットマップをコピーします。|  
|[CImage::TransparentBlt](#transparentblt)|現在のデバイス コンテキストを元のデバイス コンテキストからの透明色のビットマップをコピーします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CImage::operator HBITMAP](#operator_hbitmap)|接続されている Windows ハンドルを返します、`CImage`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CImage` ビットマップかのいずれかのデバイスに依存しないビットマップ (DIB) セクションではありません。ただし、使用することができます[作成](#create)または[CImage::Load](#load) DIB セクションのみを含むです。 非 DIB セクション ビットマップをアタッチすることができます、`CImage`オブジェクトを使用して[アタッチ](#attach)、し、以下を使用することはできませんが、 `CImage` DIB セクション ビットマップのみをサポートする方法。  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
 割り当てられているビットマップが DIB セクションを確認するには、呼び出す[IsDibSection](#isdibsection)**です。**  
  
> [!NOTE]
> **注**Visual Studio .NET 2003 で、このクラスは、数のカウントを保持`CImage`オブジェクトを作成します。 カウントが 0 の場合、関数になるたびに**オブジェクト**GDI + で使用されるリソースを解放する、自動的に呼び出されます。 これにより、いずれかの`CImage`Dll が直接または間接的を作成したオブジェクトが正しく破棄される常に、**オブジェクト**からは呼び出されません`DllMain`です。  
  
> [!NOTE]
>  グローバルを使用して`CImage`DLL 内のオブジェクトはお勧めしません。 グローバルを使用する必要がある場合`CImage`呼び出し、DLL 内のオブジェクト[CImage::ReleaseGDIPlus](#releasegdiplus)を明示的に GDI + で使用されるリソースを解放します。  
  
 `CImage` 新しいに選択することはできません[CDC](../../mfc/reference/cdc-class.md)です。 `CImage` 独自に作成**HDC**イメージにします。 `HBITMAP`を 1 つにのみ選択できます**HDC** 、時に、`HBITMAP`に関連付けられている、`CImage`別に選択することはできません**HDC**です。 必要がある場合、 `CDC`、取得、 **HDC**から、`CImage`し、[CDC::FromHandle] (../../mfc/reference/cdc-class.md#cdc__fromhandle です。  
  
## <a name="example"></a>例  
```cpp  
// Get a CDC for the image
CDC* pDC = CDC::FromHandle(m_myImage.GetDC());

// Use pDC here
pDC->Rectangle(0, 40, 100, 50);
m_myImage.ReleaseDC();
```  
  
 使用すると`CImage`MFC プロジェクトでは、プロジェクトのどのメンバー関数へのポインターの期待に注意してください、 [CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクト。 使用する場合`CImage`このような関数を使用と同様に[CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)を使用して[CBitmap::FromHandle](../../mfc/reference/cbitmap-class.md#fromhandle)、渡す、 `CImage` `HBITMAP`、返されたを使用して`CBitmap*`.  

  
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

  
 を通じて`CImage`、DIB セクションの実際のビットへのアクセス権があります。 使用することができます、 `CImage` Win32 HBITMAP や dib でもセクションを使用していたオブジェクトの任意の場所。  
  
 使用することができます`CImage`MFC または ATL のいずれかから  
  
> [!NOTE]
>  使用してプロジェクトを作成する場合`CImage`、定義する必要があります`CString`インクルードする前に`atlimage.h`です。 プロジェクトでは、MFC を使わない ATL を使用する場合は、`atlstr.h`インクルードする前に`atlimage.h`です。 プロジェクトでは、MFC (MFC サポートを使用して、ATL プロジェクトであるかどうか) を使用する場合は、`afxstr.h`インクルードする前に`atlimage.h`です。  
>   
>  同様に、含める必要があります`atlimage.h`インクルードする前に`atlimpl.cpp`です。 これを実現する簡単に含める`atlimage.h`で、`stdafx.h`です。  
  
## <a name="requirements"></a>要件  
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
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドルします。  
  
 `xDest`  
 X 座標、先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標を論理単位で、移行先の四角形の左上隅にあるのです。  
  
 *bSrcAlpha*  
 元のビットマップ全体で使用するアルファ透明度値。 既定値 0 xff (255) には、イメージが不透明であると、ピクセルごとのアルファ値のみを使用することが前提とします。  
  
 `bBlendOp`  
 ソースと、コピー先ビットマップを全体の元のビットマップ、および元のビットマップの書式情報に適用されるグローバルなアルファ値のアルファ ブレンド関数。 送信元と送信先の blend 関数に制限されて**ビットマップ**です。  
  
 `pointDest`  
 参照、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)論理単位で、移行先の四角形の左上隅を識別する構造体。  
  
 `nDestWidth`  
 論理ユニットは、先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、先の四角形の高さ。  
  
 `xSrc`  
 元の四角形の左上隅の論理 x 座標。  
  
 `ySrc`  
 元の四角形の左上隅の論理 y 座標。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、変換先を識別します。  
  
 `rectSrc`  
 参照、`RECT`構造体、ソースを特定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アルファ ブレンドのビットマップは、ピクセル単位で色の混合をサポートします。  
  
 ときに`bBlendOp`の既定値に設定されている**ビットマップ**元のピクセルのアルファ値に基づいて、コピー先ビットマップに元のビットマップが配置されます。  

##  <a name="attach"></a>  CImage::Attach  
 アタッチ`hBitmap`を`CImage`オブジェクト。  
  
```
void Attach(HBITMAP hBitmap, DIBOrientation eOrientation = DIBOR_DEFAULT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hBitmap`  
 ハンドル、`HBITMAP`です。  
  
 *eOrientation*  
 ビットマップの向きを指定します。 次のいずれかの値を指定します。  
  
- **DIBOR_DEFAULT**ビットマップの向きは、オペレーティング システムによって決定されます。 ただし、このことはできません常に目的の結果にすべてのオペレーティング システム。 詳細については、次のサポート技術情報の記事を参照してください ( **Q186586**): [prb]: 概念常に返します正高さの DIB のセクションでします。  
  
- **DIBOR_BOTTOMUP**ビットマップの行は逆の順序でです。 これにより、 [CImage::GetBits](#getbits)ビットマップ バッファーの末尾付近のポインターを返すと[CImage::GetPitch](#getpitch)を負の数を返します。  
  
- **DIBOR_TOPDOWN**上下からにビットマップの行があります。 これにより、 [CImage::GetBits](#getbits)をビットマップ バッファーの最初のバイトへのポインターを返すと[CImage::GetPitch](#getpitch)を正の数値を返します。  
  
### <a name="remarks"></a>コメント  
 ビットマップには、非 DIB セクション ビットマップや DIB セクション ビットマップのいずれかを指定できます。 参照してください[IsDIBSection](#isdibsection) DIB でのみ使用できるメソッドの一覧については、ビットマップをセクションです。  
  
##  <a name="bitblt"></a>  CImage::BitBlt  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
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
 `hDestDC`  
 転送先**HDC**です。  
  
 `xDest`  
 移行先の四角形の左上隅の論理 x 座標。  
  
 `yDest`  
 移行先の四角形の左上隅の論理 y 座標。  
  
 `dwROP`  
 実行するラスター オペレーションです。 ラスター オペレーション コードは、変換先を形成する、ソース、変換先、およびパターンのビット (で定義されている、現在選択されているブラシ) を組み合わせる方法を定義します。 参照してください[BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370)その他のラスター オペレーション コードとその説明の一覧については Windows SDK に含まれています。  
  
 `pointDest`  
 A[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)先の四角形の左上隅を示す構造体。  
  
 `nDestWidth`  
 論理ユニットは、先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、先の四角形の高さ。  
  
 `xSrc`  
 元の四角形の左上隅の論理 x 座標。  
  
 `ySrc`  
 元の四角形の左上隅の論理 y 座標。  
  
 `rectDest`  
 A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)先の四角形を示す構造体。  
  
 `pointSrc`  
 A**ポイント**元の四角形の左上隅を示す構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370) Windows SDK に含まれています。  
  
##  <a name="cimage"></a>  CImage::CImage  
 `CImage` オブジェクトを構築します。  
  
```
CImage() throw();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトを作成した後で呼び出す[作成](#create)、[ロード](#load)、 [LoadFromResource](#loadfromresource)、または[アタッチ](#attach)ビットマップをオブジェクトにアタッチします。  
  
 **注**Visual Studio では、このクラスは、数のカウントを保持`CImage`オブジェクトを作成します。 カウントが 0 の場合、関数になるたびに**オブジェクト**GDI + で使用されるリソースを解放する、自動的に呼び出されます。 これにより、いずれかの`CImage`Dll が直接または間接的を作成したオブジェクトが正しく破棄される常に、**オブジェクト**DllMain からは呼び出されません。  
  
 グローバルを使用して`CImage`DLL 内のオブジェクトはお勧めしません。 グローバルを使用する必要がある場合`CImage`呼び出し、DLL 内のオブジェクト[CImage::ReleaseGDIPlus](#releasegdiplus)を明示的に GDI + で使用されるリソースを解放します。  
  
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
 `nWidth`  
 幅、 `CImage` (ピクセル単位) のビットマップ。  
  
 `nHeight`  
 高さ、 `CImage` (ピクセル単位) のビットマップ。 場合`nHeight`が正の値、ビットマップはボトムアップ DIB と原点は左下隅です。 場合`nHeight`は負の場合、ビットマップが上から下へ DIB を起点と左上隅です。  
  
 `nBPP`  
 ビットマップのピクセルごとのビット数。 通常、4、8、16、24、または 32 です。 モノクロ ビットマップやマスクを 1 にすることができます。  
  
 `dwFlags`  
 かどうか、ビットマップ オブジェクトはアルファ チャネルを指定します。 次の値の 0 個以上の組み合わせが可能です。  
  
- **createAlphaChannel**場合にのみ使用できます`nBPP`32、および`eCompression`は**値**です。 指定した場合、各ピクセル (英数字以外の 32 ビットのイメージで使用されていない) の第 4 バイトに格納されている、各ピクセルのアルファ (透明度) 値を作成したイメージがあります。 呼び出すときに自動的に、このアルファ チャネルが使用[CImage::AlphaBlend](#alphablend)です。  
  
> [!NOTE]
>  呼び出しで[:draw](#draw)、アルファ チャネルを持つイメージは自動的にアルファ、変換先に統合します。  
  
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
 `nWidth`  
 幅、 `CImage` (ピクセル単位) のビットマップ。  
  
 `nHeight`  
 高さ、 `CImage` (ピクセル単位) のビットマップ。 場合`nHeight`が正の値、ビットマップはボトムアップ DIB と原点は左下隅です。 場合`nHeight`は負の場合、ビットマップが上から下へ DIB を起点と左上隅です。  
  
 `nBPP`  
 ビットマップのピクセルごとのビット数。 通常、4、8、16、24、または 32 です。 モノクロ ビットマップやマスクを 1 にすることができます。  
  
 `eCompression`  
 (上から下へ Dib は圧縮できません)、圧縮されたボトムアップ ビットマップの圧縮の種類を指定します。 次のいずれかの値になります。  
  
- **値**形式に圧縮されていません。 呼び出すときに、この値を指定する`CImage::CreateEx`は呼び出すことと同じ`CImage::Create`です。  
  
- **BI_BITFIELDS**形式に圧縮されていないと、カラー テーブルから成る 3`DWORD`赤を指定するカラー マスク、緑、青のコンポーネントがそれぞれ、各ピクセルのです。 これは、16、32 bpp のビットマップを使用すると有効です。  
  
 *pdwBitfields*  
 場合にのみ使用`eCompression`に設定されている**BI_BITFIELDS**、それ以外の場合があります**NULL**です。 3 つの配列へのポインター`DWORD`のどのビットごとのピクセルは、赤の使用を指定するビットマスクが、緑、青の色のコンポーネントがそれぞれします。 ビット フィールドの制限については、次を参照してください。 [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376) Windows SDK に含まれています。  
  
 `dwFlags`  
 かどうか、ビットマップ オブジェクトはアルファ チャネルを指定します。 次の値の 0 個以上の組み合わせが可能です。  
  
- **createAlphaChannel**場合にのみ使用できます`nBPP`32、および`eCompression`は**値**です。 指定した場合、各ピクセル (英数字以外の 32 ビットのイメージで使用されていない) の第 4 バイトに格納されている、各ピクセルのアルファ (透明度) 値を作成したイメージがあります。 呼び出すときに自動的に、このアルファ チャネルが使用[CImage::AlphaBlend](#alphablend)です。  
  
    > [!NOTE]
    >  呼び出しで[:draw](#draw)、アルファ チャネルを持つイメージは自動的にアルファ、変換先に統合します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**正常終了した場合。 それ以外の場合**FALSE**です。  
  
### <a name="example"></a>例  
 次の例では、各ピクセルのエンコードに 16 ビットを使用して、100 x 100 ピクセルのビットマップを作成します。 指定した 16 ビットのピクセルでは、赤の要素のエンコード ビット 0-3、4 ~ 7 ビット エンコード緑、および 8 ~ 11 ビット エンコード青。 残りの 4 ビットは、使用されません。  

```cpp  
DWORD adwBitmasks[3] = { 0x0000000f, 0x000000f0, 0x00000f00 };
m_myImage.CreateEx(100, 100, 16, BI_BITFIELDS, adwBitmasks, 0);
```


##  <a name="destroy"></a>  CImage::Destroy  
 ビットマップからのデタッチ、`CImage`オブジェクトをビットマップを破棄します。  
  
```
void Destroy() throw();
```  
  
##  <a name="detach"></a>  CImage::Detach  
 ビットマップからのデタッチ、`CImage`オブジェクト。  
  
```
HBITMAP Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチ、ビットマップへのハンドルまたは**NULL**ビットマップが添付されていない場合。  
  
##  <a name="draw"></a>  :Draw  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
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
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 `xDest`  
 X 座標、先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標を論理単位で、移行先の四角形の左上隅にあるのです。  
  
 `nDestWidth`  
 論理ユニットは、先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、先の四角形の高さ。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、変換先を識別します。  
  
 `rectSrc`  
 参照、`RECT`構造体、ソースを特定します。  
  
 `pointDest`  
 参照、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)論理単位で、移行先の四角形の左上隅を識別する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **描画**と同じ操作を実行[StretchBlt](#stretchblt)イメージには、透明色のアルファ チャネルが含まれている場合を除き、します。 その場合は、**描画**いずれかと同じ操作を実行[TransparentBlt](#transparentblt)または[およびアルファブレンド](#alphablend)必要に応じて。  
  
 バージョンの**描画**元の四角形を指定しない、ソース イメージ全体は、既定値です。 バージョンの**描画**する先の四角形のサイズが指定されていません、ソース イメージのサイズは、既定または縮小が行われます。  
  
##  <a name="getbits"></a>  CImage::GetBits  
 ビットマップ内の特定のピクセルの実際のビット値へのポインターを取得します。  
  
```
void* GetBits() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ビットマップ バッファーへのポインター。 ビットマップがボトムアップ DIB の場合は、バッファーの末尾の近くポインター。 場合は、トップダウン DIB、バッファーの最初のバイトを指すポインターです。  
  
### <a name="remarks"></a>コメント  
 によって返される値と共に、このポインターを使用して[GetPitch](#getpitch)を検索し、画像内の個々 のピクセルを変更できます。  
  
> [!NOTE]
>  このメソッドは、DIB セクション ビットマップのみをサポートしています。したがって、アクセスするアクセスのピクセル、 `CImage` DIB セクションのピクセルのと同様のオブジェクトします。 返されるポインターが指す位置 (0, 0)、ピクセルです。  
  
##  <a name="getbpp"></a>  CImage::GetBPP  
 ピクセルあたりのビット値を取得します。  
  
```
int GetBPP() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 1 ピクセルあたりのビット数。  
  
### <a name="remarks"></a>コメント  
 この値は、各ピクセルを定義するビットの数とビットマップの色の最大数を決定します。  
  
 ピクセルごとのビットは 1、4、8、16、24、または 32 では通常です。 参照してください、 **biBitCount**のメンバー [BITMAPINFOHEADER](http://msdn.microsoft.com/library/windows/desktop/dd183376)この値の詳細については、Windows SDK に含まれています。  
  
##  <a name="getcolortable"></a>  CImage::GetColorTable  
 DIB セクションのパレット内のエントリの範囲から赤、緑、青 (RGB) の色の値を取得します。  
  
```
void GetColorTable(UINT iFirstColor,
 UINT nColors,
 RGBQUAD* prgbColors) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iFirstColor`  
 取得する最初のエントリのカラー テーブルのインデックス。  
  
 `nColors`  
 取得するカラー テーブル エントリの数。  
  
 `prgbColors`  
 配列へのポインター [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)構造体の色を取得するテーブルのエントリ。  
  
##  <a name="getdc"></a>  CImage::GetDC  
 現在選択されているイメージのあるデバイス コンテキストを取得します。  
  
```
HDC GetDC() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 デバイス コンテキストを識別するハンドル。  
  
### <a name="remarks"></a>コメント  
 呼び出しごとに`GetDC`、後続の呼び出しにする必要があります[ReleaseDC](#releasedc)です。  
  
##  <a name="getexporterfilterstring"></a>  CImage::GetExporterFilterString  
 イメージを保存するためには、使用できるイメージ形式を検索します。  
  
```
static HRESULT GetExporterFilterString(CSimpleString& strExporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultSave,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>パラメーター  
 *strExporters*  
 参照、 **CSimpleString**オブジェクト。 参照してください**解説**詳細についてはします。  
  
 `aguidFileTypes`  
 文字列内のファイルの種類のいずれかに対応する各要素に、Guid の配列。 例では`pszAllFilesDescription`下、 `aguidFileTypes`[0] は`GUID_NULL`残りの配列値は、現在のオペレーティング システムでサポートされているイメージ ファイル形式とします。  
  
> [!NOTE]
>  定数の完全な一覧を参照してください。**イメージ ファイル形式の定数**Windows SDK に含まれています。  
  
 `pszAllFilesDescription`  
 このパラメーターがない場合**NULL**、フィルター文字列は、一覧の先頭に追加の 1 つのフィルターがします。 このフィルターはの現在の値に`pszAllFilesDescription`その説明の一覧で、その他のエクスポーターでサポートされている任意の拡張子のファイルを受け入れるとします。  
  
 例えば:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any exporter.
CImage::GetExporterFilterString(
    strExporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 一覧から除外するファイルの種類を指定するビット フラグのセット。 指定できるフラグは次のとおりです。  
  
- **excludeGIF** 0x01 除外 GIF ファイルを = です。  
  
- **excludeBMP** 0x02 除外 BMP (Windows ビットマップ) ファイルを = です。  
  
- **excludeEMF** = 0x04 除外 EMF (拡張メタファイル) ファイル。  
  
- **excludeWMF** 0x08 除外 WMF (Windows メタファイル) ファイルを = です。  
  
- **excludeJPEG** 0x10 除外 JPEG ファイルを = です。  
  
- **excludePNG** 0x20 除外 PNG ファイルを = です。  
  
- **excludeTIFF** 0x40 除外 TIFF ファイルを = です。  
  
- **excludeIcon** 0x80 除外 ICO (Windows のアイコン) ファイルを = です。  
  
- **excludeOther** = 0x80000000 が上記以外の他のファイル種類を除外します。  
  
- **excludeDefaultLoad** load]、[既定の型が含まれているすべてのファイルの場合は 0 を =  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF**特別な要件があるためには、これらのファイルを既定で除外するよう、保存するためです。  
  
 `chSeparator`  
 イメージ形式の間で使用される区切り記号。 参照してください**解説**詳細についてはします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
### <a name="remarks"></a>コメント  
 MFC には、結果の書式指定文字列を渡すことができます[CFileDialog](../../mfc/reference/cfiledialog-class.md)ファイル名を付けて保存 ダイアログ ボックスで使用可能なイメージ ファイルの拡張機能を公開するオブジェクトの書式します。  
  
 パラメーター *strExporter*形式があります。  
  
 ファイルの description0&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;.. .file 説明*n*&#124;\*.ext *n*&#124;&#124;  
  
 場所 '&#124;' で指定された区切り記号`chSeparator`です。 例えば:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 既定の区切り記号を使用して '&#124;' MFC にこの文字列を渡す場合`CFileDialog`オブジェクト。 一般的な名前を付けて保存 ダイアログ ボックスにこの文字列を渡す場合は、null の区切り記号 '\0' を使用します。  
  
##  <a name="getheight"></a>  CImage::GetHeight  
 イメージのピクセル単位の高さを取得します。  
  
```
int GetHeight() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 イメージのピクセル単位の高さ。  
  
##  <a name="getimporterfilterstring"></a>  CImage::GetImporterFilterString  
 イメージの読み込みに使用できるイメージ形式を検索します。  
  
```
static HRESULT GetImporterFilterString(CSimpleString& strImporters,
 CSimpleArray<GUID>& aguidFileTypes,
 LPCTSTR pszAllFilesDescription = NULL,
 DWORD dwExclude = excludeDefaultLoad,
 TCHAR chSeparator = _T('|'));
```  
  
### <a name="parameters"></a>パラメーター  
 *strImporters*  
 参照、 **CSimpleString**オブジェクト。 参照してください**解説**詳細についてはします。  
  
 `aguidFileTypes`  
 文字列内のファイルの種類のいずれかに対応する各要素に、Guid の配列。 例では`pszAllFilesDescription`下、 `aguidFileTypes`[0] は`GUID_NULL`残りの配列を持つ値は、現在のオペレーティング システムでサポートされているイメージ ファイル形式。  
  
> [!NOTE]
>  定数の完全な一覧を参照してください。**イメージ ファイル形式の定数**Windows SDK に含まれています。  
  
 `pszAllFilesDescription`  
 このパラメーターがない場合**NULL**、フィルター文字列は、一覧の先頭に追加の 1 つのフィルターがします。 このフィルターはの現在の値に`pszAllFilesDescription`その説明の一覧で、その他のエクスポーターでサポートされている任意の拡張子のファイルを受け入れるとします。  
  
 例えば:  

```cpp  
//First filter in the list will be titled "All Image Files", and
//will accept files with any extension supported by any importer.
CImage::GetImporterFilterString(
    strImporters, aguidFileTypes, 
 _T("All Image Files"));
```  

  
 `dwExclude`  
 一覧から除外するファイルの種類を指定するビット フラグのセット。 指定できるフラグは次のとおりです。  
  
- **excludeGIF** 0x01 除外 GIF ファイルを = です。  
  
- **excludeBMP** 0x02 除外 BMP (Windows ビットマップ) ファイルを = です。  
  
- **excludeEMF** = 0x04 除外 EMF (拡張メタファイル) ファイル。  
  
- **excludeWMF** 0x08 除外 WMF (Windows メタファイル) ファイルを = です。  
  
- **excludeJPEG** 0x10 除外 JPEG ファイルを = です。  
  
- **excludePNG** 0x20 除外 PNG ファイルを = です。  
  
- **excludeTIFF** 0x40 除外 TIFF ファイルを = です。  
  
- **excludeIcon** 0x80 除外 ICO (Windows のアイコン) ファイルを = です。  
  
- **excludeOther** = 0x80000000 が上記以外の他のファイル種類を除外します。  
  
- **excludeDefaultLoad** load]、[既定の型が含まれているすべてのファイルの場合は 0 を =  
  
- **excludeDefaultSave** = **excludeIcon &#124; excludeEMF &#124; excludeWMF**特別な要件があるためには、これらのファイルを既定で除外するよう、保存するためです。  
  
 `chSeparator`  
 イメージ形式の間で使用される区切り記号。 参照してください**解説**詳細についてはします。  
  
### <a name="remarks"></a>コメント  
 MFC には、結果の書式指定文字列を渡すことができます[CFileDialog](../../mfc/reference/cfiledialog-class.md)で使用可能なイメージ ファイルの拡張機能を公開するオブジェクトの書式、**ファイルを開く** ダイアログ ボックス。  
  
 パラメーター *strImporter*形式があります。  
  
 ファイルの description0&#124;\*.ext0&#124;filedescription1&#124;\*.ext1&#124;.. .file 説明*n*&#124;\*.ext *n*&#124;&#124;  
  
 場所 '&#124;' で指定された区切り記号`chSeparator`です。 例えば:  
  
 `"Bitmap format|*.bmp|JPEG format|*.jpg|GIF format|*.gif|PNG format|*.png||"`  
  
 既定の区切り記号を使用して '&#124;' MFC にこの文字列を渡す場合`CFileDialog`オブジェクト。 共通にこの文字列を渡す場合、null の区切り記号 '\0' を使用して**ファイルを開く** ダイアログ ボックス。  
  
##  <a name="getmaxcolortableentries"></a>  CImage::GetMaxColorTableEntries  
 カラー テーブル内のエントリの最大数を取得します。  
  
```
int GetMaxColorTableEntries() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 カラー テーブル内のエントリの数。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、DIB セクション ビットマップのみがサポートしています。  
  
##  <a name="getpitch"></a>  CImage::GetPitch  
 イメージの声の高さを取得します。  
  
```
int GetPitch() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 イメージのピッチです。 戻り値が負の場合、ビットマップはボトムアップ DIB を起点と左下隅です。 戻り値が正の場合は、ビットマップが上から下へ DIB を起点と左上隅です。  
  
### <a name="remarks"></a>コメント  
 ピッチは、(バイト単位) を 1 つのビットマップの行の先頭を表す 2 つのメモリ アドレスとビットマップの次の行の先頭の間の距離です。 声の高さは、バイト単位で測定されるため、イメージのピッチでは、ピクセル形式を決定することができます。 ピッチでは、ビットマップ用に予約の追加のメモリを含めることもできます。  
  
 使用して`GetPitch`で[GetBits](#getbits)を個々 のピクセルの画像を検索します。  
  
> [!NOTE]
>  このメソッドには、DIB セクション ビットマップのみがサポートしています。  
  
##  <a name="getpixel"></a>  CImage::GetPixel  
 指定された位置のピクセルの色を取得*x*と*y*です。  
  
```
COLORREF GetPixel(int x,int y) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 ピクセルの x 座標。  
  
 *y*  
 ピクセルの y 座標。  
  
### <a name="return-value"></a>戻り値  
 赤、緑、青 (RGB) の値、ピクセルです。 戻り値は、ピクセルが現在のクリップ領域外にある場合は、 **CLR_INVALID**です。  
  
##  <a name="getpixeladdress"></a>  CImage::GetPixelAddress  
 ピクセルの正確なアドレスを取得します。  
  
```
void* GetPixelAddress(int x,int y) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 ピクセルの x 座標。  
  
 *y*  
 ピクセルの y 座標。  
  
### <a name="remarks"></a>コメント  
 アドレスは、ピクセルの座標、ビットマップ、およびピクセルあたりのビットのピッチに従って決定されます。  
  
 1 ピクセルあたり 8 ビット未満のある形式の場合は、このメソッドは、ピクセルを含むバイトのアドレスを返します。 たとえば、イメージの形式は 4 ビット/ピクセル、`GetPixelAddress`を返します。 1 バイトの 2 つのピクセルの最初のピクセルにすると、バイトのアドレスを計算する必要があります。  
  
> [!NOTE]
>  このメソッドには、DIB セクション ビットマップのみがサポートしています。  
  
##  <a name="gettransparentcolor"></a>  CImage::GetTransparentColor  
 カラー パレットの透明色の位置を示すインデックスを取得します。  
  
```
LONG GetTransparentColor() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 透明色のインデックス。  
  
##  <a name="getwidth"></a>  CImage::GetWidth  
 イメージのピクセル単位の幅を取得します。  
  
```
int GetWidth() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、ビットマップの幅。  
  
##  <a name="isdibsection"></a>  CImage::IsDIBSection  
 割り当てられているビットマップが DIB セクションであるかどうかを判断します。  
  
```
bool IsDIBSection() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 **true**アタッチされているビットマップは DIB セクション場合。 それ以外の場合**false**です。  
  
### <a name="remarks"></a>コメント  
 ビットマップは DIB セクションではない場合は、以下を使用することはできません`CImage`DIB セクション ビットマップのみをサポートするメソッド。  
  
- [GetBits](#getbits)  
  
- [GetColorTable](#getcolortable)  
  
- [GetMaxColorTableEntries](#getmaxcolortableentries)  
  
- [GetPitch](#getpitch)  
  
- [GetPixelAddress](#getpixeladdress)  
  
- [IsIndexed](#isindexed)  
  
- [SetColorTable](#setcolortable)  
  
##  <a name="isindexed"></a>  CImage::IsIndexed  
 カラー パレットにビットマップのピクセルを割り当てるかどうかを判断します。  
  
```
bool IsIndexed() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 **true**それ以外のインデックス付き**false**です。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る**true**ビットマップが 8 ビットである場合にのみ (256 色) 以下です。  
  
> [!NOTE]
>  このメソッドには、DIB セクション ビットマップのみがサポートしています。  
  
##  <a name="isnull"></a>  CImage::IsNull  
 ビットマップが現在読み込まれているかどうかを判断します。  
  
```
bool IsNull() const throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る**True**いる場合は、ビットマップそれ以外の読み込まれた**False**です。  
  
##  <a name="istransparencysupported"></a>  CImage::IsTransparencySupported  
 アプリケーションが透明なビットマップをサポートするかどうかを示します。  
  
```
static BOOL IsTransparencySupported() throw();
```  
  
### <a name="return-value"></a>戻り値  
 現在のプラットフォームの透過性をサポートする場合は 0 以外の値。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合は、戻り値は 0 以外の場合、透過性をサポートするへの呼び出し[およびアルファブレンド](#alphablend)、 [TransparentBlt](#transparentblt)、または[描画](#draw)透明色を処理します。  
  

##  <a name="load"></a>  CImage::Load  
 イメージを読み込みます。  
  
```
HRESULT Load(LPCTSTR pszFileName) throw();
HRESULT Load(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFileName`  
 読み込むイメージ ファイルの名前を含む文字列へのポインター。  
  
 `pStream`  
 読み込むイメージ ファイルの名前を格納しているストリームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
### <a name="remarks"></a>コメント  
 指定されたイメージを読み込みます*pszFileName*または`pStream`です。  
  
 有効なイメージの種類は、BMP、GIF、JPEG、PNG、TIFF です。  
  
##  <a name="loadfromresource"></a>  CImage::LoadFromResource  
 イメージを読み込み、`BITMAP`リソース。  
  
```
void LoadFromResource(
 HINSTANCE hInstance,
 LPCTSTR pszResourceName) throw();

void LoadFromResource(
 HINSTANCE hInstance,
 UINT nIDResource) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 読み込まれるイメージが含まれるモジュールのインスタンスへのハンドルします。  
  
 `pszResourceName`  
 読み込む画像が含まれるリソースの名前を含む文字列へのポインター。  
  
 `nIDResource`  
 読み込むリソースの ID。  
  
### <a name="remarks"></a>コメント  
 リソースは、型でなければなりません`BITMAP`です。  
  
##  <a name="maskblt"></a>  CImage::MaskBlt  
 指定したマスクとラスター オペレーションを使用する元とコピー先のビットマップの色のデータを結合します。  
  
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
 `hDestDC`  
 実行可能ファイルがリソースを含むモジュールへのハンドル。  
  
 `xDest`  
 X 座標、先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標を論理単位で、移行先の四角形の左上隅にあるのです。  
  
 `nDestWidth`  
 論理ユニットは、コピー先の四角形と元のビットマップの幅。  
  
 `nDestHeight`  
 論理単位で、対象の四角形と元のビットマップの高さ。  
  
 `xSrc`  
 元のビットマップの左上隅の論理 x 座標。  
  
 `ySrc`  
 元のビットマップの左上隅の論理 y 座標。  
  
 `hbmMask`  
 元のデバイス コンテキストのカラー ビットマップと組み合わせるモノクロのマスク ビットマップへのハンドルします。  
  
 `xMask`  
 指定されたマスク ビットマップのピクセルの水平方向のオフセット、`hbmMask`パラメーター。  
  
 `yMask`  
 指定されたマスク ビットマップのピクセルの垂直オフセット、`hbmMask`パラメーター。  
  
 `dwROP`  
 ソースおよび変換先データの組み合わせを制御するメソッドを使用する前景色と背景の両方の三項ラスター オペレーション コードを指定します。 バック グラウンド ラスター オペレーション コードがこの値の上位ワードの高位バイトに格納されています。フォア グラウンド ラスター オペレーション コードがこの値の上位ワードの下位バイトに格納されています。この値の下位ワードは無視され、0 にする必要があります。 前景色および背景でこのメソッドのコンテキストの詳細については、次を参照してください。 `MaskBlt` Windows SDK に含まれています。 一般的なラスター オペレーション コードの一覧は、次を参照してください。 `BitBlt` Windows SDK に含まれています。  
  
 `rectDest`  
 参照、`RECT`構造体、変換先を識別します。  
  
 `pointSrc`  
 A`POINT`元の四角形の左上隅を示す構造体。  
  
 `pointMask`  
 A**ポイント**マスク ビットマップの左上隅を示す構造体。  
  
 `pointDest`  
 参照、**ポイント**論理単位で、移行先の四角形の左上隅を識別する構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows NT、バージョン 4.0 以降のみに適用されます。  
  
##  <a name="operator_hbitmap"></a>  CImage::operator HBITMAP  
 この演算子のアタッチされた Windows GDI ハンドルの取得を使用して、`CImage`オブジェクト。 この演算子はキャスト演算子の`HBITMAP`オブジェクト。  
  
##  <a name="plgblt"></a>  CImage::PlgBlt  
 コピー先デバイス コンテキストで指定した平行四辺形に元のデバイス コンテキスト内の四角形からのビット ブロック転送を実行します。  
  
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
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 *pPoints*  
 平行四辺形の 3 つの角を識別する論理空間内の次の 3 つの点の配列へのポインター。 元の四角形の左上隅は、この配列、配列内の 2 番目のポイントを右上隅および 3 番目のポイントを左下隅の最初のポイントにマップされます。 元の四角形の右下隅は、暗黙的な 4 番目のポイント、平行四辺形内にマップされます。  
  
 `hbmMask`  
 元の四角形の色をマスクに使用されるオプションのモノクロ ビットマップへのハンドル。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `xMask`  
 モノクロのビットマップの左上隅の x 座標。  
  
 `yMask`  
 モノクロのビットマップの左上隅の y 座標。  
  
 `rectSrc`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体の元の四角形の座標を指定します。  
  
 `pointMask`  
 A[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)マスク ビットマップの左上隅を示す構造体。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 場合`hbmMask`モノクロのビットマップが有効**PlgBit**このビットマップを使用して、元の四角形の色データのビットをマスクします。  
  
 このメソッドは、Windows NT、バージョン 4.0 以降のみに適用されます。 参照してください[PlgBlt](http://msdn.microsoft.com/library/windows/desktop/dd162804)より詳細な情報の Windows SDK に含まれています。  
  
##  <a name="releasedc"></a>  CImage::ReleaseDC  
 デバイス コンテキストを解放します。  
  
```
void ReleaseDC() const throw();
```  
  
### <a name="remarks"></a>コメント  
 デバイス コンテキストに一度に選択できる 1 つだけのビットマップ、呼び出す必要があります`ReleaseDC`呼び出しごとに[GetDC](#getdc)です。  
  
##  <a name="releasegdiplus"></a>  CImage::ReleaseGDIPlus  
 GDI + で使用されるリソースを解放します。  
  
```
void ReleaseGDIPlus() throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すグローバルによって割り当てられたリソースを解放する必要があります`CImage`オブジェクト。 参照してください[CImage::CImage](#cimage)です。  
  
##  <a name="save"></a>  CImage::Save  
 指定したストリームまたはディスク上のファイルにイメージを保存します。  
  
```
HRESULT Save(IStream* pStream,
 REFGUID guidFileType) const throw();

HRESULT Save(LPCTSTR pszFileName,
 REFGUID guidFileType= GUID_NULL) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 ファイル イメージ データを含む COM IStream オブジェクトへのポインター。  
  
 *pszFileName*  
 イメージのファイル名へのポインター。  
  
 `guidFileType`  
 イメージを保存するファイルの種類。 次のいずれかの値を指定します。  
  
- **ImageFormatBMP**圧縮されていないビットマップ イメージです。  
  
- **ImageFormatPNG** A ポータブル ネットワーク グラフィックス (PNG) 圧縮されたイメージ。  
  
- **ImageFormatJPEG** A JPEG 圧縮されたイメージ。  
  
- **ImageFormatGIF** A GIF 圧縮されたイメージ。  
  
> [!NOTE]
>  定数の完全な一覧を参照してください。**イメージ ファイル形式の定数**Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
### <a name="remarks"></a>コメント  
 指定した名前と型を使用してイメージを保存するには、この関数を呼び出します。 場合、`guidFileType`パラメーターが含まれていない、イメージの形式を決定するファイル名の拡張子が使用されます。 拡張機能が指定されていない場合は、bmp ファイル形式にイメージが保存されます。  
  
##  <a name="setcolortable"></a>  CImage::SetColorTable  
 DIB セクションのパレット内のエントリの範囲の赤、緑、青 (RGB) の色値を設定します。  
  
```
void SetColorTable(
  UINT iFirstColor, 
  UINT nColors,
  const RGBQUAD* prgbColors) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iFirstColor`  
 設定する最初のエントリのカラー テーブルのインデックス。  
  
 `nColors`  
 設定するカラー テーブル エントリの数。  
  
 `prgbColors`  
 配列へのポインター [RGBQUAD](http://msdn.microsoft.com/library/windows/desktop/dd162938)テーブル エントリの色を設定する構造体。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、DIB セクション ビットマップのみがサポートしています。  
  
##  <a name="setpixel"></a>  CImage::SetPixel  
 ビットマップ内で特定の場所のピクセルの色を設定します。  
  
```
void SetPixel(int x, int y, COLORREF color) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 設定するピクセルの水平位置です。  
  
 *y*  
 設定するピクセルの垂直方向の位置。  
  
 `color`  
 ピクセルを設定する色です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ピクセルの座標が選択されているクリッピング領域の外にある場合に失敗します。  
  
##  <a name="setpixelindexed"></a>  CImage::SetPixelIndexed  
 ある色にピクセルの色を設定`iIndex`カラー パレットにします。  
  
```
void SetPixelIndexed(int x, int y, int iIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 設定するピクセルの水平位置です。  
  
 *y*  
 設定するピクセルの垂直方向の位置。  
  
 `iIndex`  
 カラー パレットの色のインデックス。  
  
##  <a name="setpixelrgb"></a>  CImage::SetPixelRGB  
 によって指定された場所にあるピクセル設定*x*と*y*で示される色に*r*、 *g*、および*b*、赤、緑、青 (RGB) のイメージです。  
  
```
void SetPixelRGB(  
 int x,
 int y,
 BYTE r,
 BYTE g,
 BYTE b) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 設定するピクセルの水平位置です。  
  
 *y*  
 設定するピクセルの垂直方向の位置。  
  
 *r*  
 赤の色の彩度。  
  
 *g*  
 緑の色の彩度。  
  
 *b*  
 青の色の彩度。  
  
### <a name="remarks"></a>コメント  
 赤、緑、および青のパラメーターは、それぞれ 0 ~ 255 の数値で表されます。 3 つすべてのパラメーターを 0 に設定した場合、色は黒です。 次の 3 つのすべてのパラメーターを 255 に設定した場合、色は白です。  
  
##  <a name="settransparentcolor"></a>  CImage::SetTransparentColor  
 透過的と指定したインデックス位置にある、色を設定します。  
  
```
LONG SetTransparentColor(LONG iTransparentColor) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *iTransparentColor*  
 透過色に設定する色のカラー パレット内のインデックス。 -1 の場合、色が設定されていない透過的です。  
  
### <a name="return-value"></a>戻り値  
 以前の色のインデックスに透明として設定します。  
  
##  <a name="stretchblt"></a>  CImage::StretchBlt  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
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
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 `xDest`  
 X 座標、先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標を論理単位で、移行先の四角形の左上隅にあるのです。  
  
 `nDestWidth`  
 論理ユニットは、先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、先の四角形の高さ。  
  
 `dwROP`  
 実行するラスター オペレーションです。 ラスター オペレーション コードは、変換先を形成する、ソース、変換先、およびパターンのビット (で定義されている、現在選択されているブラシ) を組み合わせる方法を定義します。 参照してください[BitBlt](http://msdn.microsoft.com/library/windows/desktop/dd183370)その他のラスター オペレーション コードとその説明の一覧については Windows SDK に含まれています。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、変換先を識別します。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectSrc`  
 参照、`RECT`構造体、ソースを特定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [StretchBlt](http://msdn.microsoft.com/library/windows/desktop/dd145120) Windows SDK に含まれています。  
  
##  <a name="transparentblt"></a>  CImage::TransparentBlt  
 コピー元デバイス コンテキストから現在のデバイス コンテキストにビットマップをコピーします。  
  
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
 `hDestDC`  
 コピー先デバイス コンテキストへのハンドル。  
  
 `xDest`  
 X 座標、先の四角形の左上隅の論理単位です。  
  
 `yDest`  
 Y 座標を論理単位で、移行先の四角形の左上隅にあるのです。  
  
 `nDestWidth`  
 論理ユニットは、先の四角形の幅。  
  
 `nDestHeight`  
 論理ユニットは、先の四角形の高さ。  
  
 *crTransparent*  
 透明として処理する元のビットマップの色。 既定では、 **CLR_INVALID**、現在は、イメージの透明色として設定する色を使用することを示すです。  
  
 `rectDest`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体、変換先を識別します。  
  
 `xSrc`  
 X 座標、元の四角形の左上隅の論理単位です。  
  
 `ySrc`  
 Y 座標、元の四角形の左上隅の論理単位です。  
  
 `nSrcWidth`  
 論理ユニットは、元の四角形の幅。  
  
 `nSrcHeight`  
 論理ユニットは、元の四角形の高さ。  
  
 `rectSrc`  
 参照、`RECT`構造体、ソースを特定します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**成功した場合、それ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `TransparentBlt` ピクセルあたり 8 ビット、およびピクセルごとの 4 ビットの元のビットマップはサポートされます。 使用して[CImage::AlphaBlend](#alphablend)透過性の 32 ビット/ピクセルのビットマップを指定します。  
  
  
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
 [MMXSwarm サンプル](../../visual-cpp-samples.md)   
 [SimpleImage サンプル](../../visual-cpp-samples.md)   
 [デバイスに依存しないビットマップ](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)[デバイスに依存しないビットマップ](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   









