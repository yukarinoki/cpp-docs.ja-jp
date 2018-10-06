---
title: 'チュートリアル: MSBuild を使用した Visual C プロジェクトの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 09/24/2018
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
ms.openlocfilehash: e8a1c45342cf1f5eb178764d6fd723950f52e7e0
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821242"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成

このチュートリアルでは、MSBuild を使用して、コマンド プロンプトでの Visual C プロジェクトをビルドする方法を示します。 C++ ソース ファイルと Visual C のコンソール アプリケーションの XML ベースのプロジェクト ファイルを作成する方法について説明します。 プロジェクトをビルドした後は、ビルド プロセスをカスタマイズする方法を学習します。

このチュートリアルでは、次の作業について説明します。

- プロジェクトの C++ ソース ファイルの作成。

- XML MSBuild プロジェクト ファイルを作成します。

- MSBuild を使用して、プロジェクトをビルドします。

- MSBuild を使用して、プロジェクトをカスタマイズします。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するための要件は次のとおりです。

- Visual Studio でのコピー、 **C++ によるデスクトップ開発**ワークロードをインストールします。

- MSBuild システムの一般的理解。

> [!NOTE]
> Visual Studio IDE を使用して、後で、プロジェクト ファイルを編集する場合は、このアプローチを使用しないでください。 .Vcxproj ファイルを手動で作成する場合、Visual Studio IDE できないことがあります、読み込んでを編集したり、プロジェクトがプロジェクト項目でワイルドカードを使用している場合に特にです。

> [!NOTE]
> 低レベルのビルド手順のほとんどに含まれる、 **.targets**と **.props**プロパティに格納されている、VCTargets ディレクトリで定義されているファイル`$(VCTargetsPath)`します。 Visual Studio 2017 Enterprise Edition でこれらのファイルの既定のパスは c:\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Enterprise\\Common7\\IDE\\VC\\VCTargets\\します。

## <a name="creating-the-c-source-files"></a>C++ ソース ファイルの作成

このチュートリアルでは、ソース ファイルとヘッダー ファイルを持つプロジェクトを作成します。 main.cpp という名前のソース ファイルには、コンソール アプリケーションの main 関数を含めます。 main.h という名前のヘッダー ファイルには、iostream ヘッダー ファイルをインクルードするためのコードを含めます。 Visual Studio Code などのエディターで、Visual Studio またはテキストを使用してこれらの C++ ファイルを作成できます。

### <a name="to-create-the-c-source-files-for-your-project"></a>プロジェクトの C++ ソース ファイルを作成するには

1. プロジェクトのディレクトリを作成します。

1. main.cpp という名前のファイルを作成し、このファイルに次のコードを追加します。

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

1. main.h という名前のファイルを作成し、このファイルに次のコードを追加します。

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>プロジェクト ファイルXML MSBuild プロジェクト ファイルの作成

MSBuild プロジェクト ファイルがプロジェクトのルート要素を含む XML ファイル (`<Project>`)。 次の例のプロジェクト、`<Project>`要素には、7 つの子要素が含まれています。

- 3 つの項目グループ タグ (`<ItemGroup>`) プロジェクトの構成とプラットフォーム、ソース ファイル名、およびヘッダー ファイル名を指定します。

- 3 つのタグの読み込み (`<Import>`) Microsoft Visual C の設定の場所を指定します。

- プロパティ グループ タグ (`<PropertyGroup>`) プロジェクトの設定を指定します。

### <a name="to-create-the-msbuild-project-file"></a>MSBuild プロジェクト ファイルを作成するには

1. という名前のプロジェクト ファイルを作成するテキスト エディターを使用して`myproject.vcxproj`、し、次のルートを追加`<Project>`要素。 ルートの次の手順で、要素を挿入`<Project>`タグ。

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

1. 次の 2 つの追加`<ProjectConfiguration>`内の子要素、`<ItemGroup>`要素。 この子要素は、32 ビットの Windows オペレーティング システムのデバッグおよびリリース構成を指定します。

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

1. 次の追加`<Import>`このプロジェクトの既定の C++ 設定のパスを指定する要素。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. 次のプロパティ グループ要素の追加 (`<PropertyGroup>`) 2 つのプロジェクト プロパティを指定します。

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v141</PlatformToolset>
    </PropertyGroup>
    ```

1. 次の追加`<Import>`このプロジェクトの現在の C++ 設定のパスを指定する要素。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. 次の追加`<ClCompile>`内の子要素、`<ItemGroup>`要素。 この子要素は、コンパイルする C/C++ ソース ファイルの名前を指定します。

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>` *ビルド ターゲット*で定義されていると、 **VCTargets**ディレクトリ。

1. 次の追加`<ClInclude>`内の子要素、`<ItemGroup>`要素。 この子要素は、C/C++ ソース ファイルに対応するヘッダー ファイルの名前を指定します。

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. 次の追加`<Import>`このプロジェクトのターゲットを定義するファイルのパスを指定する要素。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>完成したプロジェクト ファイル

次のコードは、前の手順で作成したプロジェクト ファイルのすべての内容です。

```xml
<Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
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
    <PlatformToolset>v141</PlatformToolset>
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

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild は、出力ファイルのディレクトリを作成してし、コンパイルし、Myproject.exe プログラムを生成するプロジェクトをリンクします。 ビルド プロセスが完了したら後、は、次のコマンドを使用して、デバッグ フォルダーからアプリケーションを実行します。

`myproject`

アプリケーションは、「こんにちは、from MSBuild!」を表示する必要があります。 コンソール ウィンドウに表示します。

## <a name="customizing-your-project"></a>プロジェクトのカスタマイズ

MSBuild では定義済みのビルド ターゲットを実行、ユーザー定義のプロパティを適用し、イベント、カスタム ツールを使用してビルド手順を行うことができます。 このセクションでは、次のタスクについて説明します。

- MSBuild を使用して、ビルド ターゲットを持つ。

- MSBuild を使用して、ビルド プロパティを使用します。

- 64 ビットのコンパイラおよびツールでは、MSBuild を使用します。

- 他のツールセットには、MSBuild を使用します。

- MSBuild のカスタマイズを追加します。

### <a name="using-msbuild-with-build-targets"></a>MSBuild とビルド ターゲットの併用

A*ビルド ターゲット*はビルド中に実行できる定義済みまたはユーザー定義のコマンドの名前付きセットです。 ターゲット コマンド ライン オプション (`/t`) を使用して、ビルド ターゲットを指定します。 `myproject`サンプル プロジェクト、定義済み**クリーン**ターゲットがデバッグ フォルダー内のすべてのファイルが削除し、新しいログ ファイルを作成します。

コマンド プロンプトで次のコマンドを入力して、`myproject` を削除します。

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>MSBuild とビルド プロパティの併用

プロパティ コマンド ライン オプション (`/p`) によって、プロジェクト ビルド ファイルのプロパティをオーバーライドできます。 `myproject` サンプル プロジェクトでは、`Configuration` プロパティによってリリース用またはデバッグ用のビルド構成が指定されます。 また、ビルド済みアプリケーションを実行するためのオペレーティング システムが、`Platform` プロパティで指定されます。

コマンド プロンプトで次のコマンドを入力して、32 ビット Windows で実行される予定の `myproject` アプリケーションのデバッグ ビルドを作成します。

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

`myproject` サンプル プロジェクトが、64 ビット Windows の構成と、別の `myplatform` という名前のカスタム オペレーティング システムの構成も定義していると想定します。

コマンド プロンプトで次のコマンドを入力して、64 ビット Windows で実行するリリース ビルドを作成します。

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

コマンド プロンプトで次のコマンドを入力して、`myplatform` のリリース ビルドを作成します。

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>MSBuild と 64 ビットのコンパイラおよびツールの併用

64 ビットの Windows に既定では Visual C をインストールした場合は、64 ビット x64 ネイティブおよびクロス ツールがインストールされます。 64 ビットのコンパイラおよびツールを使用して設定して、アプリケーションをビルドする MSBuild を構成することができます、`PreferredToolArchitecture`プロパティ。 このプロパティは、プロジェクトの構成とプラットフォームのプロパティに影響しません。 既定では、32 ビット版のツールが使用されます。 コンパイラおよびツールの 64 ビット バージョンを指定する次のプロパティ グループ要素を Myproject.vcxproj プロジェクト ファイル内の後に追加、 `Microsoft.Cpp.default.props` \<Import/> 要素。

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

64 ビット ツールを使用してアプリケーションをビルドするには、コマンド プロンプトで次のコマンドを入力します。

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>MSBuild を使用して、別のツールセット

ツールセットおよびライブラリがインストールされている Visual C の他のバージョンがある場合は、MSBuild は、現在の Visual C バージョンまたはその他のインストール済みのバージョンのアプリケーションを構築できます。 たとえば、Windows xp では、ビジュアルの C++ 11.0 ツールセットを指定する、Visual Studio 2012 をインストールしている場合、この次のプロパティ グループ要素を Myproject.vcxproj プロジェクト ファイル内の後に追加、 `Microsoft.Cpp.props` \<Import/> 要素。

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

ビジュアルの C++ 11.0 Windows XP ツールセットでプロジェクトをリビルドするには、次のコマンドを入力します。

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild のカスタマイズを追加します。

MSBuild では、ビルド プロセスをカスタマイズするさまざまな方法を提供します。 次のトピックでは、MSBuild プロジェクトにカスタム ビルド ステップ、ツール、およびイベントを追加する方法を示します。

- [方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)

- [方法: MSBuild プロジェクトでビルド イベントを使用する](../build/how-to-use-build-events-in-msbuild-projects.md)
