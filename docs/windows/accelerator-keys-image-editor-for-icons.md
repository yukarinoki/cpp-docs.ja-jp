---
title: アクセラレータ キー (アイコン用イメージ エディター) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f211b15134ad292c9e7e4d3ed92d81ea59dd3b86
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683301"
---
# <a name="accelerator-keys-image-editor-for-icons"></a>アクセラレータ キー (アイコン用イメージ エディター)

既定では、キーにバインドされているイメージ エディターのコマンドをアクセラレータ キーを以下に示します。 アクセラレータ キーを変更するには、次のようにクリックします。**オプション**上、**ツール**] メニューの [選び、**キーボード**下、**環境**フォルダー。 詳細については、「[Visual Studio でのキーボード ショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」をご覧ください。

> [!NOTE]
> 使用している設定またはエディションによっては、ダイアログ ボックスで使用可能なオプションや、メニュー コマンドの名前や位置がヘルプに記載されている内容と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。

|コマンド|キー|説明|
|-------------|----------|-----------------|
|Image.AirBrushTool|**Ctrl**  +  **A**|選択したサイズと色のエアブラシを使用して描画します。|
|Image.BrushTool|**Ctrl キーを押し** + **B**|選択した図形、サイズ、色とブラシを使用して描画します。|
|Image.CopyAndOutlineSelection|**Ctrl キーを押し** + **Shift** + **U**|現在の選択領域のコピーを作成し、その外枠を描画します。 背景色が、現在の選択範囲に含まれている、ことが含まれる場合がある[透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)選択します。|
|Image.DrawOpaque|**Ctrl**  +  **J**|現在の選択範囲をいずれかにより、[非透過または透過](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)します。|
|Image.EllipseTool|**Ctrl**  +  **P**|選択した線の幅と色を使用して楕円を描画します。|
|Image.EraserTool|**Ctrl**  +  **Shift**  +  **I**|(現在の背景色) のイメージの一部を消去します。|
|Image.FilledEllipseTool|**Ctrl キーを押し** + **Shift** + **Alt** + **P**|塗りつぶされた楕円を描画します。|
|Image.FilledRectangleTool|**Ctrl キーを押し** + **Shift** + **Alt** + **R**|塗りつぶされた四角形を描画します。|
|Image.FilledRoundRectangleTool|**Ctrl キーを押し** + **Shift** + **Alt** + **W**|塗りつぶされた角の丸い四角形を描画します。|
|Image.FillTool|**Ctrl**  +  **F**|領域を塗りつぶします。|
|Image.FlipHorizontal|**Ctrl**  +  **H**|イメージまたは選択領域の上下を反転させます。|
|Image.FlipVertical|**Shift キーを押し**+ **Alt** + **H**|イメージまたは選択領域の左右を反転させます。|
|Image.LargerBrush|**Ctrl キー** + **=**|ブラシのサイズを各方向に 1 ピクセルずつ拡大します。 ブラシのサイズを小さくする方法については、この表の「Image.SmallerBrush」を参照してください。|
|Image.LineTool|**Ctrl**  +  **L**|選択した形、サイズ、および色で直線を描画します。|
|Image.MagnificationTool|**Ctrl キーを押し** + **M**|アクティブ化、**拡大**ツールで、イメージの特定のセクションを拡大することができます。|
|Image.Magnify|**Ctrl**  +  **Shift**  +  **M**|現在の拡大率と 1:1 の間で切り替えます。|
|Image.NewImageType|**[挿入]**|起動、[新規\<デバイス > イメージの種類 ダイアログ ボックス](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)で別のイメージ タイプのイメージを作成できます。|
|Image.NextColor|**Ctrl**  +  **]**<br /><br /> または<br /><br /> **Ctrl キーを押し** + **右向き矢印**|描画の前景色を次のパレット カラーに変更します。|
|Image.NextRightColor|**Ctrl**  +  **Shift**  +  **]**<br /><br /> または<br /><br /> **Shift キーを押し** + **Ctrl** + **右向き矢印**|描画の背景色を次のパレット カラーに変更します。|
|Image.OutlinedEllipseTool|**Shift キーを押し** + **Alt** + **P**|塗りつぶされた楕円を外枠付きで描画します。|
|Image.OutlinedRectangleTool|**Shift キーを押し** + **Alt** + **R**|塗りつぶされた四角形を外枠付きで描画します。|
|Image.OutlinedRoundRectangleTool|**Shift キーを押し** + **Alt** + **W**|塗りつぶされた角の丸い四角形を外枠付きで描画します。|
|Image.PencilTool|**Ctrl**  +  **I**|1 ピクセルのペンシルを使用して描画します。|
|Image.PreviousColor|**Ctrl**  +  **[**<br /><br /> または<br /><br /> **Ctrl キーを押し** + **左向き矢印**|描画の前景色を前のパレット カラーに変更します。|
|Image.PreviousRightColor|**Ctrl**  +  **Shift**  +  **[**<br /><br /> または<br /><br /> **Shift キーを押し** + **Ctrl** + **左向き矢印**|描画の背景色を前のパレット カラーに変更します。|
|Image.RectangleSelectionTool|**Shift キーを押し** + **Alt** + **S**|移動、コピー、または編集するイメージの四角形の部分を選択します。|
|Image.RectangleTool|ATL + R|選択した線の幅と色で四角形を描画します。|
|Image.Rotate90Degrees|**Ctrl**  +  **Shift**  +  **H**|イメージまたは選択領域を 90 度回転させます。|
|Image.RoundedRectangleTool|**Alt** + **W**|選択した線の幅と色で丸い四角形を描画します。|
|Image.ShowGrid|**Ctrl キーを押し** + **Alt** + **S**|ピクセル グリッドを切り替えます (オンまたはオフ、**ピクセル グリッド**オプション、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md))。|
|Image.ShowTileGrid|**Ctrl キーを押し** + **Shift** + **Alt** + **S**|タイル グリッドを切り替えます (オンまたはオフ、**タイル グリッド**オプション、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md))。|
|Image.SmallBrush|**Ctrl** + **.** (ピリオド)|削減、**ブラシ**サイズを 1 ピクセルです。 この表の「Image.LargerBrush」と「Image.SmallerBrush」も参照してください。|
|Image.SmallerBrush|**Ctrl キーを押し** +  **-** (負符号)|ブラシのサイズを各方向に 1 ピクセルずつ縮小します。 ブラシを元のサイズに戻す方法については、この表の「Image.LargerBrush」を参照してください。|
|Image.TextTool|**Ctrl**  +  **T**|開く、[テキスト ツール ダイアログ ボックス](../windows/text-tool-dialog-box-image-editor-for-icons.md)します。|
|Image.UseSelectionAsBrush|**Ctrl キーを押し** + **U**|現在の選択項目をブラシとして使用して描画します。|
|Image.ZoomIn|**Ctrl キーを押し** + **Shift** + **します。** (ピリオド)<br /><br /> または<br /><br /> **Ctrl キーを押し** + **上向きの矢印**|現在のビューの拡大率を上げます。|
|Image.ZoomOut|**Ctrl キーを押し** + **、** (コンマ)<br /><br /> または<br /><br /> **Ctrl キーを押し** + **下矢印をクリック**|現在のビューの拡大率を下げます。|

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)