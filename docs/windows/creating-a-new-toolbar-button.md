---
title: 新しいツール バー ボタンを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.toolbar
dev_langs:
- C++
helpviewer_keywords:
- Toolbar editor, creating buttons
- toolbar buttons (in Toolbar editor), button image
- toolbar buttons (in Toolbar editor), creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d883fbb34fe45be2ad84860ea7564350346749f2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873028"
---
# <a name="creating-a-new-toolbar-button"></a>ツール バー ボタンの新規作成
### <a name="to-create-a-new-toolbar-button"></a>新しいツールバー ボタンを作成するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md) Project1.rc など、リソース フォルダーを展開します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  展開して、**ツールバー**フォルダーおよび編集するツールバーを選択します。  
  
3.  ツールバーの右端にある空白のボタンに ID を割り当てます。 できるように編集することによって、 **ID**プロパティに、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 たとえば、ツール バー ボタンのメニュー オプションと同じ ID を提供する可能性があります。 この場合、ドロップダウン リスト ボックスを使用して、選択、 **ID**のメニュー オプション。  
  
     - または -  
  
     (ツールバーの表示のウィンドウ) で、ツールバーの右端にある空白のボタンを選択し、描画を開始します。 既定のボタンのコマンド ID が割り当てられます (ID_BUTTON\<n >)。  
  
 コピーして、新しいボタンとしてツールバー上にイメージを貼り付けることができます。  
  
#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>ツールバーにボタンとしてイメージを追加するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)ツールバーをダブルクリックして開きます。  
  
2.  次に、ツールバーに追加するには、イメージを開きます。  
  
    > [!NOTE]
    >  Visual Studio で、イメージを開くと場合、イメージ エディターで開きます。 その他のグラフィックス プログラム イメージを開くこともできます。  
  
3.  **編集**] メニューの [選択**コピー**です。  
  
4.  [ソース] ウィンドウの上部にあるタブをクリックして、ツールバーに切り替えます。  
  
5.  **編集**] メニューの [選択**貼り付け**です。  
  
     イメージは、ツールバーの [新規] ボタンとして表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
### <a name="requirements"></a>要件  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [ツール バー ボタン プロパティ](../windows/toolbar-button-properties.md)   
 [作成、移動、およびツール バー ボタンの編集](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)

