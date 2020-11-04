---
title: 'チュートリアル: MSBuild を使用して Visual Studio C++ プロジェクトを作成する'
description: コマンドライン MSBuild C++ .vcxproj プロジェクトをゼロから作成する方法を示すチュートリアルです。
ms.date: 10/08/2020
helpviewer_keywords:
- 'MSBuild (C++), walkthrough: create a project'
ms.openlocfilehash: b3d4e8881f926e80e95832a27f7a5106ce876265
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924334"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成

このチュートリアルでは、コマンド プロンプトで MSBuild を使用して Visual Studio C++ プロジェクトをビルドする方法を示します。 Visual C++ コンソール アプリケーション用の XML ベースの *`.vcxproj`* プロジェクト ファイルを作成する方法を学習します。 プロジェクトのビルド後は、ビルド処理をカスタマイズする方法を学習します。

> [!IMPORTANT]
> Visual Studio IDE を使用し後でプロジェクト ファイルを編集する場合は、このアプローチは使用しないでください。 *`.vcxproj`* ファイルを手動で作成すると、特にプロジェクトのプロジェクト項目でワイルドカードが使用されている場合、Visual Studio IDE でそれを編集または読み込むことができなくなるおそれがあります。 詳細については、「[`.vcxproj` と `.props` のファイル構造](./reference/vcxproj-file-structure.md)」および「[`.vcxproj` ファイルとワイルドカード](./reference/vcxproj-files-and-wildcards.md)」を参照してください。

このチュートリアルでは、次の作業について説明します。

- プロジェクトの C++ ソース ファイルの作成。

- XML MSBuild プロジェクト ファイルの作成。

- MSBuild を使用したプロジェクトのビルド。

- MSBuild を使用したプロジェクトのカスタマイズ。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには、次の前提条件が必要です。

- **C++ によるデスクトップ開発** ワークロードがインストールされた Visual Studio のコピー。

- MSBuild システムの基本的な知識。

::: moniker range="msvc-140"

> [!NOTE]
> 下位レベルのビルド命令のほとんどは、プロパティ `$(VCTargetsPath)` に格納されている既定のターゲット フォルダーの下に定義されている *`.targets`* と *`.props`* のファイルに含まれています。 ここには、 *`Microsoft.Cpp.Common.props`* などのファイルがあります。 Visual Studio 2015 以前のバージョンの場合、これらのファイルの既定のパスは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* の下にあります。

::: moniker-end

::: moniker range="msvc-150"

> [!NOTE]
> 下位レベルのビルド命令のほとんどは、プロパティ `$(VCTargetsPath)` に格納されている既定のターゲット フォルダーの下に定義されている *`.targets`* と *`.props`* のファイルに含まれています。 ここには、 *`Microsoft.Cpp.Common.props`* などのファイルがあります。 Visual Studio 2017 の場合、これらのファイルの既定のパスは *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* の下にあります。 Visual Studio 2015 以前のバージョンの場合、これらは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* の下に格納されていました。

::: moniker-end

::: moniker range=">=msvc-160"

> [!NOTE]
> 下位レベルのビルド命令のほとんどは、プロパティ `$(VCTargetsPath)` に格納されている既定のターゲット フォルダーの下に定義されている *`.targets`* と *`.props`* のファイルに含まれています。 ここには、 *`Microsoft.Cpp.Common.props`* などのファイルがあります。 これらのファイルの既定のパスは *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\`* の下にあります。 `<version>` パス要素は、Visual Studio のバージョンに固有のものです。 Visual Studio 2019 の場合は *`v160`* です。 Visual Studio 2017 により、これらのファイルは *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* に格納されていました。 Visual Studio 2015 以前のバージョンの場合、これらは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* の下に格納されていました。

::: moniker-end

## <a name="create-the-c-source-files"></a>C++ ソース ファイルの作成

このチュートリアルでは、ソース ファイルとヘッダー ファイルがあるプロジェクトを作成します。 ソース ファイル *`main.cpp`* には、コンソール アプリケーションの `main` 関数が含まれています。 ヘッダー ファイル *`main.h`* には、 *`<iostream>`* ヘッダー ファイルをインクルードするためのコードが含まれています。 これらの C++ ファイルは、Visual Studio または Visual Studio Code などのテキスト エディターを使用して作成できます。

### <a name="to-create-the-c-source-files-for-your-project"></a>プロジェクトの C++ ソース ファイルを作成するには

1. プロジェクトのフォルダーを作成します。

1. *`main.cpp`* という名前のファイルを作成し、次のコードをファイルに追加します。

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

1. *`main.h`* という名前のファイルを作成し、次のコードをファイルに追加します。

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>プロジェクト ファイルXML MSBuild プロジェクト ファイルの作成

MSBuild のプロジェクト ファイルは、プロジェクトのルート要素 (`<Project>`) を含む XML ファイルです。 ビルドするサンプル プロジェクトでは、`<Project>` 要素に 7 個の子要素が含まれています。

- 3 個の項目グループ タグ (`<ItemGroup>`) は、プロジェクトの構成とプラットフォーム、ソース ファイル名、およびヘッダー ファイル名を指定しています。

- 3 個のインポート タグ (`<Import>`) は、Microsoft Visual C++ の設定の場所を指定しています。

- 1 個のプロパティ グループ タグ (`<PropertyGroup>`) は、プロジェクト設定を指定しています。

### <a name="to-create-the-msbuild-project-file"></a>MSBuild プロジェクト ファイルを作成するには

1. テキスト エディターを使用して *`myproject.vcxproj`* という名前のプロジェクト ファイルを作成し、ここに表示されているルート `<Project>` 要素を追加します (Visual studio 2015 を使用している場合は `ToolsVersion="14.0"`、Visual Studio 2017 を使用している場合は `ToolsVersion="15.0"`、Visual Studio 2019 を使用している場合は `ToolsVersion="16.0"` を使用します)。

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

   この要素を、次のプロシージャ ステップのルート `<Project>` タグの間に挿入します。

1. これらの 2 つの `<ProjectConfiguration>` 子要素を `<ItemGroup>` 要素に追加します。 この子要素は、32 ビットの Windows オペレーティング システムのデバッグおよびリリース構成を指定します。

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

1. このプロジェクトの既定の C++ 設定のパスを指定する `<Import>` 要素を追加します。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. 2 つのプロジェクト プロパティ (`<ConfigurationType>` と `<PlatformToolset>`) を指定するプロパティ グループ要素 (`<PropertyGroup>`) を追加します (`<PlatformToolset>` 値として、Visual studio 2015 を使用している場合は `v140`、Visual Studio 2017 を使用している場合は `v141`、Visual Studio 2019 を使用している場合は `v142` を使用します)。

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v142</PlatformToolset>
    </PropertyGroup>
    ```

1. このプロジェクトの現在の C++ 設定のパスを指定する `<Import>` 要素を追加します。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. `<ItemGroup>` 要素に `<ClCompile>` 子要素を追加します。 この子要素は、コンパイルする C/C++ ソース ファイルの名前を指定します。

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>` は " *ビルド ターゲット* " であり、既定のターゲット フォルダーで定義されています。

1. `<ItemGroup>` 要素に `<ClInclude>` 子要素を追加します。 この子要素は、C/C++ ソース ファイルに対応するヘッダー ファイルの名前を指定します。

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. このプロジェクトのターゲットを定義するファイルのパスを指定する `<Import>` 要素を追加します。

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>完成したプロジェクト ファイル

次のコードは、前の手順で作成したプロジェクト ファイルのすべての内容です (Visual Studio 2017 の場合は `ToolsVersion="15.0"`、Visual Studio 2015 の場合は `ToolsVersion="14.0"` を使用します)。

```xml
<Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
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
    <PlatformToolset>v142</PlatformToolset>
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

> `msbuild myproject.vcxproj /p:configuration=debug`

MSBuild によって、出力ファイルのフォルダーが作成され、プロジェクトがコンパイルおよびリンクされて *`Myproject.exe`* プログラムが生成されます。 ビルド処理が完了したら、次のコマンドを使用して、デバッグ フォルダーからアプリケーションを実行します。

> `myproject`

アプリケーションには、"Hello, from MSBuild!" と表示されます。 コンソール ウィンドウに表示します。

## <a name="customizing-your-project"></a>プロジェクトのカスタマイズ

MSBuild では、定義済みのビルド ターゲットを実行したり、ユーザー定義のプロパティを適用したりできるほか、カスタム ツール、イベント、およびビルド ステップを使用することができます。 このセクションでは、次のタスクについて説明します。

- MSBuild でのビルド ターゲットの使用。

- MSBuild でのビルド プロパティの使用。

- MSBuild での 64 ビットのコンパイラおよびツールの使用。

- MsBuild での別のツールセットの使用。

- MSBuild へのカスタマイズの追加。

### <a name="using-msbuild-with-build-targets"></a>MSBuild とビルド ターゲットの併用

*ビルド ターゲット* とは、ビルド時に実行できる定義済みまたはユーザー定義のコマンドの名前付きセットです。 ターゲット コマンドライン オプション ( **`/t`** ) を使用して、ビルド ターゲットを指定します。 `myproject` サンプル プロジェクトの場合は、定義済みの **`clean`** ターゲットによってデバッグ フォルダー内のすべてのファイルが削除され、新しいログ ファイルが作成されます。

コマンド プロンプトで、次のコマンドを入力して `myproject` を消去します。

> `msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>MSBuild とビルド プロパティの併用

プロパティ コマンド ライン オプション (`/p`) によって、プロジェクト ビルド ファイルのプロパティをオーバーライドできます。 `myproject` サンプル プロジェクトでは、`Configuration` プロパティによってリリース用またはデバッグ用のビルド構成が指定されます。 ビルド済みアプリケーションを実行するために使用するオペレーティング システムが、`Platform` プロパティで指定されます。

コマンド プロンプトで次のコマンドを入力して、32 ビット Windows で実行する `myproject` アプリケーションのデバッグ ビルドを作成します。

> `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

`myproject` サンプル プロジェクトが、64 ビット Windows の構成と、別の `myplatform` という名前のカスタム オペレーティング システムの構成も定義していると想定します。

コマンド プロンプトで次のコマンドを入力して、64 ビット Windows で実行するリリース ビルドを作成します。

> `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

コマンド プロンプトで次のコマンドを入力して、`myplatform` のリリース ビルドを作成します。

> `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>MSBuild と 64 ビットのコンパイラおよびツールの併用

64 ビットの Windows に Visual Studio をインストールした場合、64 ビットの x64 ネイティブおよびクロス ツールが既定でインストールされます。 MSBuild を構成して `PreferredToolArchitecture` プロパティを設定すると、アプリケーションのビルドに 64 ビットのコンパイラおよびツールを使用できます。 このプロパティは、プロジェクトの構成やプラットフォームのプロパティには影響しません。 既定では、32 ビット版のツールが使用されます。 64 ビット版のコンパイラおよびツールを指定するには、 *`Microsoft.Cpp.default.props`* ファイルの `<Import />` 要素の後に、このプロパティ グループ要素を *`Myproject.vcxproj`* プロジェクト ファイルに追加します。

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

64 ビット ツールを使用してアプリケーションをビルドするには、コマンド プロンプトで次のコマンドを入力します。

> `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>MsBuild での別のツールセットの使用

インストールされている Visual C++ の他バージョンのツールセットおよびライブラリがある場合、MSBuild では、現在の Visual C++ のバージョンまたはインストールされている別のバージョン用のアプリケーションをビルドできます。 たとえば Visual Studio 2012 がインストールされている場合に Windows XP 用の Visual C++ 11.0 ツールセットを指定するには、 *`Microsoft.Cpp.props`* ファイルの `<Import />` 要素の後にこのプロパティ グループ要素を *`Myproject.vcxproj`* プロジェクト ファイルに追加します。

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Visual C++ 11.0 Windows XP ツールセットでプロジェクトをリビルドするには、次のコマンドを入力します。

> `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild へのカスタマイズの追加

MSBuild では、さまざまな方法でビルド処理をカスタマイズできます。 これらの記事では、MSBuild プロジェクトにカスタム ビルド ステップ、ツール、イベントを追加する方法を示します。

- [方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](how-to-add-custom-build-tools-to-msbuild-projects.md)

- [方法: MSBuild プロジェクトでビルド イベントを使用する](how-to-use-build-events-in-msbuild-projects.md)
