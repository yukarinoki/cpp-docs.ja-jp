---
title: '方法: コマンドラインで 64 ビット Visual C ツールセットを有効にする |Microsoft ドキュメント'
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22290cdf9418299cbba51ab1d893d60cb790e2e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369141"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>方法: 64 ビットを有効にする、x64 には、コマンドラインでの Visual C ツールセットがホストされています。

Visual C には、コンパイラ、リンカー、およびその他のプラットフォーム固有のバージョン 32 ビット、64 ビット、または ARM ベースの Windows オペレーティング システムで実行できるアプリの作成に使用できるツールが含まれています。 省略可能なその他の Visual Studio ワークロードでは、iOS、Android、および Linux など、他のプラットフォームを対象とする C++ のツールを使用できます。 既定のビルド アーキテクチャでは、32 ビット、x86 ホスト ツールを使用して、32 ビット、x86 ネイティブの Windows コードをビルドします。 ただし、64 ビットのコンピューターがある可能性があります。 プロセッサと 64 ビット コードを使用可能なメモリ領域の利点を行うには、x86、x64、または ARM プロセッサ用のコードをビルドするときに、64 ビット、x64 でホストされるツールセットを使用します。

> [!NOTE]
> Visual C エディションごとに含まれている特定のツールについては、次を参照してください。 [Visual c ツールおよび Visual Studio のエディションで機能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)します。
>
> Visual Studio IDE を使用して、64 ビット アプリケーションを作成する方法については、次を参照してください。[する方法: Visual c プロジェクトをターゲットの 64 ビット、x64 プラットフォーム](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)です。

Visual Studio インストーラーで C++ ワークロードをインストールするときに 32 ビット、x86 ホスト、ネイティブおよびクロス コンパイラ ツール x86 および x64 のコードをビルドするが常にインストールします。 ユニバーサル Windows プラットフォームのワークロードを含める場合、ARM コードを構築するための x86 ホストでクロス コンパイラ ツールもインストールされます。 64 ビット x64 には、これらのワークロードをインストールするかどうかは、プロセッサも 64 ビットのネイティブを取得し、コンパイラおよびツールをビルド x86、x64、ARM クロス コーディングします。 32 ビットおよび 64 ビット ツールには、同じコードが生成されますが、64 ビット ツールで、プリコンパイル済みヘッダーのシンボルと全体プログラム最適化のためのより多くのメモリのサポート ([/GL](../build/reference/gl-whole-program-optimization.md)と[/LTCG](../build/reference/ltcg-link-time-code-generation.md)) オプション。 32 ビット ツールを使用する場合に、メモリの制限に発生した場合は、64 ビット ツールを再試行してください。

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>64 ビット ホストされた開発者コマンド プロンプト ショートカットを使用します。

Visual Studio がインストールすると、64 ビット Windows オペレーティング システムで 64 ビット、x64 ホスト ネイティブおよびクロス コンパイラの他の開発者コマンド プロンプト ショートカットのとおりです。 上の Windows 10 でこれらのコマンド プロンプトにアクセスする、**開始**メニューで、たとえば、Visual Studio のバージョンのフォルダーを開き**Visual Studio 2017**、x64 ネイティブまたはクロスツールのいずれかを選択し、開発者コマンド プロンプトです。 上の Windows 8 の場合は、これらのコマンド プロンプトにアクセスする、**開始** 画面で、開いている**すべてのアプリ**です。 インストールされているバージョンの Visual Studio の下で、開く、 **Visual Studio**フォルダー (Visual Studio の旧バージョンではこれが付けられて**Visual Studio Tools**)。 以前のバージョンの Windows では、次のように選択します**開始**、展開**すべてのプログラム**、ご使用のバージョンのフォルダー **Visual Studio** (および、Visual Studio の以前のバージョンで。**Visual Studio Tools**)。 詳細については、[開発者コマンド プロンプトのショートカット](../build/building-on-the-command-line.md#developer-command-prompt-shortcuts)に関するトピックを参照してください。

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Vcvarsall.bat を使用してホストされるビルドの 64 ビット アーキテクチャを設定するには

ネイティブのまたはクロス コンパイラ ツール、vcvarsall.bat を実行して、コマンドラインでビルド構成を使用できますのいずれかのコマンド ファイルです。 このコマンド ファイルがパスを構成し、特定の環境変数は、既存のコマンド プロンプト ウィンドウでのアーキテクチャを構築します。 具体的な手順については、次を参照してください。 [Developer コマンド ファイルと場所](../build/building-on-the-command-line.md#developer-command-files-and-locations)です。

## <a name="see-also"></a>関連項目

[64 ビット、x64 ターゲット用の Visual C の構成](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
