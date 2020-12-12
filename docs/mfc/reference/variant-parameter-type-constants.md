---
description: '詳細: バリアント型パラメーター型の定数'
title: Variant パラメーター型の定数
ms.date: 11/04/2016
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant [MFC]
- VTS_FONT constant [MFC]
- VTS_XPOS_PIXELS constant [MFC]
- VTS_COLOR constant [MFC]
- Variants [MFC]
- VTS_YPOS_PIXELS constant [MFC]
- VTS_YSIZE_HIMETRIC constant [MFC]
- VTS_YPOS_HIMETRIC constant [MFC]
- Variants, parameter type constants
- Variant data constants [MFC]
- VTS_PICTURE constant [MFC]
- VTS_TRISTATE constant [MFC]
- VTS_XSIZE_HIMETRIC constant [MFC]
- VTS_HANDLE constant [MFC]
- VTS_XSIZE_PIXELS constant [MFC]
- VTS_OPTEXCLUSIVE constant [MFC]
- VTS_YSIZE_PIXELS constant [MFC]
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
ms.openlocfilehash: 5bc3dcc8a0a888b21b88700db99b05c0f12a4c5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218499"
---
# <a name="variant-parameter-type-constants"></a>Variant パラメーター型の定数

このトピックでは、Microsoft Foundation Class ライブラリの OLE コントロールクラスで使用するように設計されたバリアント型パラメーターの型を示す新しい定数を示します。

クラス定数の一覧を次に示します。

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a> バリアントデータ定数

- RGB カラー値を表すために使用される32ビット整数を VTS_COLOR します。

- `IFontDisp`OLE フォントオブジェクトのインターフェイスへのポインターを VTS_FONT します。

- Windows ハンドル値を VTS_HANDLE します。

- `IPictureDisp`OLE ピクチャオブジェクトのインターフェイスへのポインターを VTS_PICTURE します。

- オプションボタンなど、コントロールのグループで使用することを意図したコントロールに使用される16ビット値 VTS_OPTEXCLUSIVE ます。 この型は、グループ内の1つのコントロールに真の値がある場合は、それ以外はすべて FALSE であることをコンテナーに指示します。

- 有効な3つの値のいずれかを持つことができるプロパティに使用される16ビット符号付き整数を VTS_TRISTATE します (選択、クリア、使用不可)。たとえば、チェックボックスなどです。

- HIMETRIC 単位の x 軸に沿った位置を表すために使用される32ビット符号なし整数 VTS_XPOS_HIMETRIC ます。

- HIMETRIC 単位の y 軸に沿った位置を表すために使用される32ビット符号なし整数 VTS_YPOS_HIMETRIC ます。

- X 軸に沿った位置をピクセル単位で表すために使用される32ビット符号なし整数 VTS_XPOS_PIXELS ます。

- Y 軸に沿った位置をピクセル単位で表すために使用される32ビット符号なし整数を VTS_YPOS_PIXELS します。

- 画面オブジェクトの幅をピクセル単位で表すために使用される32ビット符号なし整数を VTS_XSIZE_PIXELS します。

- 画面オブジェクトの高さをピクセル単位で表すために使用される32ビット符号なし整数を VTS_YSIZE_PIXELS します。

- HIMETRIC 単位での画面オブジェクトの幅を表すために使用される32ビット符号なし整数 VTS_XSIZE_HIMETRIC ます。

- HIMETRIC 単位での画面オブジェクトの高さを表すために使用される32ビット符号なし整数 VTS_YSIZE_HIMETRIC ます。

    > [!NOTE]
    >  Variant データ定数へのポインターを提供する VTS_FONT および VTS_PICTURE を除き、すべてのバリアント型に対して追加のバリアント定数が定義されています。 これらの定数には、VTS_P 規約を使用して名前が付けられ `constantname` ます。 たとえば、VTS_PCOLOR は VTS_COLOR 定数へのポインターです。

## <a name="requirements"></a>要件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
