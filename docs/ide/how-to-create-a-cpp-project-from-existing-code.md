---
title: '方法 : 既存のコードから C++ プロジェクトを作成する'
ms.date: 11/04/2016
helpviewer_keywords:
- C++, creating projects from existing code
ms.assetid: e328a938-395c-48ea-9e35-dd433de12b31
ms.openlocfilehash: dafd4e939444c581a76e9ccfcab4c3f6bbe819d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552504"
---
# <a name="how-to-create-a-c-project-from-existing-code"></a>方法 : 既存のコードから C++ プロジェクトを作成する

Visual Studio で、**既存コード ファイルからの新しいプロジェクトの作成**ウィザードを使用すると、既存のコード ファイルを Visual C++ プロジェクトに移植できます。 このウィザードは、Visual Studio の以前の Express Edition では使用できません。 このウィザードによって、MSBuild システムを利用してソース ファイルとビルド構成を管理する新しいソリューションとプロジェクトが作成されます。

既存のコード ファイルを Visual C++ プロジェクトを移植することで、IDE に組み込まれているネイティブ MSBuild プロジェクト管理機能をすべて利用できます。 nmake メイクファイル、CMake、代替など、既存のビルド システムを使用する場合、代わりに [フォルダーを開く] オプションを利用できます。 詳細については、「[Open Folder projects in Visual C++ (Visual C++ の [フォルダーを開く] プロジェクト)](../ide/non-msbuild-projects.md)」をご覧ください。 いずれのオプションでも、[IntelliSense](/visualstudio/ide/using-intellisense) や[プロジェクト プロパティ](../ide/working-with-project-properties.md)など、IDE 機能を利用できます。

### <a name="to-create-a-c-project-from-existing-code"></a>既存のコードから C++ プロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** をポイントし、**[既存のコードからプロジェクトを作成]** をクリックします。

1. **既存コード ファイルからの新しいプロジェクトの作成**ウィザードの最初のページで、**[作成するプロジェクトの種類を入力してください]** ボックスの一覧の **[Visual C++]** をクリックします。 **[次へ]** を選択して続行します。

1. プロジェクトの場所とソース ファイルのディレクトリを指定します。 このページの詳細については、「[[プロジェクトの場所とソース ファイルの指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-project-location-and-source-files.md)」を参照してください。 **[次へ]** を選択して続行します。

1. 使用するプロジェクト設定を指定します。 このページの詳細については、「[[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)」を参照してください。 **[次へ]** を選択して続行します。

1. 使用するデバッグ構成の設定を指定します。 このページの詳細については、「[[デバッグ構成の設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-debug-configuration-settings.md)」を参照してください。 **[次へ]** を選択して続行します。

1. 使用するリリース構成の設定を指定します。 このページの詳細については、「[[リリースの構成の設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-release-configuration.md)」を参照してください。 **[完了]** をクリックし、新しいプロジェクトを生成します。

## <a name="see-also"></a>参照

[[プロジェクトの場所とソース ファイルの指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-project-location-and-source-files.md)<br>
[[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)<br>
[[デバッグ構成の設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-debug-configuration-settings.md)<br>
[[リリースの構成の設定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-release-configuration.md)