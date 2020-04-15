---
title: プロジェクトでのクラン/LLVM のサポート
ms.date: 08/30/2019
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 8d7d7fec979d3e7b8f665e56094ee1c309e3b686
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323117"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>ビジュアル スタジオ プロジェクトでの Clang/LLVM のサポート

::: moniker range="<=vs-2017"

CMake プロジェクトと MSBuild プロジェクトの両方の Clang サポートは、Visual Studio 2019 で使用できます。

::: moniker-end

::: moniker range="vs-2019"

Clang で Visual Studio 2019 バージョン 16.2 を使用して、Windows または Linux を対象とする C++ Visual Studio プロジェクト (MSBuild) を編集、ビルド、およびデバッグできます。

## <a name="install"></a>インストール

Visual Studio での IDE のサポートを最大限に活用するために、Windows 用の最新の Clang コンパイラ ツールを使用することをお勧めします。 これらをまだインストールしていない場合は、Visual Studio インストーラーを開き **、C++** オプション コンポーネントを使用したデスクトップ開発で**Windows 用 C++ Clang ツールを**選択してインストールできます。 マシン上で既存の Clang インストールを使用する場合は **、v142 ビルド ツール用の C++ Clang-cl を選択します。** オプションコンポーネント。 現在、C++ 標準ライブラリには少なくとも Clang 8.0.0 が必要です。Clang のバンドルバージョンは、標準ライブラリのマイクロソフト実装の更新プログラムに最新の状態を維持するために自動的に更新されます。

![Clang コンポーネントのインストール](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Clang ツールを使用するように Windows プロジェクトを構成する

Clang を使用するように Visual Studio プロジェクトを構成するには、**ソリューション エクスプローラー**でプロジェクト ノードを右クリックし、[**プロパティ]** を選択します。 通常は、ダイアログの上部にある **[すべての構成**] を選択します。 次に、[**全般** > **プラットフォーム ツールセット**] で **[LLVM (clang-cl)]** を選択し **、[OK] をクリックします**。

![Clang コンポーネントのインストール](media/clang-msbuild-prop-page.png)

Visual Studio にバンドルされている Clang ツールを使用している場合は、追加の手順は必要ありません。 Windows プロジェクトの場合、既定では[、Clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf)モードで Clang が呼び出され、標準ライブラリのマイクロソフト実装とリンクされます。 既定では **、clang-cl.exe**は`C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`に存在します。

カスタム Clang インストールを使用している場合は、プロジェクト**プロパティ** > **VC++ DIrectories** > **構成プロパティ** > **実行可能ディレクトリ**を変更**Project** > するには、カスタム Clang インストール ルートを最初のディレクトリとして追加`LLVMInstallDir`するか、プロパティの値を変更します。 詳細については[、「カスタム LLVM の場所を設定](#custom_llvm_location)する」を参照してください。

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Clang ツールを使用するように Linux プロジェクトを構成する

Linux プロジェクトの場合、Clang GCC 互換フロントエンドが使用されます。 プロジェクトプロパティとほぼすべてのコンパイラフラグが同一です

Clang を使用するように Visual Studio Linux プロジェクトを構成するには、次の手順を実行します。

1. **ソリューション エクスプローラ**でプロジェクト ノードを右クリックし、[**プロパティ ]** をクリックします。
1. 通常は、ダイアログの上部にある **[すべての構成**] を選択します。
1. [**汎用**>**プラットフォーム ツールセット**] で **、Linux**用 Windows サブシステムを使用している場合はWSL_Clang_1_0を選択し、リモート コンピューターまたは VM を使用している場合は**Remote_Clang_1_0**を選択します。
1. **[OK]** をクリックします。

![Clang コンポーネントのインストール](media/clang-msbuild-prop-page.png)

Linux では、既定では、Visual Studio は、PATH 環境プロパティで最初に検出された Clang の場所を使用します。 カスタム Clang`LLVMInstallDir`インストールを使用している場合は、プロパティの値を変更するか、または **[プロジェクト** > プロパティ**VC++ DIrectories** > **構成プロパティ** > **Properties** > **の実行可能ディレクトリ**] の下のパスを置き換える必要があります。 詳細については[、「カスタム LLVM の場所を設定](#custom_llvm_location)する」を参照してください。

## <a name="set-a-custom-llvm-location"></a><a name="custom_llvm_location"></a>カスタム LLVM の場所を設定する

1 つ以上のプロジェクトに対してカスタム パスを設定するには *、Directory.build.props*ファイルを作成し、そのファイルを任意のプロジェクトのルート フォルダーに追加します。 ルート ソリューション フォルダーに追加して、ソリューション内のすべてのプロジェクトに適用できます。 ファイルは次のようになります (ただし、実際のパスを置き換えます)。

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>追加のプロパティの設定、編集、ビルド、デバッグ

Clang 構成を設定したら、プロジェクト ノードをもう一度右クリックし、[**プロジェクトの再読み込み**] を選択します。 Clang ツールを使用してプロジェクトをビルドおよびデバッグできるようになりました。 Visual Studio は、Clang コンパイラを使用していることを検出し、IntelliSense、強調表示、ナビゲーション、およびその他の編集機能を提供します。 エラーと警告は**出力ウィンドウ**に表示されます。 Clang 構成のプロジェクト プロパティ ページは MSVC のプロパティ ページと非常によく似ていますが、エディット コンティニュなどのコンパイラ依存機能の中には、Clang 構成では使用できないものがあります。 プロパティ ページで使用できない Clang コンパイラ またはリンカー オプションを設定するには、[**構成プロパティ** > **C/C++ (またはリンカー)** > **コマンド ライン** > **の追加オプション**] の下にあるプロパティ ページで手動で追加できます。

デバッグ時には、ブレークポイント、メモリとデータの視覚化、およびその他のほとんどのデバッグ機能を使用できます。  

![クランデバッグ](media/clang-debug-msbuild.png)

::: moniker-end
