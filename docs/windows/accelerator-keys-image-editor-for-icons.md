---
title: アクセラレータ キー (アイコン用イメージ エディター) |Microsoft ドキュメント
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
ms.openlocfilehash: f2b19fb16410f7d720d11e8b8560cde4cadf10b1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="accelerator-keys-image-editor-for-icons"></a>アクセラレータ キー (アイコン用イメージ エディター)
次は、既定では、キーにバインドされているイメージ エディターのコマンドをアクセラレータ キーを示します。 アクセラレータ キーを変更する をクリックして**オプション**上、**ツール** メニューを選択し**キーボード**下にある、**環境**フォルダーです。 詳細については、「[Visual Studio でのキーボード ショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」をご覧ください。  
  
> [!NOTE]
>  使用している設定またはエディションによっては、ダイアログ ボックスで使用可能なオプションや、メニュー コマンドの名前や位置がヘルプに記載されている内容と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
|コマンド|キー|説明|  
|-------------|----------|-----------------|  
|Image.AirBrushTool|CTRL キーを押しながら A|選択したサイズと色のエアブラシを使ってを描画します。|  
|Image.BrushTool|CTRL キーを押しながら B|選択した図形、サイズ、および色のブラシを使ってを描画します。|  
|Image.CopyAndOutlineSelection|CTRL キーと SHIFT キーを押しながら U|現在の選択領域のコピーを作成し、その外枠を描画します。 背景色が現在の選択範囲に含まれている場合、除外する必要がある場合[透過的](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)選択します。|  
|Image.DrawOpaque|CTRL キーを押しながら J|現在の選択範囲をいずれかにより、[非透過または透過](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)です。|  
|Image.EllipseTool|CTRL キーを押しながら P|選択した線の幅、色と楕円を描画します。|  
|Image.EraserTool|CTRL + SHIFT + I|(現在の背景色) のイメージの一部を消去します。|  
|Image.FilledEllipseTool|CTRL + SHIFT + ALT + P|塗りつぶされた楕円を描画します。|  
|Image.FilledRectangleTool|CTRL + SHIFT + ALT + R|塗りつぶされた四角形を描画します。|  
|Image.FilledRoundRectangleTool|CTRL + SHIFT + ALT + W|塗りつぶされた角の丸い四角形を描画します。|  
|Image.FillTool|CTRL キーを押しながら F|領域を塗りつぶします。|  
|Image.FlipHorizontal|Ctrl + H|イメージまたは選択領域の上下を反転させます。|  
|Image.FlipVertical|SHIFT + ALT + H|イメージまたは選択領域の左右を反転させます。|  
|Image.LargerBrush|CTRL + =|ブラシのサイズを各方向に 1 ピクセルずつ拡大します。 ブラシのサイズを小さくする方法については、この表の「Image.SmallerBrush」を参照してください。|  
|Image.LineTool|Ctrl + L|選択した形、サイズ、および色で直線を描画します。|  
|Image.MagnificationTool|CTRL キーを押しながら M|アクティブ化、 **Magnify**ツールで、イメージの特定のセクションを拡大することができます。|  
|Image.Magnify|CTRL キーと SHIFT キーを押しながら M|現在の拡大率と 1:1 の間で切り替えます。|  
|Image.NewImageType|INSERT|起動、[新規\<デバイス > イメージの種類 ダイアログ ボックス](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)で別のイメージの種類のイメージを作成できます。|  
|Image.NextColor|CTRL +]<br /><br /> または<br /><br /> CTRL キーを押しながら右矢印|描画の前景色を次のパレット カラーに変更します。|  
|Image.NextRightColor|CTRL キーを押しながら SHIFT キーを押しながら]<br /><br /> または<br /><br /> SHIFT + CTRL + → キー|描画の背景色を次のパレット カラーに変更します。|  
|Image.OutlinedEllipseTool|SHIFT + ALT + P|塗りつぶされた楕円を外枠付きで描画します。|  
|Image.OutlinedRectangleTool|SHIFT + ATL + R|塗りつぶされた四角形を外枠付きで描画します。|  
|Image.OutlinedRoundRectangleTool|SHIFT + ALT + W|塗りつぶされた角の丸い四角形を外枠付きで描画します。|  
|Image.PencilTool|Ctrl + I|1 ピクセルのペンシルを使用して描画します。|  
|Image.PreviousColor|CTRL キーを押しながら [<br /><br /> または<br /><br /> CTRL キーを押しながら左方向キー|描画の前景色を前のパレット カラーに変更します。|  
|Image.PreviousRightColor|CTRL キーと SHIFT キーを押しながら [<br /><br /> または<br /><br /> SHIFT キー CTRL キーを押しながら左方向キー|描画の背景色を前のパレット カラーに変更します。|  
|Image.RectangleSelectionTool|SHIFT + ALT + S|移動、コピー、または編集するイメージの四角形の部分を選択します。|  
|Image.RectangleTool|ATL + R|選択した線の幅および色の四角形を描画します。|  
|Image.Rotate90Degrees|CTRL + SHIFT + H|イメージまたは選択領域を 90 度回転させます。|  
|Image.RoundedRectangleTool|ALT キーを押しながら W|選択した線の幅および色の丸い四角形を描画します。|  
|Image.ShowGrid|CTRL + ALT + S|ピクセル グリッドを切り替えます (オンまたはオフ、**ピクセル グリッド**オプション、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md))。|  
|Image.ShowTileGrid|CTRL + SHIFT + ALT + S|タイルのグリッドを切り替えます (オンまたはオフ、**タイル グリッド**オプション、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md))。|  
|Image.SmallBrush|CTRL + です。 (ピリオド)|削減、**ブラシ**サイズを 1 ピクセルです。 この表の「Image.LargerBrush」と「Image.SmallerBrush」も参照してください。|  
|Image.SmallerBrush|CTRL + - (減算)|ブラシのサイズを各方向に 1 ピクセルずつ縮小します。 ブラシを元のサイズに戻す方法については、この表の「Image.LargerBrush」を参照してください。|  
|Image.TextTool|CTRL + T|開く、[テキスト ツール ダイアログ ボックス](../windows/text-tool-dialog-box-image-editor-for-icons.md)です。|  
|Image.UseSelectionAsBrush|CTRL キーを押しながら U|現在の選択項目をブラシとして使用して描画します。|  
|Image.ZoomIn|CTRL キーを押しながら SHIFT キーを押しながらです。 (ピリオド)<br /><br /> または<br /><br /> CTRL + 上向き矢印|現在のビューの拡大率を上げます。|  
|Image.ZoomOut|CTRL +, (コンマ)<br /><br /> または<br /><br /> CTRL + ↓ キー|現在のビューの拡大率を下げます。|  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

