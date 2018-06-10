---
title: Visual C++ プロジェクトの作成と管理 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vcprojects
- creatingmanagingVC
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3afbd2019965d859895462cfdad57292bc2e0b3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332424"
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>MSBuild ベースの Visual C++ プロジェクトの作成と管理
MSBuild は Visual C++ のネイティブ ビルド システムであり、MFC または ATL ライブラリを使用するデスクトップ アプリケーションだけでなく、UWP アプリでの使用にも最適なビルド システムです。 MSBuild は Visual Studio IDE およびプロジェクト システムと緊密に統合されていますが、コマンド ラインから使用することもできます。 Visual Studio 2017 以降、Visual C ++ では、[[フォルダーを開く] 機能を通して CMake および他の非 MSBuild システム](non-msbuild-projects.md)をサポートしています。

MSBuild ベースのプロジェクトには、プログラムのコンパイルに必要なすべてのファイルとリソースを指定する XML 形式のプロジェクト ファイル (.vcxproj) と、その他の構成設定 (たとえば、ターゲット プラットフォーム (x 86、x64、または ARM) や、プログラムのリリース バージョンとデバッグ バージョンのどちらをビルドしているかなど) があります。 プロジェクト (1 つまたは複数) は *ソリューション*に含められます。たとえば、ソリューションには、いくつかの Win32 DLL プロジェクトと、それらの DLL を使用する 1 つの Win32 コンソール アプリケーションを含めることができます。 プロジェクトをビルドすると、MSBuild エンジンがプロジェクト ファイルを使用して、実行可能ファイルやその他の指定されたカスタム出力を生成します。

Visual C++ プロジェクトを作成するには、**[ファイル &#124; 新規作成 &#124; プロジェクト]** を選択して、左側のウィンドウで Visual C++ が選択されていることを確認し、中央のウィンドウでプロジェクト テンプレートの一覧から選択します。 テンプレートをクリックすると、ほとんどの場合はウィザードが表示され、プロジェクトを作成する前にさまざまなプロジェクト プロパティを設定することができます。 それらのプロパティは、プロジェクトのプロパティ ページを使用することで、後で表示し変更することができます (**[プロジェクト &#124; プロパティ]**)。  
  
 次のようにして、新しいプロジェクトを作成することもできます。  
  
-   **[ファイル &#124; 新規作成 &#124; 既存のコードから新しいプロジェクトを作成]** を選択して、プロンプトに従って既存のソース コード ファイルを追加します。 このオプションは、ソース コード ファイルが 25 以下で、複雑な依存関係がなく、比較的小規模で単純なプロジェクトに最も適しています。  
  
-   メイクファイルから始め、[全般] タブでメイクファイル プロジェクト テンプレートを選択します。  
  
-   **[全般]** タブで空のプロジェクトを作成し、ソリューション エクスプローラーでプロジェクト ノードを右クリックして **[追加 &#124; 既存項目]** を選択してソース コード ファイルを自分で追加します。  
  
-   using the [Win32 Application Wizard](../windows/win32-application-wizard.md)の使用。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Visual C++ プロジェクトの種類](../ide/visual-cpp-project-types.md)  
 Visual C++ で利用できる MSBuild ベースのプロジェクトの種類について説明します。  
  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)  
 さまざまな種類の MSBuild プロジェクトで使用されるファイルの種類について説明します。  
  
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)  
 ウィザードを使用して Visual C++ プロジェクトを作成する方法について説明します。  
  
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)  
 プロパティ ページおよびプロパティ シートを使用して、プロジェクト設定を指定する方法について説明します。  
  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)  
 機能を追加するために、クラス、メソッド、変数などの要素をプロジェクトに追加する方法について説明します。  
  
 [方法 : ビルドのプロジェクト出力ファイルを編成する](../ide/how-to-organize-project-output-files-for-builds.md)  
 プロジェクトの出力ファイルを管理する方法について説明します。  
  
## <a name="related-sections"></a>関連項目  
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)  
 コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。  
  
 [Visual C++ リファレンス](http://msdn.microsoft.com/en-us/1ba03b5c-8229-4f63-b08c-6c12141d6ab1)  
 C と C++ の言語リファレンス、Visual C++ で提供されるライブラリ、Visual C++ 機能拡張オブジェクト モデル、および MASM (Microsoft Macro Assembler) に関するトピックへのリンクがあります。  
  
## <a name="see-also"></a>参照  
 [Visual Studio SDK](http://msdn.microsoft.com/vstudio/extend)
