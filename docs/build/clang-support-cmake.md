---
title: プロジェクトでのクラン/LLVM のサポート
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: 46bfe788c13df3a37dd9cba654d16cfe4c3fe177
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323181"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>プロジェクトでのクラン/LLVM のサポート

::: moniker range="<=vs-2017"

Clang のサポートは、Visual Studio 2019 で利用できます。

::: moniker-end

::: moniker range="vs-2019"

Clang と共に Visual Studio を使用して、Windows または Linux を対象とする C++ CMake プロジェクトを編集およびデバッグできます。

**Windows**: Visual Studio 2019 バージョン 16.1 には、Windows を対象とする CMake プロジェクトで Clang/LLVM を使用した編集、ビルド、およびデバッグのサポートが含まれています。

**Linux**: Linux CMake プロジェクトの場合、特別な Visual Studio サポートは必要ありません。 ディストリビューションのパッケージ マネージャを使用して Clang をインストールし、CMakeLists.txt ファイルに適切なコマンドを追加できます。

## <a name="install"></a>インストール

Visual Studio での IDE のサポートを最大限に活用するために、Windows 用の最新の Clang コンパイラ ツールを使用することをお勧めします。 これらをまだインストールしていない場合は、Visual Studio インストーラーを開き **、C++** オプション コンポーネントを使用したデスクトップ開発で**Windows 用 C++ Clang コンパイラ**を選択してインストールできます。 カスタム Clang インストールを使用する場合は **、v142 ビルド ツール コンポーネントの C++ Clang-cl を**確認してください。

![Clang コンポーネントのインストール](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>新しい構成を作成する

CMake プロジェクトに新しい Clang 構成を追加するには:

1. **ソリューション エクスプローラー**で CMakeLists.txt を右クリックし、[**プロジェクトの CMake 設定]** を選択します。

1. [**構成]** で、[**構成の追加**] ボタンを押します。

   ![構成を追加する](media/cmake-add-config-icon.png)

1. 目的の Clang 構成を選択し (Windows と Linux 用に個別の Clang 構成が提供されることに注意 **)、Select**キーを押します。

   ![CMake クランの構成](media/cmake-clang-configuration.png)

1. この構成を変更するには **、CMake 設定エディタ**を使用します。 詳細については、「 [CMake ビルド設定のカスタマイズ](customize-cmake-settings.md)」を参照してください。

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang を使用するように既存の構成を変更する

Clang を使用するように既存の構成を変更するには、次の手順を実行します。

1. **ソリューション エクスプローラー**で CMakeLists.txt を右クリックし、[**プロジェクトの CMake 設定]** を選択します。

1. [**全般**] で、[**ツールセット**] ドロップダウンを選択し、目的の Clang ツールセットを選択します。

   ![CMake Clang ツールセット](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>カスタム Clang の場所

既定では、Visual Studio は次の 2 つの場所で Clang を検索します。

- (ウィンドウズ)Visual Studio インストーラーに付属する Clang/LLVM の内部インストールされたコピー。
- (ウィンドウズとLinux)PATH 環境変数。

CMake 設定で**cMake変数CMAKE_C_COMPILER**と**CMAKE_CXX_COMPILER**を設定して、別の場所**を**指定できます。

![CMake Clang ツールセット](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang 互換モード

Windows 構成の場合、CMake は既定で[Clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf)モードで Clang を呼び出し、標準ライブラリのマイクロソフト実装とリンクします。 既定では **、clang-cl.exe**は`C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`に存在します。

これらの値は **、[CMake の設定]** の [**変数とキャッシュ]** で変更できます。 [**詳細変数を表示する]** をクリックします。 下にスクロールして **[ CMAKE_CXX_COMPILER**] を見つけ、[**参照**] ボタンをクリックして別のコンパイラ パスを指定します。

## <a name="edit-build-and-debug"></a>編集、ビルド、およびデバッグ

Clang 構成を設定した後、プロジェクトをビルドおよびデバッグできます。 Visual Studio は、Clang コンパイラを使用していることを検出し、IntelliSense、強調表示、ナビゲーション、およびその他の編集機能を提供します。 エラーと警告は**出力ウィンドウ**に表示されます。

デバッグ時には、ブレークポイント、メモリとデータの視覚化、およびその他のほとんどのデバッグ機能を使用できます。 エディット コンティニュなどのコンパイラ依存機能の一部は、Clang 構成では使用できません。

![CMake クラン デバッグ](media/clang-debug-visualize.png)

::: moniker-end
