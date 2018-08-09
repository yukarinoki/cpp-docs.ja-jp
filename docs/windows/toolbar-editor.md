---
title: ツール バー エディター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.toolbar.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors, Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe9c73a09e2a0f220ee4454baefb07b7e65fcafa
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641648"
---
# <a name="toolbar-editor"></a>ツール バー エディター
ツール バー エディターを使用すると、ツール バー リソースを作成し、ビットマップをツール バー リソースに変換できます。 ツールバー エディターはグラフィカルな表示を使用して、完成したアプリケーションの外観と非常によく似たツールバーとボタンを示します。  
  
 ツールバー エディターで、次の作業ができます。  
  
-   [新しいツールバーとボタンを作成する](../windows/creating-new-toolbars.md)  
  
-   [ビットマップからツールバーのリソースに変換する](../windows/converting-bitmaps-to-toolbars.md)  
  
-   [ツールバー ボタンを作成、移動、編集する](../windows/creating-moving-and-editing-toolbar-buttons.md)  
  
-   [ツール ヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)  
  
 イメージ エディター ウィンドウと同じように、ツールバー エディター ウィンドウには、ボタン イメージの 2 つのビューが表示されます。 分割バーは、2 つのペインを分割します。 分割バーを左右にドラッグすると、ペインの相対サイズを変更できます。 アクティブなペインには、選択境界線が表示されます。 イメージの 2 つのビューの上にはサブジェクト ツールバーがあります。  
  
 ![ツール バー エディター](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")  
ツール バー エディター  
  
 ツールバー エディターは、イメージ エディターの機能に似ています。 メニュー項目、グラフィック ツール、ビットマップのグリッドは、イメージ エディター内のものと同じです。 イメージ メニューには、ツールバー エディターとイメージ エディターを切り替えるためのメニュー コマンドがあります。 グラフィック ツールバー、カラー パレット、またはイメージ メニューの使用の詳細については、「 [イメージ エディター](../windows/image-editor-for-icons.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)   
 [メニューとその他のリソース](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)