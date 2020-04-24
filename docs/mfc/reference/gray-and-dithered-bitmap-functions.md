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
ms.openlocfilehash: a220596b880ee74d5f9ebf683d087156224ee7c5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751482"
---
# <a name="gray-and-dithered-bitmap-functions"></a>淡色表示 (灰色) ビットマップ関数とディザリングされたビットマップ関数

**淡色表示 (灰色) ビットマップ関数**

MFC には、ビットマップのコントロールが無効になっていることを示すための 2 つの関数が用意されています。

![グレー アイコンと元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "グレー アイコンと元のアイコンの比較")

|||
|-|-|
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|灰色のバージョンのビットマップを描画します。|
|[AfxGetGrayBitmap](#afxgetgraybitmap)|灰色のバージョンのビットマップをコピーします。|

**淡色表示 (灰色) ビットマップ関数**

MFC には、ビットマップの背景をディザリングされたパターンに置き換える 2 つの関数も用意されています。

![ディザー アイコンと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "ディザー アイコンと元のアイコンの比較")

|||
|-|-|
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|背景がディザリングされたビットマップを描画します。|
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|背景がディザリングされたビットマップをコピーします。|

## <a name="afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a>Afxドローグレイビットマップ

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

*Y*<br/>
宛先の y 座標。

*rSrc*<br/>
元のビットマップ。

*cr背景*<br/>
新しい背景色 (通常は COLOR_MENU などの灰色)。

### <a name="remarks"></a>解説

`AfxDrawGrayBitmap` で描画されるビットマップの外観は、無効なコントロールになります。

![グレー アイコンと元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "グレー アイコンと元のアイコンの比較")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a>ビットマップ

灰色のバージョンのビットマップをコピーします。

```cpp
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF crBackground);
```

### <a name="parameters"></a>パラメーター

*rSrc*<br/>
元のビットマップ。

*pDest*<br/>
コピー先のビットマップ。

*cr背景*<br/>
新しい背景色 (通常は COLOR_MENU などの灰色)。

### <a name="remarks"></a>解説

`AfxGetGrayBitmap` でコピーされるビットマップの外観は、無効なコントロールのようになります。

![グレー アイコンと元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "グレー アイコンと元のアイコンの比較")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a>ビットマップを描画します。

ビットマップを描画し、背景をディザ (チェッカ) パターンに置き換えます。

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

*Y*<br/>
宛先の y 座標。

*rSrc*<br/>
元のビットマップ。

*cr1*<br/>
2 つのディザ カラーのうちの 1 つ(通常は白)。

*cr2*<br/>
他のディザ カラーは、通常は明るいグレー (COLOR_MENU)。

### <a name="remarks"></a>解説

ソース ビットマップは、ビットマップの背景を置き換える 2 色 (*cr1*および*cr2*) のチェッカー パターンで、ターゲット DC に描画されます。 ソース ビットマップの背景は、白いピクセルと、ビットマップの左上隅のピクセルの色に一致するすべてのピクセルとして定義されます。

![ディザー アイコンと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "ディザー アイコンと元のアイコンの比較")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a>ビットマップ

ビットマップをコピーし、背景をディザ(チェッカ)パターンに置き換えます。

```cpp
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,
    CBitmap* pDest,
    COLORREF cr1  ,
    COLORREF cr2);
```

### <a name="parameters"></a>パラメーター

*rSrc*<br/>
元のビットマップ。

*pDest*<br/>
コピー先のビットマップ。

*cr1*<br/>
2 つのディザ カラーのうちの 1 つ(通常は白)。

*cr2*<br/>
他のディザ カラーは、通常は明るいグレー (COLOR_MENU)。

### <a name="remarks"></a>解説

ソース ビットマップの背景を置き換える 2 色 (*cr1*と*cr2*) のチェッカー パターンを使用して、コピー先のビットマップにコピーされます。 ソース ビットマップの背景は、白いピクセルと、ビットマップの左上隅のピクセルの色に一致するすべてのピクセルとして定義されます。

![ディザー アイコンと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "ビットマップ")

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
