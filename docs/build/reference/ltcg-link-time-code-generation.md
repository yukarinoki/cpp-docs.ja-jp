---
title: /LTCG (リンク時のコード生成)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
ms.openlocfilehash: 68c12cc7666da489870da1cacacc5053aeca5b51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523215"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (リンク時のコード生成)

使用 **/LTCG**プログラム全体の最適化を実行するまたは最適化のガイド付きプロファイル (PGO) インストルメンテーションを作成、トレーニングを実行およびガイド付きプロファイルを作成するには、ビルドを最適化します。

## <a name="syntax"></a>構文

> **/LTCG**[**:**{**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

これらのオプションは、Visual Studio 2015 以降で非推奨とされます。

> **/LTCG:**{**:PGINSTRUMENT**|**:PGOPTIMIZE**|**:PGUPDATE**}<br/>

### <a name="arguments"></a>引数

**増分**<br/>
(省略可能)プロジェクト全体ではなく、編集によって影響を受けるファイルのセットにプログラム全体の最適化またはリンク時コード生成 (LTCG) をリンカーがのみ適用されることを指定します。 既定では、このフラグが設定されていない場合に **/LTCG**指定すると、プロジェクト全体は、プログラム全体の最適化を使用してリンクされます。

**:NOSTATUS** &AMP;#124; **状態**<br/>
(省略可能)リンカーが、リンクの何パーセントが完了しているかを示す進行状況インジケーターを表示するかどうかを指定します。 既定では、この状態情報は表示されません。

**OFF**<br/>
(省略可能)リンク時コード生成を無効にします。 この動作は場合と同じ **/LTCG**がコマンドラインで指定されていません。

**:PGINSTRUMENT**<br/>
(省略可能)このオプションは、Visual Studio 2015 以降では非推奨です。 代わりに、 **/LTCG**と[/GENPROFILE または/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)プロファイル ガイド付き最適化のためにインストルメントされたビルドを生成します。 インストルメント化された実行から収集されるデータは、最適化されたイメージの作成に使用されます。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)します。 このオプションの短い形式は **/LTCG:PGI**します。

**:PGOPTIMIZE**<br/>
(省略可能)このオプションは、Visual Studio 2015 以降では非推奨です。 代わりに、 **/LTCG**と[/USEPROFILE](useprofile.md)最適化されたイメージを作成します。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)します。 このオプションの短い形式は **/LTCG:PGO**します。

**:PGUPDATE**<br/>
(省略可能)このオプションは、Visual Studio 2015 以降では非推奨です。 代わりに、 **/LTCG**と **/USEPROFILE**最適化されたイメージを再構築します。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)します。 このオプションの短い形式は **/LTCG:PGU**します。

## <a name="remarks"></a>Remarks

**/LTCG**オプション、コンパイラを呼び出すし、プログラム全体の最適化を実行するようにリンカーに指示します。 または、ガイド付きプロファイルの最適化を実行することもできます。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)します。

次の例外の PGO の組み合わせにリンカー オプションを追加することはできません **/LTCG**と **/USEPROFILE**の以前の PGO の初期化の組み合わせで指定されたいない **/LTCG**と **/GENPROFILE**オプション。

- [/BASE](../../build/reference/base-base-address.md)

- [/FIXED](../../build/reference/fixed-fixed-base-address.md)

- **/LTCG**

- [/MAP](../../build/reference/map-generate-mapfile.md)

- [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)

- [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)

- [/OUT](../../build/reference/out-output-file-name.md)

- [/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)

- [/PDB](../../build/reference/pdb-use-program-database.md)

- [/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)

- [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md)

リンカー オプションと共に指定されている、 **/LTCG**と **/GENPROFILE** PGO を初期化するためのオプションを使用してビルドするときに指定する必要はありません **/LTCG**と **/USEPROFILE**。 それらは暗黙的に指定します。

この記事の残りの部分について説明します **/LTCG**リンク時コード生成の観点から。

**/LTCG**で暗黙的に指定[/GL](../../build/reference/gl-whole-program-optimization.md)します。

使用してコンパイルされたモジュールが、渡される場合、リンカーはリンク時コード生成を呼び出す **/GL**や MSIL モジュール (を参照してください[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md))。 明示的に指定しない場合 **/LTCG**を渡す場合 **/GL** MSIL モジュールをリンカーでは、最終的にリンカーはこれを検出しを使用して、リンクを再起動または **/LTCG**します。 明示的に指定 **/LTCG**を渡す場合 **/GL**と MSIL モジュールを最速の可能性があるのため、リンカーは、パフォーマンスをビルドします。

さらに高速なパフォーマンスを使用して **/LTCG: 増分**します。 このオプションを指定すると、リンカーは、プロジェクト全体ではなく、ソース ファイルの変更によって影響を受ける一連のファイルのみを再び最適化します。 これにより、リンクに必要な時間を大幅に削減できます。 これは、インクリメンタル リンクと同じオプションではありません。

**/LTCG**で使用するために有効でない[/incremental](../../build/reference/incremental-link-incrementally.md)します。

ときに **/LTCG**を使用してコンパイルされたモジュールをリンクするために使用[/Og](../../build/reference/og-global-optimizations.md)、 [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、 [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、または[/Ox](../../build/reference/ox-full-optimization.md)、次の最適化が実行されます。

- クロス モジュールのインライン展開

- 手続き間レジスタ割り当て (64 ビット オペレーティング システムのみ)

- カスタム呼び出し規約 (x86 のみ)

- 小規模な TLS 変位 (x86 のみ)

- スタックの二重配置 (x86 のみ)

- 強化されたメモリの曖昧性除去 (グローバル変数および入力パラメーターのより優れた干渉の情報)

> [!NOTE]
> リンカーは、ある最適化は、各関数のコンパイルに使用されたかを決定し、リンク時に同じ最適化を適用します。

使用して **/LTCG**と **/Ogt**二重配置の最適化をによりします。

場合 **/LTCG**と **/Ogs**は指定すると、二重配置は実行されません。 サイズ用にコンパイルされたいくつかの関数と速度、向けアプリケーションで、機能の大部分にコンパイルされたかどうか (などを使用して、[最適化](../../preprocessor/optimize.md)プラグマ)、コンパイラ、二重配置を呼び出す場合に、サイズの最適化された関数二重のアラインメントを必要とする関数。

コンパイラは、すべての関数の呼び出しサイトの特定、コンパイラは関数の呼び出し規約の明示的な修飾子が無視され、関数の呼び出し規約を最適化しようとしています。

- レジスタにパラメーターを渡す

- 配置のパラメーターの順序の変更

- 未使用のパラメーターを削除します。

関数は、関数ポインターを通じて呼び出された場合、またはを使用してコンパイルされたモジュールの外部から関数を呼び出す場合 **/GL**コンパイラは関数の呼び出し規約を最適化しようとはしません。

> [!NOTE]
> 使用する場合 **/LTCG**を再定義`mainCRTStartup`アプリケーションは、グローバル オブジェクトが初期化される前に実行されるユーザー コードに関連する予期しない動作を持つことができます。 この問題に対処する 3 つの方法はあります: 再定義しない`mainCRTStartup`、格納しているファイルはコンパイルされません`mainCRTStartup`を使用して **/LTCG**、またはグローバル変数およびオブジェクトを静的に初期化します。

### <a name="ltcg-and-msil-modules"></a>/LTCG モジュールと MSIL モジュール

[/GL](../../build/reference/gl-whole-program-optimization.md) と [/clr](../../build/reference/clr-common-language-runtime-compilation.md) を使用してコンパイルされたモジュールは、 **/LTCG** が指定されている場合にリンカーへの入力として使用できます。

- **/LTCG**ネイティブ オブジェクトのファイルを受け入れることができるし、混合ネイティブ/マネージ オブジェクト ファイル (を使用してコンパイル **/clr**)。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

- **/LTCG:PGI**を使用してコンパイルしたネイティブ モジュールは受け入れません **/GL**と **/clr**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 参照してください[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)します。

1. 選択、**構成プロパティ** > **全般**プロパティ ページ。

1. **[プログラム全体の最適化]** プロパティを変更します。

適用することも **/LTCG**を選択して特定のビルドに**ビルド** > **ガイド付き最適化のプロファイル**メニュー バーのプロファイルのいずれかを選択するかプロジェクトのショートカット メニューの ガイド付き最適化オプション。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)
