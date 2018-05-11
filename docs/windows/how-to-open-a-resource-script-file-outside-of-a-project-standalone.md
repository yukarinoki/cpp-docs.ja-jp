---
title: '方法: プロジェクト (スタンドアロン) の外側でリソース スクリプト ファイルを開く |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- .rc files, viewing resources
- resource script files, viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87dd0cb1e54b6e74c9c4f4fd7d9baff6461ad470
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-project-standalone"></a>方法: プロジェクトの外側で (スタンドアロンで) リソース スクリプト ファイルを開く
.rc ファイル内のリソースは、プロジェクトを開かずに表示できます。 ドキュメント ウィンドウで開く場合に、.rc ファイルが開きます、[リソース ビュー](../windows/resource-view-window.md)ウィンドウ (同様に、ファイルがプロジェクト内の場合)。  
  
> [!NOTE]
>  ファイルをスタンドアロンで (プロジェクトの外側で) 開いているときのみ使用できるコマンドがあるため、この違いは重要です。 たとえば、ことができますのみファイルを保存する別の形式で、または別のファイル名としてプロジェクトの外側で、ファイルが開かれたときに (、**名前を付けて保存**コマンドは、プロジェクト内のファイルが開かれたときに使用できません)。  
  
### <a name="to-open-an-rc-file-outside-a-project"></a>プロジェクトの外部で .rc ファイルを開くには  
  
1.  **ファイル**] メニューの [選択**開く**、順にクリックして**ファイル**です。  
  
2.  **ファイルを開く** ダイアログ ボックスで、ビューで、ファイルを強調表示し、をクリックする、リソース スクリプト ファイルへ移動**開く**です。  
  
    > [!NOTE]
    >  まず、プロジェクトを開く場合 (**ファイル**、**開く**、**プロジェクト**)、いくつかのコマンドを使用可能にすることはできません。 ファイルを "スタンドアロン" で開くと、プロジェクトを先に読み込むことなくファイルを開くことができます。  
  
 開き、リソース ファイルをテキスト形式で表示するには、次を参照してください。[リソース スクリプト (.rc) ファイルを編集](../windows/how-to-open-a-resource-script-file-in-text-format.md)です。  
  
#### <a name="to-open-multiple-rc-files-outside-a-project"></a>プロジェクトの外部で複数の .rc ファイルを開くには  
  
1.  2 つのリソース ファイルをスタンドアロンで開きます。 たとえば、Source1.rc と Source2.rc を開きます。  
  
    1.  **ファイル**] メニューの [選択**開く**、順にクリックして**ファイル**です。  
  
    2.  **ファイルを開く** ダイアログ ボックスで、最初のリソース スクリプト ファイル (Source1.rc) を開き、ファイルを強調表示し、をクリックする移動**開く**です。  
  
    3.  直前の手順を繰り返して、2 番目の .rc ファイル (Source2.rc) を開きます。  
  
         2 つの .rc ファイルが別個のドキュメント ウィンドウで開きました。  
  
2.  2 つの .rc ファイルを開いているときに、次の手順に従ってウィンドウを並べて表示すると、両方のファイルを同時に見ることができます。  
  
    -   **ウィンドウ**] メニューの [選択**水平タブ グループの新しい**または**垂直タブ グループ**です。  
  
         \- または -  
  
    -   .Rc ファイルの 1 つを右クリックして選択**水平タブ グループの新しい**または**垂直タブ グループ**ショートカット メニューからです。  
  
> [!NOTE]
>  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  

  
### <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)