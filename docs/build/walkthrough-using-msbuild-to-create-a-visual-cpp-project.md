---
title: 'チュートリアル: MSBuild を使用した Visual C プロジェクトの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/25/2018
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
ms.openlocfilehash: b2c5c3f7001a98572129baaf3ee35bb02b6458fd
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041212"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成

このチュートリアルでは、MSBuild を使用して、コマンド プロンプトでの Visual C プロジェクトをビルドする方法を示します。 C++ ソース ファイルと Visual C コンソール アプリケーション用の XML ベースのプロジェクト ファイルを作成する方法を学習します。 次に、プロジェクトをビルドしてから、ビルド処理をカスタマイズする方法を学習します。

このチュートリアルでは、次の作業について説明します。

- プロジェクトの C++ ソース ファイルの作成。

- XML MSBuild プロジェクト ファイルを作成します。

- MSBuild を使用して、プロジェクトをビルドします。

- MSBuild を使用して、プロジェクトをカスタマイズします。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するための要件は次のとおりです。

- Visual Studio でのコピー、 **C++ を使用したデスクトップ開発**ワークロードがインストールされています。

- MSBuild システムの全般についての理解。

> [!NOTE]
> Visual Studio IDE を使用して、後で、プロジェクト ファイルを編集する場合は、このアプローチを使わないでください。 .Vcxproj ファイルを手動で作成する場合、Visual Studio IDE できないことがありますを編集またはそれを読み込むプロジェクトは、プロジェクト項目でワイルドカードを使用している場合に特にです。

> [!NOTE]
> 低レベルのビルドの手順の大部分が含まれている、 **.targets**と **.props**プロパティに格納されている、VCTargets ディレクトリで定義されているファイル`$(VCTargetsPath)`です。 Visual Studio 2017 年 1 Enterprise Edition でこれらのファイルの既定のパスは c:\\%program Files (x86)\\Microsoft Visual Studio\\2017\\エンタープライズ\\Common7\\IDE\\VC\\VCTargets\\です。

## <a name="creating-the-c-source-files"></a>C++ ソース ファイルの作成

このチュートリアルでは、ソース ファイルとヘッダー ファイルがあるプロジェクトを作成します。 main.cpp という名前のソース ファイルには、コンソール アプリケーションの main 関数を含めます。 main.h という名前のヘッダー ファイルには、iostream ヘッダー ファイルをインクルードするためのコードを含めます。 Visual Studio Code などのエディターで、Visual Studio またはテキストを使用してこれらの C++ ファイルを作成できます。

### <a name="to-create-the-c-source-files-for-your-project"></a>プロジェクトの C++ ソース ファイルを作成するには

1. プロジェクトのディレクトリを作成します。

2. main.cpp という名前のファイルを作成し、このファイルに次のコードを追加します。

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

3. main.h という名前のファイルを作成し、このファイルに次のコードを追加します。

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>プロジェクト ファイルXML MSBuild プロジェクト ファイルの作成

MSBuild プロジェクト ファイルはプロジェクトのルート要素を含んだ XML ファイル (\<プロジェクト >)。 プロジェクトで、次の例、 \<Project > 要素には、7 つの子要素が含まれています。

- 3 つの項目グループ タグ (\<ItemGroup >) プロジェクトの構成とプラットフォーム、ソース ファイル名、およびヘッダー ファイルの名前を指定します。

- 3 つのインポート タグ (\<インポート >) の Microsoft Visual C 設定の場所を指定します。

- プロパティ グループ タグ (\<PropertyGroup >) プロジェクトの設定を指定します。

### <a name="to-create-the-msbuild-project-file"></a>MSBuild プロジェクト ファイルを作成するには

1. テキスト エディターを使用してという名前のプロジェクト ファイルを作成する`myproject.vcxproj`、次のルートを追加および\<プロジェクト > 要素。 ルートの次の手順で、要素を挿入\<Project > タグ。

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

2. 次の 2 つの追加\<ProjectConfiguration > 子要素、 \<ItemGroup > 要素。 この子要素は、32 ビットの Windows オペレーティング システムのデバッグおよびリリース構成を指定します。

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

3. 次の追加\<インポート/> このプロジェクトの既定の C++ 設定のパスを指定する要素。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

4. 次のプロパティ グループ要素の追加 (\<PropertyGroup >) 2 つのプロジェクト プロパティを指定します。

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v141</PlatformToolset>
    </PropertyGroup>
    ```

5. 次の追加\<インポート/> このプロジェクトの現在の C++ 設定のパスを指定する要素。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

6. 次の追加\<ClCompile > 子要素を\<ItemGroup > 要素。 この子要素は、コンパイルする C/C++ ソース ファイルの名前を指定します。

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > \<ClCompile > は、*ビルド ターゲット*で定義されていると、 **VCTargets**ディレクトリ。

7. 次の追加\<ClInclude > 子要素を\<ItemGroup > 要素。 この子要素は、C/C++ ソース ファイルに対応するヘッダー ファイルの名前を指定します。

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

8. 次の追加\<インポート > 要素をこのプロジェクトのターゲットを定義するファイルのパスを指定します。

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

MSBuild は、出力ファイルのディレクトリを作成およびコンパイルし、Myproject.exe プログラムを生成するようにプロジェクトをリンクします。 ビルド処理が完了したら、次のコマンドを使用してアプリケーションを実行します。

`myproject`

アプリケーションは、「こんにちは, from MSBuild!」を表示する必要があります。 コンソール ウィンドウに表示します。

## <a name="customizing-your-project"></a>プロジェクトのカスタマイズ

MSBuild では定義済みのビルド ターゲットを実行、ユーザー定義のプロパティを適用およびイベントのカスタム ツールを使用してビルド ステップを行うことができます。 このセクションでは、次のタスクについて説明します。

- ビルド ターゲットを持つ MSBuild を使用します。

- ビルド プロパティを持つ MSBuild を使用します。

- MSBuild を使用して、64 ビットのコンパイラとツールを使用します。

- 他のツールセットは、MSBuild を使用します。

- MSBuild のカスタマイズを追加します。

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

64 ビット Windows で、既定では Visual C をインストールする場合は、64 ビット x64 ネイティブおよびクロス ツールがインストールされます。 設定してアプリケーションをビルドする 64 ビットのコンパイラおよびツールを使用して MSBuild を構成することができます、`PreferredToolArchitecture`プロパティです。 このプロパティは、プロジェクトの構成とプラットフォームのプロパティには影響しません。 既定では、32 ビット版のツールが使用されます。 コンパイラおよびツールの 64 ビット バージョンを指定するを Myproject.vcxproj プロジェクト ファイル内の後に、次のプロパティ グループ要素を追加、 `Microsoft.Cpp.default.props` \<インポート/> 要素。

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

64 ビット ツールを使用してアプリケーションをビルドするには、コマンド プロンプトで次のコマンドを入力します。

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>他のツールセットの MSBuild の使用

ツールセットおよびライブラリがインストールされている Visual C の他のバージョンがある場合は、MSBuild は、現在の Visual C バージョンまたはその他のインストールされているバージョンのアプリケーションを構築できます。 たとえば、インストールされている[!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]を Windows XP の Visual の C++ 11.0 ツールセットを指定して、Microsoft.Cpp.props の後に、次のプロパティ グループ要素を Myproject.vcxproj プロジェクト ファイルに追加する、`<Import />`要素。

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Visual C++ 11.0 Windows XP ツールセットでプロジェクトをリビルドするには、次のコマンドのいずれかを入力します。

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

`msbuild myproject.vcxproj /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild のカスタマイズを追加します。

MSBuild では、ビルド プロセスをカスタマイズするさまざまな方法を提供します。 次のトピックでは、MSBuild プロジェクトにカスタム ビルド ステップ、ツール、およびイベントを追加する方法を示しています。

- [方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)

- [方法: MSBuild プロジェクトでビルド イベントを使用する](../build/how-to-use-build-events-in-msbuild-projects.md)
