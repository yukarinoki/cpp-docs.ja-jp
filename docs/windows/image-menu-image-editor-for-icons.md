---
title: 画像のメニュー (アイコン用イメージ エディター) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- Image menu
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8bfeeda8d358bf3144cd5c3168686561b3586581
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880531"
---
# <a name="image-menu-image-editor-for-icons"></a>[イメージ] メニュー (アイコン用イメージ エディター)
イメージ エディターがアクティブな場合にのみが表示されたら、[イメージ] メニューには、イメージを編集、カラー パレットを管理およびイメージ エディター ウィンドウのオプションを設定するコマンドがあります。 さらに、アイコンとカーソルを使用する場合は、デバイスのイメージを使用するためのコマンドを使用。  
  
 **色を反転します。**  
 色を反転させます。 詳細については、次を参照してください。[選択範囲の色の反転](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)です。  
  
 **[左右反転]**  
 イメージまたは選択領域の上下を反転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)です。  
  
 **[上下反転]**  
 イメージまたは選択領域の左右を反転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)です。  
  
 **90 度回転します。**  
 イメージまたは選択領域を 90 度回転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)です。  
  
 **[色] ウィンドウを表示します。**  
 開く、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)で、イメージに使用する色を選択できます。 詳細については、次を参照してください。[色の](../windows/working-with-color-image-editor-for-icons.md)します。  
  
 **選択内容ブラシとして使用します。**  
 イメージの部分からカスタム ブラシを作成できます。 選択内容では、画像内で選択されている色を分散するカスタム ブラシになります。 選択範囲のコピーは、ドラッグするパスに沿った残されます。 ドラッグするより緩やかに変化は、複数のコピーが行われます。 詳細については、次を参照してください。[カスタム ブラシの作成](../windows/creating-a-custom-brush-image-editor-for-icons.md)です。  
  
 **コピーし、選択範囲をアウトライン**  
 現在の選択領域のコピーを作成し、その外枠を描画します。 背景色が現在の選択範囲に含まれている場合、除外する必要がある場合[透過的](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)選択します。  
  
 **色を調整します。**  
 開く、[カスタム カラー セレクター](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)イメージを使用する色をカスタマイズすることができます。 詳細については、次を参照してください。[のカスタマイズまたは変更する色](../windows/customizing-or-changing-colors-image-editor-for-icons.md)です。  
  
 **パレットの読み込み**  
 開く、[カラー パレットの読み込み ダイアログ ボックス](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)、.pal を付けてファイルに保存されているパレットの読み込みできます。  
  
 **パレットを保存します。**  
 パレットの色を .pal を付けてファイルに保存します。  
  
 **非透過を描画します。**  
 選択すると、現在の選択範囲を不透明です。 オフの場合、現在の選択は、透過的実行します。 詳細については、次を参照してください。[不透明または透明な背景を選択する](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)です。  
  
 **ツール バー エディター**  
 開く、[新規ツールバー ダイアログ ボックス](../windows/new-toolbar-resource-dialog-box.md)です。  
  
 **グリッドの設定**  
 開く、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md)グリッドをイメージを指定できます。  
  
 **新しいイメージの種類**  
 開く、[新規\<デバイス > イメージの種類 ダイアログ ボックス](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)です。 1 つのアイコン リソースがサイズの異なるいくつかのイメージを含めることができます。windows では、表示する方法に応じて適切なアイコン サイズを使用できます。 新しいデバイスの種類は、アイコンのサイズを変更しませんではなくアイコンに新しいイメージを作成します。 アイコンとカーソルにのみ適用されます。  
  
 **現在のアイコンとカーソル イメージ タイプ**  
 サブメニューのイメージが一覧表示最初使用可能なカーソルまたはアイコン (最初の 9) を開きます。 サブメニューの場合の最後のコマンド**よりしています.**、開く、[開く\<デバイス > イメージ ダイアログ ボックス](../windows/open-device-image-dialog-box-image-editor-for-icons.md)です。  
  
 **イメージの種類を削除します。**  
 選択したデバイスのイメージを削除します。  
  
 **ツール**  
 使用できるすべてのツールを含むサブメニューを起動、[イメージ エディター ツールバー](../windows/toolbar-image-editor-for-icons.md)です。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

