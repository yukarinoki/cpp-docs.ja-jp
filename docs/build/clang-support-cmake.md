---
title: Visual Studio CMake プロジェクトでの Clang/LLVM のサポート
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: e23da02a0c3af624ddb30cec8dbb5afda55660c9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919580"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Visual Studio CMake プロジェクトでの Clang/LLVM のサポート

::: moniker range="<=msvc-150"

Clang サポートは Visual Studio 2019 で使用できます。

::: moniker-end

::: moniker range="msvc-160"

Visual Studio を Clang と一緒に使用して、 Windows または Linux を対象とする C++ CMake プロジェクトを編集およびデバッグすることができます。

**Windows** :Visual Studio 2019 バージョン 16.1 には、Windows を対象とする CMake プロジェクトで Clang/LLVM を使用した編集、ビルド、およびデバッグのためのサポートが含まれています。

**Linux** :Linux CMake プロジェクトでは、Visual Studio の特別なサポートは必要ありません。 お使いのディストリビューションのパッケージ マネージャーを使用して Clang をインストールし、CMakeLists.txt ファイルに適切なコマンドを追加することができます。

## <a name="install"></a>インストール

Visual Studio で最適な IDE サポートを利用するには、Windows 用の最新の Clang コンパイラ ツールを使用することをお勧めします。 それをまだインストールしていない場合は、Visual Studio インストーラーを開いて、 **[C++ によるデスクトップ開発]** オプション コンポーネントの下にある **[Windows 用 C++ Clang コンパイラ]** を選択してインストールできます。 カスタムの Clang インストールを使用する場合は、 **[C++ Clang-cl for v142 build tools]** コンポーネントにチェックマークを付けてください。

![Clang コンポーネントのインストール](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>新しい構成を作成する

新しい Clang 構成を CMake プロジェクトに追加するには、次のようにします。

1. **ソリューション エクスプローラー** の CMakeLists.txt を右クリックし、 **[CMake settings for project]\(プロジェクトの CMake 設定\)** を選択します。

1. **[構成]** で、 **[構成の追加]** ボタンをクリックします。

   ![構成の追加](media/cmake-add-config-icon.png)

1. 目的の Clang 構成を選択します (Windows と Linux に別々の Clang 構成が用意されていることに注意してください)。その後、 **[選択]** を押します。

   ![CMake Clang 構成](media/cmake-clang-configuration.png)

1. この構成を変更するには、 **CMake 設定エディター** を使用します。 詳細については、「[Visual Studio で CMake のビルド設定をカスタマイズする](customize-cmake-settings.md)」を参照してください。

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang を使用するように既存の構成を変更する

Clang を使用するように既存の構成を変更するには、次の手順を実行します。

1. **ソリューション エクスプローラー** の CMakeLists.txt を右クリックし、 **[CMake settings for project]\(プロジェクトの CMake 設定\)** を選択します。

1. **[General]\(全般\)** で、 **[ツールセット]** ドロップダウンを選択し、目的の Clang ツールセットを選択します。

   ![[ツールセット] が選択され、clang cl x 86 が強調表示されている [全般] ダイアログ ボックスのスクリーンショット。](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>カスタムの Clang の場所

既定では、Visual Studio は次の 2 つの場所から Clang を検索します。

- (Windows) Visual Studio インストーラーに付属する Clang/LLVM の内部インストール コピー。
- (Windows および Linux) PATH 環境変数。

**[CMake Settings]\(CMake の設定\)** で **CMAKE_C_COMPILER** および **CMAKE_CXX_COMPILER** の CMake 変数を設定して、別の場所を指定できます。

![C Make C X X コンパイラが強調表示されている [CMake の設定] ダイアログ ボックスのスクリーンショット。](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang 互換モード

Windows 構成の場合、CMake は既定では [clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) モードで Clang を呼び出し、標準ライブラリの Microsoft 実装とリンクします。 既定では、 **clang-cl.exe** は `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin` にあります。

これらの値は、 **[CMake 変数とキャッシュ]** ( **[CMake Settings]\(CMake の設定\)** の下) で変更できます。 **[高度な変数を表示]** をクリックします。 下にスクロールして **CMAKE_CXX_COMPILER** を見つけ、 **[参照]** ボタンをクリックして別のコンパイラ パスを指定します。

## <a name="edit-build-and-debug"></a>編集、ビルド、およびデバッグ

Clang 構成を設定したら、プロジェクトをビルドしてデバッグすることができます。 Visual Studio は、Clang コンパイラが使用されていることを検出し、IntelliSense、強調表示、ナビゲーション、およびその他の編集機能を提供します。 エラーおよび警告は、 **[出力]** ウィンドウに表示されます。

デバッグ時には、ブレークポイント、メモリとデータの視覚化、およびその他のほとんどのデバッグ機能を使用できます。 エディット コンティニュなどの一部のコンパイラ依存機能は、Clang 構成では使用できません。

![CMake Clang のデバッグ](media/clang-debug-visualize.png)

::: moniker-end
