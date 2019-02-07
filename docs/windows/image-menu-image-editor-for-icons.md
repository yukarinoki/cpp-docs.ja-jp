---
title: '[イメージ] メニュー (アイコン用イメージ エディターを C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.dialog.GridSettings
- vc.editors.gridsettings
helpviewer_keywords:
- Image menu
- Grid Settings dialog box [C++]
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
ms.openlocfilehash: e7d7d92401d5910cbb8aba8ab4c6000eca45cb01
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849731"
---
# <a name="image-menu-c-image-editor-for-icons"></a>[イメージ] メニュー (アイコン用イメージ エディターを C++)

**イメージ**場合にのみ表示されるメニューで、**イメージ**エディターがアクティブになって、イメージの編集、カラー パレットを管理および設定するためのコマンドがあります**イメージ エディター**ウィンドウオプション。 また、デバイスのイメージを使用するためのコマンドは使用可能なアイコンとカーソルを使用する場合です。

|コマンド|説明|
|---|---|
|**色の反転**|色を反転させます。 詳細については、次を参照してください。[選択範囲の色の反転](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)します。|
|**[左右反転]**|イメージまたは選択領域の上下を反転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)します。|
|**[上下反転]**|イメージまたは選択領域の左右を反転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)します。|
|**90 度回転します。**|イメージまたは選択領域を 90 度回転させます。 詳細については、次を参照してください。[イメージの回転](../windows/flipping-an-image-image-editor-for-icons.md)します。|
|**[色] ウィンドウを表示します。**|開く、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)で、イメージを使用する色を選択できます。 詳細については、次を参照してください。[色の](../windows/working-with-color-image-editor-for-icons.md)します。|
|**選択範囲をブラシとして使用します。**|イメージの一部からカスタム ブラシを作成できます。 選択内容では、画像の選択範囲の色を分散するカスタム ブラシになります。 ドラッグするパスに沿った選択範囲のコピーが残されます。 緩やかに変化をドラッグする、複数のコピーを作成します。 詳細については、次を参照してください。[カスタム ブラシの作成](../windows/creating-a-custom-brush-image-editor-for-icons.md)です。|
|**コピーとアウトラインの選択**|現在の選択領域のコピーを作成し、その外枠を描画します。 背景色が、現在の選択範囲に含まれている、それが含まれる場合した[透過的な](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)選択します。
|**色を調整します。**|開く、[カスタム カラー セレクター](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)イメージを使用する色をカスタマイズできます。 詳細については、次を参照してください。[カスタマイズまたは変更する色](../windows/customizing-or-changing-colors-image-editor-for-icons.md)します。|
|**パレットの読み込み**|開く、[カラー パレットの読み込み ダイアログ ボックス](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)、*.pal ファイルに保存されているパレットをロードできます。|
|**パレットを保存します。**|パレットの色を *.pal ファイルに保存します。|
|**不透明なを描画します。**|選択すると、現在の選択も不透明にします。 オフにすると、現在の選択範囲を透明します。 詳細については、次を参照してください。[を不透明または透明な背景を選択する](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)します。|
|**ツール バー エディター**|開く、[新規ツール バー リソース ダイアログ ボックス](../windows/new-toolbar-resource-dialog-box.md)します。|
|**グリッドの設定**|開く、**グリッドの設定** ダイアログ ボックスのグリッドをイメージを指定できます。|
|**新しいイメージの種類**|開く、[新規\<デバイス > イメージの種類 ダイアログ ボックス](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)します。 1 つのアイコン リソースはさまざまなサイズのいくつかのイメージを含めることができ、windows に表示する方法に応じて適切なアイコンのサイズを使用します。 新しいデバイスの種類は、アイコンのサイズは変更されませんではなく、アイコン内に新しいイメージを作成します。 アイコンとカーソルにのみ適用されます。|
|**現在のアイコンとカーソル イメージ タイプ**|イメージが一覧表示最初使用可能なカーソルまたはアイコン (最初の 9) のサブメニューが表示されます。 最後のコマンドはサブメニューに**より.**、開く、[オープン\<デバイス > イメージ ダイアログ ボックス](../windows/open-device-image-dialog-box-image-editor-for-icons.md)。|
|**イメージ タイプを削除します。**|選択したデバイスのイメージを削除します。|
|**ツール**|使用可能なすべてのツールを含むサブメニューを起動、[イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md)します。|

**グリッド設定** ダイアログ ボックス、イメージのグリッドの設定を指定することができ、編集済み画像の上のグリッド線を表示します。 行は、イメージを編集するために便利ですが、イメージ自体の一部としては保存されません。

|プロパティ|説明|
|---|---|
|**ピクセル グリッド**|選択した場合、イメージ エディターの各ピクセルの周りのグリッドを表示します。 4 × とより高い解像度にのみ、グリッドが表示されます。|
|**タイル グリッド**|選択すると、イメージ エディターのグリッドの間隔の値で指定されたピクセルのブロックを囲むグリッドが表示されます。|
|**Width**|各タイルのブロックの幅を指定します。 このプロパティは、一定の間隔で配置された複数のイメージを含むビットマップを描画するときに便利です。|
|**Height**|各タイルのブロックの高さを指定します。 このプロパティは、一定の間隔で配置された複数のイメージを含むビットマップを描画するときに便利です。|

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[イメージのサイズ変更](../windows/resizing-an-image-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)