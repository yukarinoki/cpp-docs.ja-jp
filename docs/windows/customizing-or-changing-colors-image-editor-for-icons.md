---
title: カスタマイズまたは変更 (アイコン用イメージ エディター) の色 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
ms.assetid: e58f6b32-f435-4d9a-a570-7569433661ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6927ce218c862329e1669aaa1a42316cab68ec86
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317382"
---
# <a name="customizing-or-changing-colors-image-editor-for-icons"></a>色のカスタマイズまたは変更 (アイコン用イメージ エディター)

**イメージ**エディターの[色パレット](../windows/colors-window-image-editor-for-icons.md)16 の標準色を最初に表示されます。 表示された色以外にも、独自の色を作成できます。 できます[を保存し、カスタマイズした色パレットを読み込む](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)します。

### <a name="to-change-colors-on-the-colors-palette"></a>色パレットで色を変更するには

1. **イメージ**] メニューの [選択**色の調整**します。

2. [カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)、RGB または HSL 値を適切なテキスト ボックスに入力して、色を定義またはで色を選択、**グラデーション色の表示**ボックス。

3. スライダーを移動して、輝度を設定、**光度**バー。

4. 作成した色の多くは、ディザリングされます。 ダブルクリックして、単色をディザリングされた色に最も近いする場合、**色**ボックス。

   後で、ディザリングされた色をする場合、スライダーを移動、**光度**バーまたは十字カーソルを移動、**グラデーション色の表示**ボックスに、ディザリングを復元します。

5. クリックして**OK**新しい色を追加します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
[カラーを使用します。](../windows/working-with-color-image-editor-for-icons.md)