---
title: イメージ (アイコン用イメージ エディター) のサイズ変更 |Microsoft Docs
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
ms.openlocfilehash: 41494e8b88f41c4c842e95e9f8a9f5da0247739f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605644"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>イメージのサイズ変更 (アイコン用イメージ エディター)
イメージのサイズ変更中に、イメージ エディターの動作したかどうかに依存[選択](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)イメージ全体または一部だけです。  
  
 選択範囲には、イメージの一部のみが含まれている場合は、イメージ エディターは、行を削除することによって、選択範囲を縮小またはピクセル、または現在の背景色で領域の列は、ピクセルの行または列を複製して、選択範囲を拡大します。  
  
 選択範囲には、イメージ全体が含まれている場合、イメージ エディターか、圧縮、イメージを拡大またはトリミングし、拡張されています。  
  
 イメージのサイズ変更の 2 つのメカニズムがある: サイズ変更ハンドルと[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 イメージの一部またはすべてのサイズを変更するサイズ変更ハンドルをドラッグすることができます。 サイズ変更ハンドルをドラッグすることは、solid です。 白抜きのハンドルをドラッグすることはできません。 選択の一部ではない、のみ、イメージ全体のサイズを変更するプロパティ ウィンドウを使用することができます。  
  
 ![サイズ変更ハンドルをビットマップに](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
サイズ変更ハンドル  
  
> [!NOTE]
>  選択したタイル表示オプションがある場合、[グリッドの設定 ダイアログ ボックス](../windows/grid-settings-dialog-box-image-editor-for-icons.md)、[次へ] のタイル グリッド線にスナップのサイズを変更します。 のみをピクセル グリッドのオプションは選択する (既定の設定、)、[次へ] の使用可能なピクセルにスナップのサイズを変更します。  
  
-   [イメージ全体のサイズ変更](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [全体のイメージ トリミングまたは拡張](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [全体のイメージ縮小または拡大](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [縮小またはイメージの一部を拡大](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)