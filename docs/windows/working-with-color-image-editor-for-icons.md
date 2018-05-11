---
title: カラー (アイコン用イメージ エディター) を使用する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors, Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f9016e36ce6b081446a00136445fd7ebdd5a341
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="working-with-color-image-editor-for-icons"></a>色の調整 (アイコン用イメージ エディター)
イメージ エディターには、具体的には処理され、色をカスタマイズする多くの機能が含まれています。 前景色または背景色を設定する、境界のある領域を塗りつぶす色、または現在の前景色または背景色として使用するイメージの色を選択できます。 ツールを使用することができます、[イメージ エディター ツールバー](../windows/toolbar-image-editor-for-icons.md)のカラー パレットをと共に、 [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)イメージを作成します。  
  
 カラー パレットの色 ウィンドウには、モノクロおよび 16 色のイメージのすべての色を示します。 標準の 16 色だけでなく、独自の色を作成できます。 パレットの色を変更すると、イメージに対応する色をすぐに変更されます。  
  
 ときに 256 色のアイコンとカーソル操作イメージ、色のプロパティで、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を使用します。 詳細については、次を参照してください。 [256 色のアイコンまたはカーソルの作成](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)です。  
  
> [!NOTE]
>  イメージ エディターを使用すると、32 ビット イメージを表示できます。ただし、編集はできません。  
  
 True カラー イメージを作成することもできます。 ただし、[色] ウィンドウで; フル パレットに色のサンプルは表示されません前景色または背景色のインジケーターの領域にのみ表示されます。 使用する場合は true。 色の作成、[カスタム カラー セレクター ダイアログ ボックス](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)です。 詳細については、次を参照してください。[のカスタマイズまたは色を変更する](../windows/customizing-or-changing-colors-image-editor-for-icons.md)です。  
  
 ディスク上のカスタム カラー パレットを保存し、必要に応じてそれらを再読み込みできます。 最も最近使用したカラー パレットがレジストリに保存され、Visual Studio を起動したとき、[次へ] を自動的に読み込まれます。  
  
-   [前景色または背景色を選択します。](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [色とイメージの内側の塗りつぶし](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [イメージから使用する別の場所を選択した色](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [透明または不透明な背景を選択します。](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [選択範囲の色の反転](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [カスタマイズや色を変更します。](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [カラー パレットの保存と読み込み別](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [[色] ウィンドウ](../windows/colors-window-image-editor-for-icons.md)  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   

