---
title: Visual Studio で CMake Linux プロジェクトを作成する
description: Visual Studio で Linux CMake プロジェクトを作成する方法
ms.date: 08/06/2020
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 5753dbb37c11686becb3e141261284b68468a3bc
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507947"
---
# <a name="create-a-cmake-linux-project-in-visual-studio"></a>Visual Studio で CMake Linux プロジェクトを作成する

::: moniker range="vs-2015"
Linux サポートは Visual Studio 2017 以降で使用できます。 これらのバージョンのドキュメントを表示するには、目次の上にある **[バージョン]** ドロップダウンを **Visual Studio 2017** または **Visual Studio 2019** に設定します。
::: moniker-end

::: moniker range=">=vs-2017"

クロスプラットフォームのプロジェクトまたはオープンソースにするプロジェクトには、CMake を使用することをお勧めします。 CMake プロジェクトを使用すると、Windows、Linux 用 Windows サブシステム (WSL)、リモート システムで、同じソース コードをビルドしてデバッグすることができます。

## <a name="before-you-begin"></a>開始する前に

まず、CMake コンポーネントが含まれる Visual Studio Linux ワークロードがインストールされていることを確認します。 それは、Visual Studio インストーラーの **[C++ による Linux 開発]** ワークロードに含まれています。 それがインストールされているかわからない場合は、「[Visual Studio で C++ の Linux ワークロードをインストールする](download-install-and-setup-the-linux-development-workload.md)」を参照してください。

また、リモート マシンに次のものがインストールされていることを確認します。

- gcc
- gdb
- rsync
- zip
- ninja-build (Visual Studio 2019 以降)
::: moniker-end

::: moniker range="vs-2017"
Visual Studio で CMake を利用するには、CMake 3.8 で導入されたサーバー モードに対応する必要があります。 Microsoft から提供されている CMake バリアントについては、[https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) から最新のビルド済みバイナリをダウンロードします。

バイナリは `~/.vs/cmake` にインストールされます。 バイナリを配布すると、プロジェクトが自動的に再生成されます。 *CMakeSettings.json* の `cmakeExecutable` フィールドで指定する CMake が無効 (存在しない、またはサポートされていないバージョン) で、かつビルド済みバイナリが存在している場合は、Visual Studio では `cmakeExecutable` が無視され、ビルド済みバイナリが使われます。

Visual Studio 2017 では、CMake プロジェクトを最初から作成することはできませんが、次のセクションで説明するように、既存の CMake プロジェクトが含まれるフォルダーを開くことはできます。
::: moniker-end

::: moniker range=">=vs-2019"
Visual Studio 2019 を使用すると、リモート Linux システムまたは WSL でビルドとデバッグを行うことができ、そのシステムで CMake が呼び出されます。 ターゲット マシンに Cmake バージョン 3.14 以降がインストールされている必要があります。

ターゲット マシンに CMake の最新バージョンがあることを確認します。 ディストリビューションの既定のパッケージ マネージャーで提供されるバージョンは、しばしば最新ではなく、Visual Studio で必要なすべての機能はサポートされていません。 Visual Studio 2019 では、Linux システムに CMake の最新バージョンがインストールされているかどうかを検出します。 見つからない場合、Visual Studio のエディター ウィンドウの上部に、情報バーが表示されます。 [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) から CMake をインストールすることができます。

Visual Studio 2019 を使用すると、CMake プロジェクトを最初から作成することも、既存の CMake プロジェクトを開くこともできます。 新しい CMake プロジェクトを作成するには、以下の手順のようにします。 または、既に CMake プロジェクトがある場合は、「[CMake プロジェクト フォルダーを開く](#open-a-cmake-project-folder)」に進んでください。

## <a name="create-a-new-linux-cmake-project"></a>新しい Linux CMake プロジェクトの作成

Visual Studio 2019 で新しい Linux CMake プロジェクトを作成するには:

1. Visual Studio で **[ファイル]、[新しいプロジェクト]** の順に選択するか、**Ctrl + Shift + N** キーを押します。
1. **[言語]** を **[C++]** に設定し、「CMake」を検索します。 その後、 **[次へ]** をクリックします。 **[名前]** と **[場所]** を入力し、 **[作成]** を選択します。

または、Visual Studio 2019 で独自の CMake プロジェクトを開くこともできます。 次のセクションでは、その方法について説明します。

Visual Studio では、実行可能ファイルの名前と、要求される最小の CMake バージョンのみを使用して、最小限の *CMakeLists.txt* ファイルが作成されます。 このファイルは手動で自由に編集できます。Visual Studio によって変更が上書きされることはありません。

Visual Studio 2019 で CMake スクリプトを理解し、編集し、作成する方法については、次のリソースを参照してください。

- [Visual Studio での CMake 向けのエディター内での文書作成](https://devblogs.microsoft.com/cppblog/in-editor-documentation-for-cmake-in-visual-studio/)
- [CMake スクリプトのコード ナビゲーション](https://devblogs.microsoft.com/cppblog/code-navigation-for-cmake-scripts/)
- [CMake プロジェクトでのファイルとターゲットの追加、削除、名前変更が簡単に](https://devblogs.microsoft.com/cppblog/easily-add-remove-and-rename-files-and-targets-in-cmake-projects/)
::: moniker-end

::: moniker range=">=vs-2017"

## <a name="open-a-cmake-project-folder"></a>CMake プロジェクト フォルダーを開く

既存の CMake プロジェクトを含むフォルダーを開くと、Visual Studio では CMake キャッシュの変数が使用され、IntelliSense とビルドが自動的に構成されます。 ローカルの構成とデバッグの設定は、JSON ファイルに格納されます。 必要に応じて、Visual Studio を使用している他のユーザーとこれらのファイルを共有することもできます。

Visual Studio では、*CMakeLists.txt* ファイルは変更されません。 これにより、同じプロジェクトで作業している他のユーザーが、既存のツールを引き続き使用できます。 Visual Studio では、*CMakeLists.txt* (場合によっては *CMakeSettings.json*) の編集が保存されると、キャッシュが再生成されます。 **既存のキャッシュ**構成が使用されている場合、Visual Studio によるキャッシュの変更は行われません。

Visual Studio での CMake のサポートに関する一般的な情報については、「[Visual Studio の CMake プロジェクト](../build/cmake-projects-in-visual-studio.md)」を参照してください。 それを読んでから、ここでの作業を進めてください。

最初に、メイン メニューから **[ファイル]**  >  **[開く]**  >  **[フォルダー]** の順に選択するか、[開発者コマンド プロンプト](../build/building-on-the-command-line.md) ウィンドウに「`devenv.exe <foldername>`」と入力します。 開いたフォルダーには、ソース コードと共に *CMakeLists.txt* ファイルが入っているはずです。

次のサンプルでは、単純な *CMakeLists.txt* ファイルと .cpp ファイルを確認できます。

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

*CMakeLists.txt*:

```txt
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="next-steps"></a>次の手順

[Linux CMake プロジェクトを構成する](cmake-linux-configure.md)

## <a name="see-also"></a>関連項目

[Visual Studio の CMake プロジェクト](../build/cmake-projects-in-visual-studio.md)<br/>
::: moniker-end
