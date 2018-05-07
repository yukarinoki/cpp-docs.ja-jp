---
title: '方法: 既存のコードから C++ プロジェクトを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1786e5704d7afd07576ab738d907eb841518f8be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>方法 : 既存のコードから C++ プロジェクトを作成する

Visual Studio で移植できます、既存のコード ファイルを Visual C プロジェクトを使用して、**既存コード ファイルからの新しいプロジェクトの作成**ウィザード。 このウィザードでは、Visual Studio の以前の Express edition で使用できません。 このウィザードでは、新しいソリューションと MSBuild システムを使用して、ソース ファイルを管理し、構成をビルドするプロジェクトを作成します。  
  
Visual C プロジェクトに既存のコード ファイルを移植するには、すべての IDE に組み込まれているネイティブの MSBuild プロジェクトの管理機能を使用することができます。 Nmake メイクファイル、CMake、選択肢など、既存のビルド システムを使用する場合は、代わりにフォルダーを開くオプションを使用することができます。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](../ide/non-msbuild-projects.md)」をご覧ください。 両方のオプションでは、IDE の機能を使用できます。 [IntelliSense](/visualstudio/ide/using-intellisense)と[プロジェクト プロパティ](../ide/working-with-project-properties.md)です。  
  
### <a name="to-create-a-c-project-from-existing-code"></a>既存のコードから C++ プロジェクトを作成するには  
  
1.  **ファイル** メニューのをポイント**新規**、クリックして**既存のコードからプロジェクトを**です。  
  
1.  最初のページで、**既存コード ファイルから新しいプロジェクトの作成**ウィザードで、 **Visual C**で、**作成にどのような種類のプロジェクトを指定しては** ボックスの一覧です。 **[次へ]** を選択して続行します。 
  
1.  プロジェクトの場所と、ソース ファイルのディレクトリを指定します。 このページの詳細については、「[プロジェクト場所を指定し、、ソース ファイルを作成する新しいプロジェクトから既存コード ファイル ウィザード](../ide/specify-project-location-and-source-files.md)です。 **[次へ]** を選択して続行します。  
  
1.  使用するプロジェクトの設定を指定します。 このページの詳細については、「[プロジェクト設定の指定]、[新しいプロジェクトから既存コード ファイル作成ウィザード](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)です。 **[次へ]** を選択して続行します。  

1.  使用するデバッグ構成の設定を指定します。 このページの詳細については、「[デバッグ構成の設定を指定して、新しいプロジェクトから既存コード ファイル作成ウィザード](../ide/specify-debug-configuration-settings.md)です。 **[次へ]** を選択して続行します。  

1.  使用するリリースの構成設定を指定します。 このページの詳細については、「[リリース構成設定の指定、新しいプロジェクトから既存コード ファイル作成ウィザード](../ide/specify-release-configuration.md)です。 選択**完了**新しいプロジェクトを生成します。  
  
## <a name="see-also"></a>関連項目  

[プロジェクトを指定の場所とソース ファイル、既存コード ファイル ウィザードから新しいプロジェクトの作成](../ide/specify-project-location-and-source-files.md)   
[プロジェクトの設定を指定して、既存のコード ファイル ウィザードから新しいプロジェクトの作成](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)   
[デバッグ構成の設定を指定して、既存のコード ファイル ウィザードから新しいプロジェクトの作成](../ide/specify-debug-configuration-settings.md)   
[[リリースの構成の設定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-release-configuration.md)