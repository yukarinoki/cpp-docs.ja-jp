---
title: アイコン用イメージ エディター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, images
- resource editors, graphics
- Image editor [C++]
- resource editors, Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41c4bf71d8d3479f8353c1f57e725f07926dee47
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879283"
---
# <a name="image-editor-for-icons"></a>アイコン用イメージ エディター
イメージ エディターには、イメージの作成と編集に使用できる広範なツール セットと、ツール バーのビットマップの作成に役立つ機能が用意されています。 **[イメージ]** メニューのコマンドや、 **[イメージ エディター]** ツール バーのツールを使用して、ビットマップ、アイコン、カーソルだけでなく、GIF 形式や JPEG 形式のイメージも編集できます。  
  
 イメージ エディターでは、次の作業ができます。  
  
-   [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)  
  
-   [色の調整](../windows/working-with-color-image-editor-for-icons.md)  
  
-   [アイコンとカーソル : ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
  
-   [イメージ エディターのアクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)  
  
 イメージ エディター ウィンドウには 2 つのイメージ ビューが表示され、2 つのペインは分割バーで区切られています。 分割バーを左右にドラッグすると、ペインの相対サイズを変更できます。 アクティブなペインには、選択境界線が表示されます。  
  
 イメージ エディター ウィンドウは、必要に応じて調整できます。 [拡大率を変更](../windows/changing-the-magnification-factor-image-editor-for-icons.md) したり、 [ピクセル グリッドの表示と非表示を切り替え](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md)たりできます。  
  
> [!NOTE]
>  イメージ エディターを使用すると、32 ビット イメージを表示できます。ただし、編集はできません。  
  
## <a name="visual-studio-image-library"></a>Visual Studio Image Library  
 アプリケーションで使用できるアニメーション、ビットマップ、およびアイコンが多数含まれる Visual Studio Image Library は、無料でダウンロードできます。 ライブラリをダウンロードする方法の詳細については、「 [Visual Studio Image Library](/visualstudio/designers/the-visual-studio-image-library)」を参照してください。  
  
## <a name="managed-resources"></a>マネージ リソース  
 イメージ エディターと [バイナリ エディター](binary-editor.md) を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
### <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)   
 [アイコン](http://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)

