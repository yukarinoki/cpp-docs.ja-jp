---
title: 'チュートリアル: MSBuild を使用した Visual C プロジェクトの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.walkthrough.createproject
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88366f78556ebcab6dc7b796cdeeefd402b99721
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392563"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成
このチュートリアルを使用する方法を示します[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]コマンド プロンプトでの Visual C プロジェクトをビルドします。 C++ ソース ファイルと Visual C コンソール アプリケーション用の XML ベースのプロジェクト ファイルを作成する方法を学習します。 次に、プロジェクトをビルドしてから、ビルド処理をカスタマイズする方法を学習します。  
  
 このチュートリアルでは、次の作業について説明します。  
  
-   プロジェクトの C++ ソース ファイルの作成。  
  
-   XML [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] プロジェクト ファイルの作成。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] を使用したプロジェクトのビルド。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] を使用したプロジェクトのカスタマイズ。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するための要件は次のとおりです。  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] システムの基本的な知識  
  
## <a name="creating-the-c-source-files"></a>C++ ソース ファイルの作成  
 このチュートリアルでは、ソース ファイルとヘッダー ファイルがあるプロジェクトを作成します。 main.cpp という名前のソース ファイルには、コンソール アプリケーションの main 関数を含めます。 main.h という名前のヘッダー ファイルには、iostream ヘッダー ファイルをインクルードするためのコードを含めます。 これらの C++ ファイルは、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] またはテキスト エディターを使用して作成できます。  
  
#### <a name="to-create-the-c-source-files-for-your-project"></a>プロジェクトの C++ ソース ファイルを作成するには  
  
1.  プロジェクトのディレクトリを作成します。  
  
2.  main.cpp という名前のファイルを作成し、このファイルに次のコードを追加します。  
  
    ```cpp  
    // main.cpp : the application source code.  
    #include <iostream>  
    #include "main.h"  
    int main()  
    {  
       std::cout << "Hello, from MSBuild!\n";  
       return 0;  
    }  
    ```  
  
3.  main.h という名前のファイルを作成し、このファイルに次のコードを追加します。  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## <a name="creating-the-xml-msbuild-project-file"></a>プロジェクト ファイルXML MSBuild プロジェクト ファイルの作成  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]プロジェクト ファイルはプロジェクトのルート要素を含む XML ファイル (\<プロジェクト >)。 プロジェクトで、次の例、 \<Project > 要素には、7 つの子要素が含まれています。  
  
-   3 つの項目グループ タグ (\<ItemGroup >) プロジェクトの構成とプラットフォーム、ソース ファイル名、およびヘッダー ファイルの名前を指定します。  
  
-   3 つのインポート タグ (\<インポート >) の Microsoft Visual C 設定の場所を指定します。  
  
-   プロパティ グループ タグ (\<PropertyGroup >) プロジェクトの設定を指定します。  
  
#### <a name="to-create-the-msbuild-project-file"></a>MSBuild プロジェクト ファイルを作成するには  
  
1.  テキスト エディターを使用してという名前のプロジェクト ファイルを作成する`myproject.vcxproj`、次のルートを追加および\<プロジェクト > 要素。 ルートの次の手順で、要素を挿入\<Project > タグ。  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  次の 2 つの追加\<ProjectConfiguration > 子要素、 \<ItemGroup > 要素。 この子要素は、32 ビットの Windows オペレーティング システムのデバッグおよびリリース構成を指定します。  
  
    ```xml  
    <ItemGroup>  
      <ProjectConfiguration Include="Debug|Win32">  
        <Configuration>Debug</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
      <ProjectConfiguration Include="Release|Win32">  
        <Configuration>Release</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
    </ItemGroup>  
  
    ```  
  
3.  次の追加\<インポート/> このプロジェクトの既定の C++ 設定のパスを指定する要素。  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  次のプロパティ グループ要素の追加 (\<PropertyGroup >) 2 つのプロジェクト プロパティを指定します。  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  次の追加\<インポート/> このプロジェクトの現在の C++ 設定のパスを指定する要素。  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  次の追加\<ClCompile > 子要素を\<ItemGroup > 要素。 この子要素は、コンパイルする C/C++ ソース ファイルの名前を指定します。  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  次の追加\<ClInclude > 子要素を\<ItemGroup > 要素。 この子要素は、C/C++ ソース ファイルに対応するヘッダー ファイルの名前を指定します。  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  次の追加\<インポート > 要素をこのプロジェクトのターゲットを定義するファイルのパスを指定します。  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### <a name="complete-project-file"></a>完成したプロジェクト ファイル  
 次のコードは、前の手順で作成したプロジェクト ファイルのすべての内容です。  
  
```xml  
<Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup>  
    <ProjectConfiguration Include="Debug|Win32">  
      <Configuration>Debug</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
    <ProjectConfiguration Include="Release|Win32">  
      <Configuration>Release</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  <PropertyGroup>  
    <ConfigurationType>Application</ConfigurationType>  
    <PlatformToolset>v120</PlatformToolset>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
  <ItemGroup>  
    <ClCompile Include="main.cpp" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClInclude Include="main.h" />  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
</Project>  
```  
  
## <a name="using-msbuild-to-build-your-project"></a>MSBuild を使用したプロジェクトのビルド  
 コマンド プロンプトで次のコマンドを入力して、コンソール アプリケーションをビルドします。  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] は、出力ファイルのディレクトリを作成し、プロジェクトをコンパイルおよびリンクして Myproject.exe プログラムを生成します。 ビルド処理が完了したら、次のコマンドを使用してアプリケーションを実行します。  
  
```  
myproject  
```  
  
 アプリケーションは、「こんにちは, from MSBuild!」を表示する必要があります。 コンソール ウィンドウに表示します。  
  
## <a name="customizing-your-project"></a>プロジェクトのカスタマイズ  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] では、定義済みのビルド ターゲットを実行したり、ユーザー定義のプロパティを適用したりできるほか、カスタム ツール、イベント、およびビルド ステップを使用することができます。 このセクションでは、次のタスクについて説明します。  
  
-   使用して[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]ビルド ターゲットを持つ。  
  
-   使用する[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]とビルド プロパティです。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] と 64 ビットのコンパイラおよびツールの併用。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] と他のツールセットの併用。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] のカスタマイズの追加。  
  
### <a name="using-msbuild-with-build-targets"></a>MSBuild とビルド ターゲットの併用  
 A*ビルド ターゲット*ビルド時に実行できる定義済みまたはユーザー定義のコマンドの名前付きセットです。 ターゲット コマンド ライン オプションを使用して (**/t**) ビルド ターゲットを指定します。 場合、`myproject`例のプロジェクトで、定義済み**クリーン**ターゲットがデバッグ フォルダー内のすべてのファイルを削除し、新しいログ ファイルを作成します。  
  
 コマンド プロンプトで次のコマンドを入力して、`myproject` を削除します。  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### <a name="using-msbuild-with-build-properties"></a>MSBuild とビルド プロパティの併用  
 プロパティ コマンド ライン オプション (**/p**) は、プロジェクト ビルド ファイルでプロパティをオーバーライドすることができます。 `myproject` サンプル プロジェクトでは、`Configuration` プロパティによってリリース用またはデバッグ用のビルド構成が指定されます。 また、ビルド済みアプリケーションを実行するためのオペレーティング システムが、`Platform` プロパティで指定されます。  
  
 コマンド プロンプトで次のコマンドを入力して、32 ビット Windows で実行される予定の `myproject` アプリケーションのデバッグ ビルドを作成します。  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 `myproject` サンプル プロジェクトが、64 ビット Windows の構成と、別の `myplatform` という名前のカスタム オペレーティング システムの構成も定義していると想定します。  
  
 コマンド プロンプトで次のコマンドを入力して、64 ビット Windows で実行するリリース ビルドを作成します。  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 コマンド プロンプトで次のコマンドを入力して、`myplatform` のリリース ビルドを作成します。  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>MSBuild と 64 ビットのコンパイラおよびツールの併用  
 64 ビット Windows で、既定では Visual C をインストールする場合は、64 ビット x64 ネイティブおよびクロス ツールがインストールされます。 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] プロパティを設定することで、アプリケーションのビルドには 64 ビットのコンパイラおよびツールが使用されるように `PreferredToolArchitecture` を構成できます。 このプロパティは、プロジェクトの構成とプラットフォームのプロパティには影響しません。 既定では、32 ビット版のツールが使用されます。 コンパイラおよびツールの 64 ビット バージョンを指定するを Myproject.vcxproj プロジェクト ファイル内の後に、次のプロパティ グループ要素を追加、 `Microsoft.Cpp.default.props` \<インポート/> 要素。  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 64 ビット ツールを使用してアプリケーションをビルドするには、コマンド プロンプトで次のコマンドを入力します。  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="using-msbuild-with-a-different-toolset"></a>MsBuild と他のツールセットの併用  
 ツールセットおよびライブラリの Visual C をインストールするには、他のバージョンがある場合[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]Visual C の現在のバージョンのいずれかのアプリケーションを構築できますか、他のバージョンをインストールします。 たとえば、インストールされている[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]を Windows XP の Visual の C++ 11.0 ツールセットを指定して、Microsoft.Cpp.props の後に、次のプロパティ グループ要素を Myproject.vcxproj プロジェクト ファイルに追加する、`<Import />`要素。  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 Visual C++ 11.0 Windows XP ツールセットでプロジェクトをリビルドするには、次のコマンドのいずれかを入力します。  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### <a name="adding-msbuild-customizations"></a>MSBuild のカスタマイズの追加  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] では、さまざまな方法でビルド処理をカスタマイズできます。 次のトピックでは、[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] プロジェクトにカスタム ビルド ステップ、ツール、およびイベントを追加する方法を示します。  
  
-   [方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)  
  
-   [方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [方法: MSBuild プロジェクトでビルド イベントを使用する](../build/how-to-use-build-events-in-msbuild-projects.md)