---
title: '方法: コマンドラインでの 64 ビットの MSVC ツールセットを有効にします。'
ms.date: 03/29/2018
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
ms.openlocfilehash: 8436254a3d8c5c1dae018c2309ceaad7bd5b2408
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188913"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-msvc-toolset-on-the-command-line"></a>方法: 64 ビットを有効にする、コマンドラインで MSVC ツールセットが x64 にホストされています。

Visual Studio には、C++ コンパイラ、リンカー、およびその他のプラットフォームに固有のバージョンの 32 ビット、64 ビット、または ARM ベースの Windows オペレーティング システムで実行できるアプリの作成に使用できるツールが含まれています。 省略可能なその他の Visual Studio ワークロードでは、iOS、Android、Linux などの他のプラットフォームを対象とする C++ ツールを使用できます。 既定ビルド アーキテクチャでは、32 ビット、x86 でホストされているツールを使用して、32 ビットの x86 ネイティブ Windows コードをビルドします。 ただし、64 ビットのコンピューターがある可能性があります。 プロセッサと 64 ビットのコードを使用可能なメモリ領域の利点は、x86、x64、または ARM プロセッサ用のコードをビルドするときに、64 ビット、x64 でホストされているツールセットを使用して実行できます。

> [!NOTE]
> 各 Visual Studio のエディションに含まれている特定のツールについては、次を参照してください。 [Visual c Tools と Visual Studio エディションで機能](../overview/visual-cpp-tools-and-features-in-visual-studio-editions.md)します。
>
> Visual Studio IDE を使用して、64 ビット アプリケーションを作成する方法については、次を参照してください。[方法。Configure Visual C++ Projects to Target 64-Bit, x64 Platforms](how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)」(方法: Visual C++ プロジェクトを 64 ビット、x64 プラットフォーム用に設定する) を参照してください。

Visual Studio インストーラーで C++ ワークロードをインストールするときに 32 ビット、x86 ホスト、ネイティブおよびクロス コンパイラ ツール x86 および x64 のコードをビルドするが常にインストールします。 ユニバーサル Windows プラットフォームのワークロードを含める場合も、ARM コードを構築するためのクロス コンパイラの x86 でホストされているツールをインストールします。 64 ビット、x64 では、これらのワークロードをインストールするかどうか、プロセッサも 64 ビットのネイティブと取得クロス コンパイラおよびツールをビルド x86、x64、ARM コードします。 32 ビットおよび 64 ビット ツールは、同一のコードを生成しますが、64 ビット ツールは、プリコンパイル済みヘッダーのシンボルとプログラムの全体の最適化のより多くのメモリをサポート ([/GL](reference/gl-whole-program-optimization.md)と[/LTCG](reference/ltcg-link-time-code-generation.md)) オプション。 32 ビット ツールを使用する場合に、メモリの制限に発生した場合は、64 ビットのツールをお試しください。

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>64 ビットのホストされた開発者コマンド プロンプト ショートカットを使用してください。

Visual Studio は、64 ビット Windows オペレーティング システムにインストールするときに、その他の開発者コマンド プロンプト ショートカット、64 ビット、x64 でホストされているネイティブおよびクロス コンパイラを使用できます。 上の Windows 10 でこれらのコマンド プロンプトにアクセスする、**開始**メニューで、たとえば、Visual Studio のバージョンのフォルダーを開き**Visual Studio 2017**、x64 ネイティブまたはクロスツールのいずれかを選択開発者コマンド プロンプト。 上の Windows 8 の場合、これらのコマンド プロンプトにアクセスする、**開始** 画面で、開いている**すべてのアプリ**します。 Visual Studio のインストールされているバージョンの見出しの下を開く、 **Visual Studio**フォルダー (Visual Studio の以前のバージョンでという可能性がありますのある**Visual Studio Tools**)。 以前のバージョンの Windows では、次のように選択します**開始**、展開**すべてのプログラム**、バージョンのフォルダー **Visual Studio** (と Visual Studio の以前のバージョンで。**Visual Studio Tools**)。 詳細については、[開発者コマンド プロンプトのショートカット](building-on-the-command-line.md#developer_command_prompt_shortcuts)に関するトピックを参照してください。

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Vcvarsall.bat を使用して、ホステッド ビルドの 64 ビット アーキテクチャを設定するには

ネイティブのまたはクロス、vcvarsall.bat を実行して、コマンドラインでビルド構成を使用できますコンパイラ ツールのいずれかのコマンド ファイルです。 このコマンド ファイルがパスを構成し、特定の環境変数は、既存のコマンド プロンプト ウィンドウでのアーキテクチャを構築します。 具体的な手順については、次を参照してください。[開発者コマンド ファイルの場所](building-on-the-command-line.md#developer_command_file_locations)します。

## <a name="see-also"></a>関連項目

[64 ビット、x64 用の C++ プロジェクトの構成のターゲット](configuring-programs-for-64-bit-visual-cpp.md)<br/>
