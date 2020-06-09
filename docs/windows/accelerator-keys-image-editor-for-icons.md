---
title: アクセラレータキー (アイコン用 C++ イメージエディター)
ms.date: 02/15/2019
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
ms.openlocfilehash: 0f54b244526bbda878dd75b0e1ca97a89d680ea6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622004"
---
# <a name="accelerator-keys-c-image-editor-for-icons"></a>アクセラレータキー (アイコン用 C++ イメージエディター)

次に示すのは、既定でキーにバインドされるイメージエディターコマンドのアクセラレータキーです。 アクセラレータキーを変更するには、[メニュー**ツール**] [オプション] に移動し、  >  **Options** [**環境**] フォルダーの下の [**キーボード**] を選択します。 詳細については、「[Visual Studio でのキーボード ショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」をご覧ください。

> [!NOTE]
> 使用している設定またはエディションによっては、ダイアログ ボックスで使用可能なオプションや、メニュー コマンドの名前や位置がヘルプに記載されている内容と異なる場合があります。 設定を変更するには、[メニュー**ツール**] [  >  **設定のインポートとエクスポート**] に移動します。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

|コマンド|キー|説明|
|-------------|----------|-----------------|
|AirBrushTool|**Ctrl**  + **A**|選択したサイズと色でエアブラシを使用して描画します。|
|Image.BrushTool|**Ctrl**  + **B**|選択された図形、サイズ、および色でブラシを使用して描画します。|
|CopyAndOutlineSelection|**Ctrl**  + **Shift**  + **U**|現在の選択領域のコピーを作成し、その外枠を描画します。 背景色が現在の選択範囲に含まれている場合は、[透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)になっている場合は除外されます。|
|Image.DrawOpaque|**Ctrl**  + **J**|現在の選択範囲を[不透明または透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)にします。|
|Image.EllipseTool|**Ctrl**  + **P**|選択した線の幅と色で楕円を描画します。|
|EraserTool|**Ctrl**  + **Shift**  + **I**|イメージの一部を (現在の背景色で) 消去します。|
|Image.FilledEllipseTool|**Ctrl**  + **Shift**  + **Alt**  + **P**|塗りつぶされた楕円を描画します。|
|Image.FilledRectangleTool|**Ctrl**  + **Shift**  + **Alt**  + **R**|塗りつぶされた四角形を描画します。|
|FilledRoundRectangleTool|**Ctrl**  + **Shift**  + **Alt**  + **W**|塗りつぶされた角の丸い四角形を描画します。|
|Image.FillTool|**Ctrl**  + **F**|領域を塗りつぶします。|
|Image.FlipHorizontal|**Ctrl**  + **H**|イメージまたは選択領域の上下を反転させます。|
|Image.FlipVertical|**Shift** + **Alt**  + **H**|イメージまたは選択領域の左右を反転させます。|
|Image.LargerBrush|**+** + **=**|ブラシのサイズを各方向に 1 ピクセルずつ拡大します。 ブラシのサイズを小さくする方法については、この表の「Image.SmallerBrush」を参照してください。|
|Image.LineTool|**Ctrl**  + **L**|選択した形、サイズ、および色で直線を描画します。|
|Image.MagnificationTool|**Ctrl**  + **M**|[**拡大**] ツールをアクティブにします。これにより、イメージの特定のセクションを拡大できます。|
|Image.Magnify|**Ctrl** + **Shift** + **M**|現在の拡大率と 1:1 の間で切り替えます。|
|Image.NewImageType|**挿入**|[[新しい \<Device> イメージの種類] ダイアログボックス](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)を開きます。このダイアログボックスでは、別のイメージの種類のイメージを作成できます。|
|Image.NextColor|**Ctrl**  + **]**<br /><br /> または<br /><br /> **Ctrl**  + **右方向キー**|描画の前景色を次のパレット カラーに変更します。|
|Image.NextRightColor|**Ctrl**  + **Shift**  + **]**<br /><br /> または<br /><br /> **Shift**  + **Ctrl**  + **右方向キー**|描画の背景色を次のパレット カラーに変更します。|
|Image.OutlinedEllipseTool|**Shift**  + **Alt**  + **P**|塗りつぶされた楕円を外枠付きで描画します。|
|Image.OutlinedRectangleTool|**Shift**  + **Alt**  + **R**|塗りつぶされた四角形を外枠付きで描画します。|
|OutlinedRoundRectangleTool|**Shift**  + **Alt**  + **W**|塗りつぶされた角の丸い四角形を外枠付きで描画します。|
|Image.PencilTool|**Ctrl**  + **I**|1 ピクセルのペンシルを使用して描画します。|
|Image.PreviousColor|**Ctrl**  + **[**<br /><br /> または<br /><br /> **Ctrl**  + **左方向キー**|描画の前景色を前のパレット カラーに変更します。|
|Image.PreviousRightColor|**Ctrl**  + **Shift**  + **[**<br /><br /> または<br /><br /> **Shift**  + **Ctrl**  + **左方向キー**|描画の背景色を前のパレット カラーに変更します。|
|Image.RectangleSelectionTool|**Shift**  + **Alt**  + **S**|イメージの四角形の部分を選択して、移動、コピー、または編集します。|
|Image.RectangleTool|ATL + R|選択した線の幅と色で四角形を描画します。|
|Image.Rotate90Degrees|**Ctrl**  + **Shift**  + **H**|イメージまたは選択領域を 90 度回転させます。|
|Image.RoundedRectangleTool|**Alt**  + **W**|選択した線の幅と色で丸い四角形を描画します。|
|Image.ShowGrid|**Ctrl**  + **Alt**  + **S**|ピクセルグリッドを切り替えます ([[グリッドの設定] ダイアログボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md)の [**ピクセルグリッド**] オプションをオンまたはオフにします)。|
|Image.ShowTileGrid|**Ctrl**  + **Shift**  + **Alt**  + **S**|タイルグリッドを切り替えます ([[グリッドの設定] ダイアログボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md)の [**タイルグリッド**] オプションをオンまたはオフにします)。|
|Image.SmallBrush|**Ctrl**  + **.** (ピリオド) に変更します|**ブラシ**のサイズを1ピクセルに縮小します。 この表の「Image.LargerBrush」と「Image.SmallerBrush」も参照してください。|
|Image.SmallerBrush|**Ctrl**  +  Ctrl **-** 除く|ブラシのサイズを各方向に 1 ピクセルずつ縮小します。 ブラシを元のサイズに戻す方法については、この表の「Image.LargerBrush」を参照してください。|
|Image.TextTool|**Ctrl**  + **T**|[[テキストツール] ダイアログボックス](../windows/text-tool-dialog-box-image-editor-for-icons.md)を開きます。|
|Image. UseSelectionAsBrush|**Ctrl**  + **U**|現在の選択項目をブラシとして使用して描画します。|
|Image.ZoomIn|**Ctrl**  + **Shift**  + **.** (ピリオド) に変更します<br /><br /> または<br /><br /> **Ctrl**  + **上矢印**|現在のビューの拡大率を上げます。|
|Image.ZoomOut|**Ctrl**  + **、** (コンマ)<br /><br /> または<br /><br /> **Ctrl**  + **下方向キー**|現在のビューの拡大率を下げます。|

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アイコン用イメージエディター](image-editor-for-icons.md)<br/>
[方法: アイコンまたはその他のイメージを作成する](creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[方法: イメージを編集する](selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[方法: 描画ツールを使用する](using-a-drawing-tool-image-editor-for-icons.md)<br/>
[方法: 色を操作する](working-with-color-image-editor-for-icons.md)<br/>
