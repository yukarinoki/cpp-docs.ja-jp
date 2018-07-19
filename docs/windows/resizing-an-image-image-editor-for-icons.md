---
title: イメージ (アイコン用イメージ エディター) のサイズ変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c6636e1f92907c301c6e66abd63f744375bffeb8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879049"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>イメージのサイズ変更 (アイコン用イメージ エディター)
イメージのサイズ変更中に、イメージ エディターの動作は異なりますか[選択](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)イメージ全体または一部だけです。  
  
 選択範囲には、イメージの一部のみが含まれている場合は、イメージ エディターは、行を削除して、選択範囲を縮小またはピクセル、または現在の背景色で領域の列が行または列のピクセルを複製して選択範囲を拡大します。  
  
 選択範囲には、画像全体が含まれている場合、イメージ エディターか、圧縮し、イメージを拡大またはトリミングし、それを拡張します。  
  
 イメージのサイズ変更の 2 つのメカニズムがある: サイズ変更ハンドルと[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 すべてのサイズまたはイメージの一部を変更するサイズ変更ハンドルをドラッグすることができます。 ドラッグできるサイズ変更ハンドルは、純色です。 中空のハンドルをドラッグすることはできません。 選択の一部ではない、のみ、画像全体のサイズを変更するプロパティ ウィンドウを使用することができます。  
  
 ![サイズ変更ハンドル ビットマップに](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
サイズ変更ハンドル  
  
> [!NOTE]
>  選択したタイル表示オプションがある場合、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md)、次のタイルのグリッド線にスナップのサイズを変更します。 オプションは、ピクセル グリッドには、(既定の設定) が選択されているだけの場合に、[次へ] の使用可能なピクセル スナップのサイズを変更します。  
  
-   [イメージ全体のサイズを変更します。](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [トリミングまたはイメージ全体の拡張](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [全体のイメージ縮小または拡大](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [縮小または拡大イメージの一部](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

