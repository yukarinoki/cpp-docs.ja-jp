---
title: Variant パラメーター型の定数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13820ff4fb07c3743f36ba3ebe33ee56a3a79c7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379861"
---
# <a name="variant-parameter-type-constants"></a>Variant パラメーター型の定数
このトピックでは、Microsoft Foundation Class ライブラリの OLE コントロール クラスで使用するために設計された variant パラメーター型を示す新しい定数を示します。  
  
 クラスの定数の一覧を次に示します。  
  
##  <a name="_mfc_variant_data_constants"></a> Variant データ定数  
  
-   **VTS_COLOR** RGB 色の値を表す 32 ビット整数。  
  
-   **VTS_FONT**へのポインター、**この**OLE フォント オブジェクトのインターフェイスです。  
  
-   **VTS_HANDLE** A Windows ハンドルの値。  
  
-   **VTS_PICTURE**へのポインター、 `IPictureDisp` OLE 画像オブジェクトのインターフェイスです。  
  
-   **VTS_OPTEXCLUSIVE**ラジオ ボタンなどのコントロールのグループで使用するものでは、コントロールで使用される 16 ビット値。 この型は、コントロール内の 1 つの場合がグループにあるをコンテナーに通知を**TRUE**値、その他のすべて必要があります**FALSE**です。  
  
-   **VTS_TRISTATE** 16 ビット符号付き整数が (選択されている、オフになって、使用できない)、3 つの値のいずれかの例を持つことができるプロパティのチェック ボックスを使用します。  
  
-   **VTS_XPOS_HIMETRIC**で x 軸に沿った位置を表すために使用する 32 ビット符号なし整数**HIMETRIC**単位です。  
  
-   **VTS_YPOS_HIMETRIC**で y 軸に沿った位置を表すために使用する 32 ビット符号なし整数**HIMETRIC**単位です。  
  
-   **VTS_XPOS_PIXELS** 32 ビット符号なし整数の x 軸に沿ったピクセル単位での位置を表すために使用します。  
  
-   **VTS_YPOS_PIXELS** 32 ビット符号なし整数の y 軸に沿ったピクセル単位での位置を表すために使用します。  
  
-   **VTS_XSIZE_PIXELS** 32 ビット符号なし整数のピクセル単位で画面オブジェクトの幅を表すために使用します。  
  
-   **VTS_YSIZE_PIXELS** 32 ビット符号なし整数のピクセル単位で画面オブジェクトの高さを表すために使用します。  
  
-   **VTS_XSIZE_HIMETRIC**画面のオブジェクトの幅を表すために使用する 32 ビット符号なし整数**HIMETRIC**単位です。  
  
-   **VTS_YSIZE_HIMETRIC**画面のオブジェクトの高さを表すために使用する 32 ビット符号なし整数**HIMETRIC**単位です。  
  
    > [!NOTE]
    >  追加のバリアント定数が定義されて、すべてのバリアント型の例外を除いて**VTS_FONT**と**VTS_PICTURE**、variant データ co へのポインターを提供します。nstant です。 これらの定数の名前、**付け**`constantname`規則。 たとえば、 **VTS_PCOLOR**へのポインター、 **VTS_COLOR**定数。  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
