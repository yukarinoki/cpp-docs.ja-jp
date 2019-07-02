---
title: Visual Studio の CMake プロジェクトで CLANG/LLVM サポート
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++
ms.openlocfilehash: 6773d9cdb076ef305ba635306f3bc9c6575d2203
ms.sourcegitcommit: b233f05adae607f75815111006a771c432df5a9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67517107"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Visual Studio の CMake プロジェクトで CLANG/LLVM サポート

::: moniker range="<=vs-2017"

Clang サポートは、Visual Studio 2019 で使用できます。

::: moniker-end

::: moniker range="vs-2019"

Clang と Visual Studio を使用するには編集およびデバッグC++そのターゲットの Windows または Linux の CMake プロジェクトします。

**Windows**:Visual Studio 2019 16.1 のバージョンには、編集、ビルド、および CLANG/LLVM で Windows をターゲットとする CMake プロジェクトのデバッグのサポートが含まれています。 

**Linux**:Linux CMake プロジェクトでは、特殊な Visual Studio のサポートは必要ありません。 Clang のディストリビューションのパッケージ マネージャーを使用してをインストールして、CMakeLists.txt ファイルに適切なコマンドを追加できます。

## <a name="install"></a>インストール

Visual Studio での最適な IDE のサポート、Windows の最新の Clang コンパイラ ツールの使用をお勧めします。 Visual Studio インストーラーを開き、選択してインストールできるものをいない場合**Windows Clang コンパイラ** **によるデスクトップ開発C++** オプションのコンポーネント。

![Clang コンポーネントのインストール](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>新しい構成を作成します。

CMake プロジェクトに新しい Clang 構成を追加するには

1. CMakeLists.txt を右クリックして**ソリューション エクスプ ローラー**選択**プロジェクトの CMake 設定**します。

1. **構成**、キーを押して、**構成の追加**ボタン。

   ![構成を追加します。](media/cmake-add-config-icon.png)

1. Clang の必要な構成 (Windows および Linux 用個別 Clang 構成が提供されるメモ) キーを押します選択**選択**:

   ![CMake Clang 構成](media/cmake-clang-configuration.png)

1. この構成を変更するには、使用、 **CMake の設定エディター**します。 詳細については、次を参照してください。 [CMake のカスタマイズは、Visual Studio での設定をビルド](customize-cmake-settings.md)します。

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang を使用する既存の構成を変更します。

Clang を使用する既存の構成を変更するには、次の手順を実行します。

1. CMakeLists.txt を右クリックして**ソリューション エクスプ ローラー**選択**プロジェクトの CMake 設定**します。

1. **全般**選択、**ツールセット**ドロップダウン目的 Clang ツールセットを選択。

   ![CMake Clang ツールセット](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Clang のカスタムの場所

既定では、Visual Studio の 2 か所に Clang を探します。

- (Windows)Visual Studio インストーラーに付属する CLANG/LLVM の内部的にインストール済みコピー。
- (Windows および Linux)PATH 環境変数。

別の場所を指定するを設定、 **CMAKE_C_COMPILER**と**CMAKE_CXX_COMPILER**で CMake 変数**CMake 設定**:

![CMake Clang ツールセット](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang 互換性モード

Windows の構成では、既定で CMake が Clang でを呼び出す[clang cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf)モードと標準ライブラリの Microsoft 実装をリンクします。 既定では、 **clang cl.exe**にある`C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`します。

 これらの値を変更する**CMake 設定** **CMake 変数とキャッシュ**します。 クリックして**変数の詳細の表示**します。 まで下にスクロール**CMAKE_CXX_COMPILER**、順にクリックして、**参照**別のコンパイラのパスを指定するボタンをクリックします。

## <a name="edit-build-and-debug"></a>編集、ビルド、およびデバッグ

Clang の構成を設定した後は、ビルドし、プロジェクトをデバッグできます。 Visual Studio では、Clang コンパイラを使用しているし、IntelliSense、強調表示、ナビゲーション、およびその他の編集機能を提供することを検出します。 エラーおよび警告が表示されます、**出力ウィンドウ**します。

デバッグする場合、ブレークポイント、メモリとデータの視覚化、およびその他のほとんどのデバッグ機能を使用することができます。 Clang の構成の編集と続行などの一部のコンパイラに依存する機能が利用できません。

![CMake Clang のデバッグ](media/clang-debug-visualize.png)

::: moniker-end
