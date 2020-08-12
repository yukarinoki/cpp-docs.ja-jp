---
title: '[詳細設定] プロパティページ (プロジェクト)'
ms.date: 08/10/2020
f1_keywords:
- VC.Project.VCConfiguration.VCToolsVersion
ms.description: Use the Advanced property page in Visual Studio 2019 to set various properties for C++ projects.
ms.openlocfilehash: 3d6694e44d3da4023998a0335cd06c85b353b2b1
ms.sourcegitcommit: 8140647370017b885432349ce89f187c3068b46a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "88144166"
---
# <a name="advanced-property-page"></a>[詳細設定] プロパティページ

::: moniker range="<=vs-2017"

[詳細設定] プロパティページは、Visual Studio 2019 以降で使用できます。 このバージョンのドキュメントを表示するには、この記事の Visual Studio の **[バージョン]** セレクター コントロールを Visual Studio 2019 に設定してください。 このページの目次の一番上にあります。

::: moniker-end

::: moniker range="vs-2019"

[詳細設定] プロパティページは、Visual Studio 2019 以降で使用できます。

## <a name="advanced-properties"></a>高度なプロパティ

- **ターゲットファイル拡張子**

   ビルド出力に使用するファイル拡張子を指定します。 *`.exe`* アプリケーションでは、スタティックライブラリおよび dll 用に既定値が使用さ *`.lib`* *`.dll`* れます。

- **消去時に削除する拡張子**

   **[ビルド]** メニューの **[消去]** を選択すると、プロジェクトの構成がビルドされる中間ディレクトリからファイルが削除されます。 このプロパティで指定した拡張子を持つファイルは、**クリーン**の実行時または再構築時に削除されます。 ビルドシステムは、中間ディレクトリにこれらの拡張子を持つすべてのファイルを削除します。 また、ビルドの場所に関係なく、ビルドの既知の出力も削除されます。 (ファイルなどの中間出力を含み *`.obj`* ます)。このプロパティには、ワイルドカード文字を指定できます。

   プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>」を参照してください。

- **ビルド ログ ファイル**

   では、プロジェクトをビルドするたびに作成されるログファイルの既定以外の場所を指定できます。 既定の場所はマクロによって指定され `$(IntDir)$(MSBuildProjectName).log` ます。

   プロジェクト マクロを使用して、ディレクトリの場所を変更できます。 「[ビルドコマンドとプロパティの一般的なマクロ](common-macros-for-build-commands-and-properties.md)」を参照してください。

- **推奨されるビルドツールのアーキテクチャ**

   X86 または x64 のビルドツールを使用するかどうかを指定します。

- **デバッグライブラリを使用する**

   デバッグビルドとリリースビルドのどちらを作成するかを指定します。

- **Unity (ジャンボ) ビルドを有効にする**

   コンパイル前に、多数の C++ ソースファイルを1つ以上のファイルに結合する、より高速なビルド処理を可能にします。 これらの結合ファイルは*unity*ファイルと呼ばれます。 Unity ゲームエンジンとは無関係です。

- **コンテンツを OutDir にコピーする**

   プロジェクトの*コンテンツ*としてマークされている項目をプロジェクトの出力ディレクトリ () にコピーし `$(OutDir)` ます。 この設定により、展開が簡単になります。 このプロパティは、Visual Studio 2019 バージョン16.7 以降で使用できます。

- **プロジェクト参照を OutDir にコピーする**

   実行可能ファイル (DLL および EXE ファイル) プロジェクト参照項目をプロジェクトの出力ディレクトリ () にコピーし `$(OutDir)` ます。 C++/CLI ( [`/clr`](clr-common-language-runtime-compilation.md) ) プロジェクトでは、このプロパティは無視されます。 代わりに、各プロジェクト参照の [**ローカルにコピー** ] プロパティは、出力ディレクトリにコピーされるかどうかを制御します。 この設定を使用すると、ローカル展開を簡単に行うことができます。 Visual Studio 2019 バージョン16.7 以降で使用できます。

- **プロジェクト参照のシンボルを OutDir にコピーする**

   プロジェクト参照項目の PDB ファイルを、プロジェクト参照の実行可能項目と共にプロジェクトの出力ディレクトリ () にコピーし `$(OutDir)` ます。 このプロパティは、C++/CLI プロジェクトに対して常に有効です。 この設定により、デバッグの展開が簡単になります。 Visual Studio 2019 バージョン16.7 以降で使用できます。

- **C++ ランタイムを OutDir にコピーする**

   ランタイム Dll をプロジェクトの出力ディレクトリ () にコピー `$(OutDir)` します。 この設定を使用すると、ローカル展開を簡単に行うことができます。 Visual Studio 2019 バージョン16.7 以降で使用できます。

- **MFC の使用法**

   Mfc プロジェクトが MFC DLL との間で静的または動的にリンクするかどうかを指定します。 非 MFC プロジェクトでは、[**標準の Windows ライブラリを使用**する] を選択して、mfc に含まれる Win32 ライブラリをリンクします。

   プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>」を参照してください。

- **文字セット**

   を設定するかどうか `_UNICODE` `_MBCS` を定義します。 該当する場合は、リンカーのエントリ ポイントにも影響します。

   プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>」を参照してください。

- **プログラム全体の最適化**

   [`/GL`](gl-whole-program-optimization.md)コンパイラオプションとリンカーオプションを指定し [`/LTCG`](ltcg-link-time-code-generation.md) ます。 既定では、デバッグ構成ではプログラム全体の最適化が無効になっており、リリース構成では有効になっています。

- **MSVC ツールセットのバージョン**

   プロジェクトのビルドに使用される MSVC ツールセットの完全バージョンを指定します。 ツールセットには、さまざまな更新プログラムとプレビュー版がインストールされている場合があります。 ここでは、どれを使用するかを指定できます。

## <a name="ccli-properties"></a>C++/CLI のプロパティ

- **共通言語ランタイム サポート**

   [`/clr`](clr-common-language-runtime-compilation.md)コンパイラオプションを使用します。

   プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>」を参照してください。

- **.NET Framework 対象バージョン**

   マネージド プロジェクトでは、ターゲットにする .NET Framework バージョンを指定します。

- **マネージド インクリメンタル ビルドを有効にする**

   マネージプロジェクトの場合、このオプションを使用すると、アセンブリを生成するときに外部の可視性を検出できます。 マネージプロジェクトへの変更が他のプロジェクトから参照できない場合、依存プロジェクトは再構築されません。 マネージインクリメンタルビルドを使用すると、マネージプロジェクトを含むソリューションのビルド時間を大幅に向上させることができます。

::: moniker-end
