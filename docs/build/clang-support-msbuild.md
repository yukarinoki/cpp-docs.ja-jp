---
description: '詳細情報: Visual Studio プロジェクトでの Clang/LLVM のサポート'
title: Visual Studio の Visual Studio プロジェクトでの Clang/LLVM のサポート
ms.date: 06/02/2020
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 0008eddf41da672a820be02adb723af0b8673285
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163159"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Visual Studio プロジェクトでの Clang/LLVM のサポート

::: moniker range="<=msvc-150"

Visual Studio 2019 では、CMake プロジェクトと MSBuild プロジェクトの両方に対して Clang がサポートされます。

::: moniker-end

::: moniker range="msvc-160"

Visual Studio 2019 のバージョン 16.2 と Clang を使用して、Windows または Linux をターゲットとする C++ Visual Studio プロジェクト (MSBuild) を編集、ビルド、およびデバッグできます。

## <a name="install"></a>インストール

Visual Studio での IDE のサポートを十分に活用するために、Windows 用の最新の Clang コンパイラ ツールを使用することをお勧めします。 まだインストールしていない場合は、Visual Studio インストーラーを開いて、 **[C++ によるデスクトップ開発]** オプション コンポーネントの下にある **[Windows 用 C++ Clang コンパイラ]** を選択してインストールできます。 お使いのコンピューター上の既存の Clang インストールを使用する場合は、 **[v142 ビルド ツールの C++ Clang-cl]** オプション コンポーネントを選択します。 現時点では、Microsoft C++ 標準ライブラリには最低でも Clang 8.0.0 が必要です。Clang のバンドル バージョンは、最新の状態を維持するために、標準ライブラリの Microsoft 実装に含まれる更新プログラムによって自動的に更新されます。

![[個別のコンポーネント] タブが選択され、C++ Clang コンポーネントが表示されている Visual Studio インストーラーのスクリーンショット。](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Windows プロジェクトを Clang ツールを使用するように構成する

Visual Studio プロジェクトを Clang を使用するように構成するには、**ソリューション エクスプローラー** でプロジェクト ノードを右クリックし、 **[プロパティ]** を選択します。 通常は、最初にダイアログの上部にある **[すべての構成]** を選択する必要があります。 次に、 **[全般]**  >  **[プラットフォーム ツールセット]** で、 **[LLVM (clang-cl)]** を選択し、 **[OK]** を選択します。

![[構成プロパティ] > [全般] が選択され、[プラットフォーム ツールセット] と [L L V M (clang c l)] オプションが強調表示されている [プロパティ ページ] ダイアログ ボックスのスクリーンショット。](media/clang-msbuild-prop-page.png)

Visual Studio にバンドルされている Clang ツールを使用する場合は、追加の手順は必要ありません。 Windows プロジェクトの場合、Visual Studio では既定で Clang が [clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) モードで呼び出され、標準ライブラリの Microsoft 実装とリンクされます。 既定では、**clang-cl.exe** は *%VCINSTALLDIR%\\Tools\\Llvm\\bin\\* と *%VCINSTALLDIR%\\Tools\\Llvm\\x64\\bin\\* にあります。

Clang のカスタム インストールを使用する場合は、 **[プロジェクト]**  >  **[プロパティ]**  >  **[VC++ ディレクトリ]**  >  **[構成プロパティ]**  >  **[実行可能ファイルのディレクトリ]** で最初のディレクトリとして Clang のカスタム インストールのルートを追加するか、`LLVMInstallDir` プロパティの値を変更することで、変更を行うことができます。 詳細については、「[カスタム LLVM の場所を設定する](#custom_llvm_location)」を参照してください。

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Linux プロジェクトを Clang ツールを使用するように構成する

Linux プロジェクトの場合、Visual Studio では Clang GCC と互換性のあるフロントエンドが使用されます。 プロジェクトのプロパティとほぼすべてのコンパイラ フラグは同じです。

Visual Studio の Linux プロジェクトを Clang を使用するように構成するには:

1. **ソリューション エクスプローラー** でプロジェクト ノードを右クリックし、 **[プロパティ]** を選択します。
1. 通常は、最初にダイアログの上部にある **[すべての構成]** を選択する必要があります。
1. **[全般]** > **[プラットフォーム ツールセット]** で、Linux 用 Windows サブシステムを使用する場合は **[WSL_Clang_1_0]** を、リモート コンピューターまたは VM を使用する場合は **[Remote_Clang_1_0]** を選択します。
1. **[OK]** を押します。

![[構成プロパティ] > [全般] が選択され、[プラットフォーム ツールセット] と [L L V M (clang c l)] オプションが強調表示されているコンソール アプリ clang Visual Studio 2019 の [プロパティ ページ] ダイアログ ボックスのスクリーンショット。](media/clang-msbuild-prop-page.png)

Linux 上の Visual Studio では、既定で PATH 環境プロパティで検出された最初の Clang の場所が使用されます。 Clang のカスタム インストールを使用する場合は、`LLVMInstallDir` プロパティの値を変更するか、 **[プロジェクト]**  >  **[プロパティ]**  >  **[VC++ ディレクトリ]**  >  **[構成プロパティ]**  >  **[実行可能ファイルのディレクトリ]** でパスを置き換える必要があります。 詳細については、「[カスタム LLVM の場所を設定する](#custom_llvm_location)」を参照してください。

## <a name="set-a-custom-llvm-location"></a><a name="custom_llvm_location"></a> カスタム LLVM の場所を設定する

*Directory.build.props* ファイルを作成し、そのファイルをプロジェクトのルート フォルダーに追加することで、1 つ以上のプロジェクトに対する LLVM のカスタム パスを設定できます。 ソリューションのルート フォルダーに追加することで、ソリューションに含まれるすべてのプロジェクトに適用できます。 ファイルは次のようになります (実際のパスに置き換えてください)。

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>追加のプロパティの設定、編集、ビルド、およびデバッグ

Clang 構成を設定した後、プロジェクト ノードをもう一度右クリックし、 **[プロジェクトの再読み込み]** を選択します。 これで、Clang ツールを使用してプロジェクトのビルドとデバッグを実行できます。 Visual Studio によって、Clang コンパイラを使用していることが検出され、IntelliSense、強調表示、ナビゲーション、およびその他の編集機能が提供されます。 エラーと警告は **[出力] ウィンドウ** に表示されます。 Clang 構成のプロジェクトのプロパティ ページは MSVC とほぼ同じですが、コンパイラに依存するいくつかの機能 (編集や続行など) は Clang 構成では使用できません。 プロパティ ページでは利用できない Clang のコンパイラ オプションまたはリンカー オプションを設定するには、 **[構成プロパティ]**  >  **[C/C++ (またはリンカー)]**  >  **[コマンド ライン]**  >  **[追加のオプション]** のプロパティ ページで、手動で追加できます。

デバッグ時には、ブレークポイント、メモリとデータの視覚化、およびその他のほとんどのデバッグ機能を使用できます。  

![Clang のデバッグ](media/clang-debug-msbuild.png)

::: moniker-end
