---
title: アイコンまたはその他のイメージ (アイコン用イメージ エディター) の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resource toolbars
- resources [Visual Studio], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2138e32b18f2e15de027e3cc04fb1bd7ee46ecd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874734"
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>アイコンまたはその他のイメージの作成 (アイコン用イメージ エディター)
(ビットマップ、アイコン、カーソル、またはツールバー)、新しいイメージを作成し、その外観をカスタマイズする、イメージ エディターを使用することができます。 後でパターン化新しいビットマップを作成することも、[テンプレート](../windows/how-to-use-resource-templates.md)です。  
  
### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>アンマネージ C++ プロジェクトに新しいイメージ リソースを追加するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし**リソースの挿入**ショートカット メニューからです。 (を単に右クリック、カーソルなど、.rc ファイルに既存のイメージ リソースがある場合、**カーソル**フォルダーを選択**挿入カーソル**ショートカット メニューからです)。  
  
    > [!NOTE]
    >  **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)を作成したい画像リソースの種類を選択 (**ビットマップ**など) をクリックし、**新規**です。  
  
     場合は、プラス記号 (**+**) で画像リソースの種類の横に表示される、**リソースの挿入**ツールバーのテンプレートが使用できることを意味、ダイアログ ボックスで、します。 テンプレートの一覧を展開し、テンプレートを選択してをクリックするには、プラス記号をクリックして**新規**です。  
  
### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>.NET プログラミング言語でのプロジェクトに新しいイメージ リソースを追加するには  
  
1.  **ソリューション エクスプ ローラー**、プロジェクト フォルダーを右クリックし (たとえば、 **WindowsApplication1**)。  
  
2.  ショートカット メニューから **追加**、順に選択**新しい項目の追加**です。  
  
3.  **カテゴリ** ウィンドウで、展開、**ローカル プロジェクト アイテム**フォルダーを選択し、**リソース**です。  
  
4.  **テンプレート** ウィンドウで、プロジェクトに追加するには、リソースの種類を選択します。  
  
     ソリューション エクスプ ローラーでプロジェクトにリソースを追加し、リソースがで開きます、[イメージ エディター](../windows/image-editor-for-icons.md)です。 イメージ エディターで使用できるすべてのツールを使用して、イメージを変更することができますようになりました。 マネージ プロジェクトにイメージを追加する方法については、次を参照してください。[デザイン時にピクチャの読み込み](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms)です。  
  
    > [!NOTE]
    >  編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。 詳細については、次を参照してください。[リソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)で、 *.NET Framework 開発者ガイド 』* です。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 なし  
  
## <a name="see-also"></a>関連項目  
 [アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [ビットマップ ツールバーからへの変換](../windows/converting-bitmaps-to-toolbars.md)   
 [ツールバーの新規作成](../windows/creating-new-toolbars.md)   
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)

