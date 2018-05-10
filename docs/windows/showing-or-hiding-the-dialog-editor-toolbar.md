---
title: ダイアログ エディター ツールバーの表示と非表示 |Microsoft ドキュメント
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
ms.openlocfilehash: ad456d37252b40be72217e6cbc40a2a399bb34ef
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar"></a>[ダイアログ エディター] ツール バーの表示と非表示
ダイアログ エディターを開くと、ソリューションの上部に自動的にダイアログ エディター ツールバーが表示されます。  
  
### <a name="dialog-editor-toolbar"></a>ダイアログ エディター ツール バー  
  
|アイコン|説明|アイコン|説明|  
|----------|-------------|----------|-------------|  
|![ダイアログのテスト ボタン](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|[ダイアログのテスト]|![左右均等配置ボタン](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|[左右]|  
|![左揃えボタン](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|[左揃え]|![上下均等配置ボタン](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|[下へ移動]|  
|![右揃えボタン](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|[右揃え]|![Make 同じ幅ボタン](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|[同じ幅に揃える]|  
|![上揃えボタン](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|[上揃え]|![Make 同じ高さボタン](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|[同じ高さに揃える]|  
|![下揃えボタン](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|[下揃え]|![Make 同じサイズのボタン](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|[同じサイズに揃える]|  
|![垂直方向の中央揃えボタン](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|Vertical|![グリッドの切り替えボタン](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|グリッドの切り替え|  
|![水平方向の中央揃えボタン](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|[水平方向]|![ガイドの切り替えボタン](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|[ガイドの切り替え]|  
  
 ダイアログ エディター ツールバーには、たとえばサイズと位置合わせ ダイアログ ボックス上のコントロールのレイアウトを変更するためのボタンが含まれています。 ダイアログ エディター ツールバーのボタンは、[書式] メニューのコマンドに対応します。 詳細については、「[ダイアログ エディターのアクセラレータ キー](../windows/accelerator-keys-for-the-dialog-editor.md)です。  
  
 ダイアログ エディターでは、ときに、使用可能なツールバーと windows の一覧から選択して、ダイアログ エディターのツールバーの表示を切り替えることができます。  
  
### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>ダイアログ エディター ツールバーを非表示  
  
1.  **ビュー**ボタンをクリックし**ツールバー**順に選択**ダイアログ エディター**サブメニューからです。  
  
    > [!NOTE]
    >  ダイアログ エディターでダイアログ ボックスのリソースを開くと、既定では、ダイアログ エディターのツールバーが表示されます。ただし、ツールバーを明示的に閉じる場合は、ダイアログ ボックスのリソースでは、次に開いた際を起動する必要があります。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロールの配置](../windows/arrangement-of-controls-on-dialog-boxes.md)   
 [方法: リソースの作成](../windows/how-to-create-a-resource.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)

