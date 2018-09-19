---
title: イメージのメニュー (アイコン用イメージ エディターを C++) |Microsoft Docs
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
ms.openlocfilehash: ca37981352ddcef639b3e8ed5bbd00a14f56f126
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700714"
---
# <a name="image-menu-c-image-editor-for-icons"></a>[イメージ] メニュー (アイコン用イメージ エディターを C++)

**イメージ**場合にのみ表示されるメニューで、**イメージ**エディターがアクティブになって、イメージの編集、カラー パレットを管理および設定するためのコマンドがあります**イメージ エディター**ウィンドウオプション。 さらに、デバイスのイメージを使用するためのコマンドは使用可能なアイコンとカーソルを使用する場合です。

- **色の反転**

   色を反転させます。 詳細については、次を参照してください。[選択範囲の色の反転](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)します。

- **[左右反転]**

   イメージまたは選択領域の上下を反転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)します。

- **[上下反転]**

   イメージまたは選択領域の左右を反転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)します。

- **90 度回転します。**

   イメージまたは選択領域を 90 度回転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)します。

- **[色] ウィンドウを表示します。**

   開く、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)で、イメージを使用する色を選択できます。 詳細については、次を参照してください。[色の](../windows/working-with-color-image-editor-for-icons.md)します。

- **選択範囲をブラシとして使用します。**

   イメージの一部からカスタム ブラシを作成できます。 選択内容では、画像の選択範囲の色を分散するカスタム ブラシになります。 ドラッグするパスに沿った選択範囲のコピーが残されます。 緩やかに変化をドラッグする、複数のコピーを作成します。 詳細については、次を参照してください。[カスタム ブラシの作成](../windows/creating-a-custom-brush-image-editor-for-icons.md)です。

- **コピーとアウトラインの選択**

   現在の選択領域のコピーを作成し、その外枠を描画します。 背景色が、現在の選択範囲に含まれている、ことが含まれる場合がある[透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)選択します。

- **色を調整します。**

   開く、[カスタム カラー セレクター](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)イメージを使用する色をカスタマイズできます。 詳細については、次を参照してください。[カスタマイズまたは変更する色](../windows/customizing-or-changing-colors-image-editor-for-icons.md)します。

- **パレットの読み込み**

   開く、[カラー パレットの読み込み ダイアログ ボックス](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)、*.pal ファイルに保存されているパレットをロードできます。

- **パレットを保存します。**

   パレットの色を *.pal ファイルに保存します。

- **不透明なを描画します。**

   選択すると、現在の選択も不透明にします。 オフにすると、現在の選択範囲を透明します。 詳細については、次を参照してください。[を不透明または透明な背景を選択する](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)します。

- **ツール バー エディター**

   開く、[新規ツール バー リソース ダイアログ ボックス](../windows/new-toolbar-resource-dialog-box.md)します。

- **グリッドの設定**

   開く、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md)イメージのグリッドを指定できます。

- **新しいイメージの種類**

   開く、[新規\<デバイス > イメージの種類 ダイアログ ボックス](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)します。 1 つのアイコン リソースがサイズの異なるいくつかのイメージを含めることができます。windows では、表示する方法に応じて適切なアイコンのサイズを使用できます。 新しいデバイスの種類は、アイコンのサイズを変更しませんではなく、アイコン内に新しいイメージを作成します。 アイコンとカーソルにのみ適用されます。

- **現在のアイコンとカーソル イメージ タイプ**

   イメージが一覧表示最初使用可能なカーソルまたはアイコン (最初の 9) のサブメニューが表示されます。 最後のコマンドはサブメニューに**より.**、開く、[オープン\<デバイス > イメージ ダイアログ ボックス](../windows/open-device-image-dialog-box-image-editor-for-icons.md)。

- **イメージ タイプを削除します。**

   選択したデバイスのイメージを削除します。

- **ツール**

   使用可能なすべてのツールを含むサブメニューを起動、[イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)