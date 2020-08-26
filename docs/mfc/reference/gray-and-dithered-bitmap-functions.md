---
title: 淡色表示 (灰色) ビットマップ関数とディザリングされたビットマップ関数
ms.date: 11/19/2018
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
helpviewer_keywords:
- gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
ms.openlocfilehash: 57f163fd36c0f25508d94a84495fcaf1956e277d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837204"
---
# <a name="gray-and-dithered-bitmap-functions"></a>淡色表示 (灰色) ビットマップ関数とディザリングされたビットマップ関数

**淡色表示 (灰色) ビットマップ関数**

MFC には、ビットマップのコントロールが無効になっていることを示すための 2 つの関数が用意されています。

![グレー アイコンと元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "グレー アイコンと元のアイコンの比較")

|名前|説明|
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|灰色のバージョンのビットマップを描画します。|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|灰色のバージョンのビットマップをコピーします。|

**淡色表示 (灰色) ビットマップ関数**

MFC には、ビットマップの背景をディザリングされたパターンに置き換える 2 つの関数も用意されています。

![ディザー アイコンと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "ディザー アイコンと元のアイコンの比較")

|名前|説明|
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|背景がディザリングされたビットマップを描画します。|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|背景がディザリングされたビットマップをコピーします。|

## <a name="afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a> AfxDrawGrayBitmap

灰色のバージョンのビットマップを描画します。

```cpp
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF crBackground);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
宛先 DC を示します。

*x*<br/>
宛先の x 座標。

*y*<br/>
宛先の y 座標。

*.Rsrc*<br/>
元のビットマップ。

*crBackground*<br/>
新しい背景色 (通常は COLOR_MENU などの灰色)。

### <a name="remarks"></a>解説

`AfxDrawGrayBitmap` で描画されるビットマップの外観は、無効なコントロールになります。

![グレー アイコンと元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "グレー アイコンと元のアイコンの比較")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a> AfxGetGrayBitmap

灰色のバージョンのビットマップをコピーします。

```cpp
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>パラメーター

*.Rsrc*<br/>
元のビットマップ。

*pDest*<br/>
コピー先のビットマップ。

*crBackground*<br/>
新しい背景色 (通常は COLOR_MENU などの灰色)。

### <a name="remarks"></a>解説

`AfxGetGrayBitmap` でコピーされるビットマップの外観は、無効なコントロールのようになります。

![グレー アイコンと元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "グレー アイコンと元のアイコンの比較")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a> AfxDrawDitheredBitmap

ビットマップを描画し、背景をディザリングされた (チェッカー) パターンに置き換えます。

```cpp
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,
    int x,
    int y,
    const CBitmap& rSrc,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
宛先 DC を示します。

*x*<br/>
宛先の x 座標。

*y*<br/>
宛先の y 座標。

*.Rsrc*<br/>
元のビットマップ。

*cr1*<br/>
2つのディザーカラーのうちの1つ。通常は白です。

*cr2*<br/>
その他のディザーの色。通常は薄い灰色 (COLOR_MENU) です。

### <a name="remarks"></a>解説

ソースビットマップは、ビットマップの背景を置き換える2色 (*cr1* と *cr2*) のパターンで、宛先 DC 上に描画されます。 ソースビットマップの背景は、そのビットマップの左上隅にあるピクセルの色に一致する、白いピクセルとすべてのピクセルとして定義されます。

![ディザー アイコンと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "ディザー アイコンと元のアイコンの比較")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a> AfxGetDitheredBitmap

ビットマップをコピーし、背景をディザリングされた (チェッカー) パターンに置き換えます。

```cpp
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>パラメーター

*.Rsrc*<br/>
元のビットマップ。

*pDest*<br/>
コピー先のビットマップ。

*cr1*<br/>
2つのディザーカラーのうちの1つ。通常は白です。

*cr2*<br/>
その他のディザーの色。通常は薄い灰色 (COLOR_MENU) です。

### <a name="remarks"></a>解説

ソースビットマップは、ソースビットマップの背景を置き換える2色 (*cr1* と *cr2*) のパターンでコピー先のビットマップにコピーされます。 ソースビットマップの背景は、そのビットマップの左上隅にあるピクセルの色に一致する、白いピクセルとすべてのピクセルとして定義されます。

![ディザー アイコンと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "vcdiruncommand edbitmap")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
