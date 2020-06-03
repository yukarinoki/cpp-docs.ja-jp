---
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
ms.openlocfilehash: f73c72830216679f8a91d0037d48c1e1b8e400c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372864"
---
# <a name="variant-parameter-type-constants"></a>Variant パラメーター型の定数

このトピックでは、Microsoft Foundation クラス ライブラリの OLE コントロール クラスで使用するように設計されたバリアント パラメーター型を示す新しい定数を示します。

クラス定数の一覧を次に示します。

## <a name="variant-data-constants"></a><a name="_mfc_variant_data_constants"></a>バリアント データ定数

- VTS_COLOR RGB カラー値を表すために使用される 32 ビット整数。

- VTS_FONT OLE フォント`IFontDisp`オブジェクトのインターフェイスへのポインター。

- VTS_HANDLE ウィンドウ ハンドルの値です。

- VTS_PICTURE OLE ピクチャ`IPictureDisp`オブジェクトのインターフェイスへのポインター。

- VTS_OPTEXCLUSIVEラジオ ボタンなどのコントロールのグループで使用するコントロールに使用される 16 ビット値。 この型は、グループ内の 1 つのコントロールに TRUE 値がある場合、他のコントロールはすべて FALSE にする必要があることをコンテナーに指示します。

- VTS_TRISTATE チェック ボックスなど、3 つの値 (選択済み、選択解除、使用不可) のいずれかを持つことができるプロパティに使用される 16 ビット符号付き整数。

- VTS_XPOS_HIMETRIC HIMETRIC 単位で x 軸に沿った位置を表すために使用される 32 ビット符号なし整数。

- VTS_YPOS_HIMETRIC HIMETRIC 単位で y 軸に沿った位置を表すために使用される 32 ビット符号なし整数。

- VTS_XPOS_PIXELS x 軸に沿った位置をピクセル単位で表すために使用される 32 ビット符号なし整数。

- VTS_YPOS_PIXELS y 軸に沿った位置をピクセル単位で表すために使用される 32 ビット符号なし整数。

- VTS_XSIZE_PIXELS画面オブジェクトの幅をピクセル単位で表すために使用される 32 ビット符号なし整数。

- VTS_YSIZE_PIXELS画面オブジェクトの高さをピクセル単位で表すために使用される 32 ビット符号なし整数。

- VTS_XSIZE_HIMETRIC HIMETRIC 単位で画面オブジェクトの幅を表すために使用される 32 ビット符号なし整数。

- VTS_YSIZE_HIMETRIC HIMETRIC 単位で画面オブジェクトの高さを表すために使用される 32 ビット符号なし整数。

    > [!NOTE]
    >  すべてのバリアント型に対して、バリアント型のデータ定数へのポインターを提供するVTS_FONTとVTS_PICTUREを除く、追加のバリアント定数が定義されています。 これらの定数は、VTS_P`constantname`の規則を使用して名前が付けられます。 たとえば、VTS_PCOLORはVTS_COLOR定数へのポインターです。

## <a name="requirements"></a>必要条件

**ヘッダー :** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
