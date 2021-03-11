---
description: '詳細情報: Visual Studio プロジェクトでの Clang/LLVM のサポート'
title: Visual Studio プロジェクトでの Clang/LLVM のサポート
ms.date: 02/05/2021
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 31f79280e51bcf277bd3a992c4d7d2e39e679f30
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236622"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Visual Studio プロジェクトでの Clang/LLVM のサポート

::: moniker range="<=msvc-150"

Visual Studio 2019 では、CMake プロジェクトと MSBuild プロジェクトの両方に対して Clang がサポートされます。

::: moniker-end

::: moniker range="msvc-160"

Visual Studio 2019 のバージョン 16.2 以降と Clang を使用して、Windows または Linux をターゲットとする C++ Visual Studio プロジェクト (MSBuild) を編集、ビルド、デバッグできます。

## <a name="install"></a>インストール

Visual Studio での IDE のサポートを十分に活用するために、Windows 用の最新の Clang コンパイラ ツールを使用することをお勧めします。 そのツールをまだインストールしていない場合は、Visual Studio インストーラーを開いて、 **[C++ によるデスクトップ開発]** オプション コンポーネントの下にある **[Windows 用 C++ Clang コンパイラ]** を選択してインストールできます。 お使いのコンピューター上の既存の Clang インストールを使用することもできます。その場合は、 **[v142 ビルド ツールの C++ Clang-cl]** オプション コンポーネントを選択します。

Microsoft C++ 標準ライブラリ用には Clang 8.0.0 以上が必要です。

![[個別のコンポーネント] タブが選択され、C++ Clang コンポーネントが表示されている Visual Studio インストーラーのスクリーンショット。](media/clang-install-vs2019.png)

新しいバージョンの Visual Studio では、Clang ツールセットの新しいバージョンが提供されます。 バンドルされたバージョンの Clang は自動的に更新され、この標準ライブラリの Microsoft による実装の更新に合わせて最新の状態に保たれます。 たとえば、Visual Studio 2019 バージョン 16.9 には Clang v11 が含まれています。

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Windows プロジェクトを Clang ツールを使用するように構成する

Visual Studio プロジェクトを Clang を使用するように構成するには、**ソリューション エクスプローラー** でプロジェクト ノードを右クリックし、 **[プロパティ]** を選択します。 通常は、最初にダイアログの上部にある **[すべての構成]** を選択する必要があります。 次に、 **[全般]**  >  **[プラットフォーム ツールセット]** で、 **[LLVM (clang-cl)]** を選択し、 **[OK]** を選択します。

![[構成プロパティ] > [全般] が選択され、[プラットフォーム ツールセット] と [L L V M (clang c l)] オプションが強調表示されている [プロパティ ページ] ダイアログ ボックスのスクリーンショット。](media/clang-msbuild-prop-page.png)

Visual Studio にバンドルされている Clang ツールを使用する場合は、追加の手順は必要ありません。 Windows プロジェクトの場合、Visual Studio の既定では、Clang が [clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) モードで呼び出されます。 それがこの標準ライブラリの Microsoft による実装とリンクされます。 既定では、**clang-cl.exe** は *%VCINSTALLDIR%\\Tools\\Llvm\\bin\\* と *%VCINSTALLDIR%\\Tools\\Llvm\\x64\\bin\\* にあります。

Clang のカスタム インストールを使用する場合は、 **[プロジェクト]**  >  **[プロパティ]**  >  **[VC++ ディレクトリ]**  >  **[構成プロパティ]**  >  **[実行可能ファイルのディレクトリ]** で最初のディレクトリとして Clang のカスタム インストールのルートを追加するか、`LLVMInstallDir` プロパティの値を変更することで、変更を行うことができます。 詳細については、「[カスタム LLVM の場所を設定する](#custom_llvm_location)」を参照してください。

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Linux プロジェクトを Clang ツールを使用するように構成する

Linux プロジェクトの場合、Visual Studio では Clang GCC と互換性のあるフロントエンドが使用されます。 プロジェクトのプロパティとほぼすべてのコンパイラ フラグは同じです。

Visual Studio の Linux プロジェクトを Clang を使用するように構成するには:

1. **ソリューション エクスプローラー** でプロジェクト ノードを右クリックし、 **[プロパティ]** を選択します。
1. 通常は、最初にダイアログの上部にある **[すべての構成]** を選択する必要があります。
1. Linux 用 Windows サブシステム (WSL) を使用する場合は、 **[全般]**  >  **[プラットフォーム ツールセット]** で **[WSL_Clang_1_0]** を選択します。 リモート コンピューターまたは VM を使用する場合は、 **[Remote_Clang_1_0]** を選択します。
1. **[OK]** を押します。

![[構成プロパティ] > [全般] が選択され、[プラットフォーム ツールセット] と [L L V M (clang c l)] オプションが強調表示されているコンソール アプリ clang Visual Studio 2019 の [プロパティ ページ] ダイアログ ボックスのスクリーンショット。](media/clang-msbuild-prop-page.png)

Linux 上の Visual Studio の場合、PATH 環境プロパティで検出された最初の Clang の場所が既定で使用されます。 Clang のカスタム インストールを使用する場合は、`LLVMInstallDir` プロパティの値を変更するか、 **[プロジェクト]**  >  **[プロパティ]**  >  **[構成プロパティ]**  >  **[VC++ ディレクトリ]**  >  **[実行可能ファイルのディレクトリ]** でパスを入力する必要があります。 詳細については、「[カスタム LLVM の場所を設定する](#custom_llvm_location)」を参照してください。

## <a name="set-a-custom-llvm-location"></a><a name="custom_llvm_location"></a> カスタム LLVM の場所を設定する

1 つ以上のプロジェクトに対して LLVM へのカスタム パスを設定するには、*Directory.build.props* ファイルを作成します。 次に、そのファイルを任意のプロジェクトのルート フォルダーに追加します。 ソリューションのルート フォルダーに追加することで、ソリューションに含まれるすべてのプロジェクトに適用できます。 ファイルは次のようになります (ただし、LLVM パスは実際のものを使用してください)。

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>C:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

このプロパティとカスタム LLVM ツールセットのバージョンを組み合わせることができます。 詳細については、「[カスタム LLVM ツールセットのバージョンを設定する](#custom_llvm_toolset)」を参照してください。

## <a name="set-a-custom-llvm-toolset-version"></a><a name="custom_llvm_toolset"></a>カスタム LLVM ツールセットのバージョンを設定する

Visual Studio 2019 バージョン 16.9 以降では、LLVM のカスタム ツールセット バージョンを設定できます。 Visual Studio でプロジェクトにこのプロパティを設定するには、次のようにします。

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](./working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** > **[全般]** プロパティ ページを選択します。

1. **[プラットフォーム ツールセット]** プロパティがまだ設定されていない場合は、 *[LLVM (clang-cl)]* に変更します。

1. **[構成プロパティ]** > **[詳細]** プロパティ ページを選択します。

1. **[LLVM ツールセット バージョン]** プロパティを自分が使用するバージョンに変更し、 **[OK]** を選択して変更を保存します。

**[LLVM ツールセット バージョン]** プロパティは、LLVM プラットフォーム ツールセットが選択されている場合にのみ表示されます。

1 つ以上のプロジェクトに対してツールセット バージョンを設定するには、*Directory.build.props* ファイルを作成します。 次に、そのファイルを任意のプロジェクトのルート フォルダーに追加します。 ソリューションのルート フォルダーに追加することで、ソリューションに含まれるすべてのプロジェクトに適用します。 ファイルは次のようになります (ただし、LLVM パスは実際のものを使用してください)。

```xml
<Project>
  <PropertyGroup>
    <LLVMToolsVersion>11.0.0</LLVMToolsVersion>
  </PropertyGroup>
</Project>
```

このプロパティとカスタム LLVM の場所を組み合わせることもできます。 たとえば、*Directory.build.props* ファイルは次のようになります。

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>C:\MyLLVMRootDir</LLVMInstallDir>
    <LLVMToolsVersion>11.0.0</LLVMToolsVersion>
  </PropertyGroup>
</Project>
```

*Directory.build.props* ファイルを追加すると、プロジェクトのプロパティ ページ ダイアログに既定としての設定が表示されます。 ただし、Visual Studio でこれらのプロパティを変更すると、*Directory.build.props* ファイル内の設定がオーバーライドされます。

## <a name="set-additional-properties-edit-build-and-debug"></a>追加のプロパティの設定、編集、ビルド、およびデバッグ

Clang 構成を設定した後、プロジェクト ノードをもう一度右クリックし、 **[プロジェクトの再読み込み]** を選択します。 これで、Clang ツールを使用してプロジェクトのビルドとデバッグを実行できます。 Visual Studio によって、Clang コンパイラを使用していることが検出され、IntelliSense、強調表示、ナビゲーション、およびその他の編集機能が提供されます。 エラーおよび警告は、 **[出力]** ウィンドウに表示されます。 Clang 構成のプロジェクト プロパティ ページは、MSVC のものに似ています。 ただし、エディット コンティニュなどの一部のコンパイラ依存機能は、Clang 構成では使用できません。 プロパティ ページで使用できない Clang コンパイラまたはリンカー オプションを設定することができます。 プロパティ ページの **[構成プロパティ]**  >  **[C/C++] (または [リンカー])**  >  **[コマンド ライン]**  >  **[追加のオプション]** で、手動で追加します。

デバッグ時には、ブレークポイント、メモリとデータの視覚化、およびその他のほとんどのデバッグ機能を使用できます。  

![Clang のデバッグ](media/clang-debug-msbuild.png)

::: moniker-end
