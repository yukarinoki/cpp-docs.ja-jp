---
title: 色の調整 (アイコン用イメージ エディター)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.color
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
ms.openlocfilehash: 7103332d0b7c0f4756da9526290cabb79544617d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610705"
---
# <a name="working-with-color-image-editor-for-icons"></a>色の調整 (アイコン用イメージ エディター)

**イメージ エディター**具体的には、処理し、色をカスタマイズする多くの機能が含まれています。 前景色または背景色を設定する、境界付けられた領域を塗りつぶす色、または現在の前景色または背景色として使用するイメージの色を選択できます。 ツールを使用することができます、[イメージ エディターのツールバー](../windows/toolbar-image-editor-for-icons.md)のカラー パレットをと共に、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)イメージを作成します。

モノクロと 16 色のイメージのすべての色に表示されます、**色**パレットで、**色**ウィンドウ。 標準の 16 色だけでなく、独自のカスタム色を作成できます。 パレットの色を変更すると、イメージ内の対応する色がすぐに変更します。

256 色のアイコンやカーソルのイメージを使用する場合、**色**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)使用されます。 詳細については、次を参照してください。 [256 色のアイコンまたはカーソルの作成](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)です。

> [!NOTE]
> 使用して、**イメージ エディター**、32 ビットのイメージを表示することができますが、編集することはできません。

True-カラー イメージを作成することもできます。 ただし、サンプルの場合は true。 色は表示されませんで完全なパレットで、**色**ウィンドウには、フォア グラウンドまたはバック グラウンドのカラー インジケーター領域にのみ出現します。 True の色を使用して作成、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)します。 詳細については、次を参照してください。[のカスタマイズまたは色を変更する](../windows/customizing-or-changing-colors-image-editor-for-icons.md)します。

ディスク上のカスタマイズされたカラー パレットを保存し、必要に応じて再読み込みできます。 最も最近使用したカラー パレットがレジストリに保存し、次回 Visual Studio を起動したときを自動的に読み込まれます。

- [前景色または背景色を選択します。](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)

- [色を使用してイメージの内側の塗りつぶし](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)

- [イメージを使用して別の場所を選択した色](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)

- [透明または不透明な背景の選択](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)

- [選択範囲の色の反転](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)

- [カスタマイズまたは色の変更](../windows/customizing-or-changing-colors-image-editor-for-icons.md)

- [カラー パレットの保存と読み込み別](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)

- [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)
