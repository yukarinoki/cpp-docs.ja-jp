---
title: ダイアログ エディター ツールバーの表示と非表示 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog editor, showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8a19de393e7451f045d840552127743f87e00ba
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019174"
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>[ダイアログ エディター] ツール バーの表示と非表示
開くと、**ダイアログ**エディター、**ダイアログ エディター**ソリューションの上部にあるツールバーが自動的に表示されます。  
  
### <a name="dialog-editor-toolbar"></a>ダイアログ エディター ツール バー  
  
|アイコン|説明|アイコン|説明|  
|----------|-------------|----------|-------------|  
|![ダイアログのテスト ボタン](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|[ダイアログのテスト]|![左右均等配置ボタン](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|[左右]|  
|![左揃えボタン](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|[左揃え]|![上下均等配置ボタン](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|[下へ移動]|  
|![右揃えボタン](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|[右揃え]|![Make 同じ幅ボタン](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|[同じ幅に揃える]|  
|![上揃えボタン](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|[上揃え]|![Make 同じ高さボタン](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|[同じ高さに揃える]|  
|![下揃えボタン](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|[下揃え]|![同じサイズのボタン](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|[同じサイズに揃える]|  
|![垂直方向の中心のボタン](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Vertical|![グリッドの切り替えボタン](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|グリッドの切り替え|  
|![水平方向の中央ボタン](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|[水平方向]|![ガイドの切り替えボタン](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|[ガイドの切り替え]|  
  
 **ダイアログ エディター**ツールバーには、ダイアログ ボックスで、たとえばサイズと配置上のコントロールのレイアウトを変更するためのボタンが含まれています。 **ダイアログ エディター**ツール バー ボタンにコマンドに対応しており、**形式**メニュー。 詳細については、次を参照してください。[ダイアログ エディターのアクセラレータ キー](../windows/accelerator-keys-for-the-dialog-editor.md)します。  
  
 は、**ダイアログ**エディターの表示を切り替えることができます、**ダイアログ エディター**ツールバーを使用できるツールバーおよびウィンドウの一覧から選択します。  
  
### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>ダイアログ エディターのツールバーを非表示  
  
1.  **ビュー**ボタンをクリックし**ツールバー**選択**ダイアログ エディター**サブメニューから。  
  
    > [!NOTE]
    >  **ダイアログ エディター**ダイアログ エディターのダイアログ ボックスのリソースを開くと、既定でツールバーが表示されます。 ただし、場合は、ツールバーを明示的に閉じる必要があります ダイアログ ボックスのリソースでは、次に開いた際に、を起動します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロールの配置](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [方法: リソースの作成](../windows/how-to-create-a-resource.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)