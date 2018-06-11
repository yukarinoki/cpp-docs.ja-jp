---
title: /LTCG (リンク時コード生成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.LinkTimeCodeGeneration
- VC.Project.VCConfiguration.WholeProgramOptimization
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
- /ltcg
- VC.Project.VCCLCompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- link-time code generation in C++ linker
- /LTCG linker option
- -LTCG linker option
- LTCG linker option
ms.assetid: 788c6f52-fdb8-40c2-90af-4026ea2cf2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc4266e8b01201226c53584bed9f90ed9dcabef7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703734"
---
# <a name="ltcg-link-time-code-generation"></a>/LTCG (リンク時のコード生成)

使用して **/LTCG**全体プログラム最適化を実行するか作成してプロファイル ガイド付き最適化の (PGO) のインストルメンテーション、トレーニングを実行します。 ガイド付きプロファイルの作成、ビルドを最適化します。

## <a name="syntax"></a>構文

> **/LTCG**[**:**{**INCREMENTAL**|**NOSTATUS**|**STATUS**|**OFF**}]<br/>

これらのオプションは、Visual Studio 2015 以降で使用されていません。

> **/LTCG:**{**:PGINSTRUMENT**|**:PGOPTIMIZE**|**:PGUPDATE**}<br/>

### <a name="arguments"></a>引数

**増分**(省略可能)<br/>
プロジェクト全体ではなく、編集によって影響を受けるファイルのセット全体プログラム最適化またはリンク時コード生成 (LTCG) をリンカーがのみ適用されることを指定します。 既定では、このフラグが設定されていない場合に **/LTCG**指定すると、プロジェクト全体がプログラム全体の最適化を使用してリンクされているとします。

**NOSTATUS** &#124; **ステータス**(省略可能)<br/>
リンカーが、リンクの何パーセントが完了を示す進行状況インジケーターを表示するかどうかを指定します。 既定では、この状態情報は表示されません。

**オフ**(省略可能)<br/>
リンク時コード生成を無効にします。 この動作は場合と同じ **/LTCG**がコマンドラインで指定されていません。

**:PGINSTRUMENT** (省略可能)<br/>
このオプションは、Visual Studio 2015 以降では推奨されません。 代わりに、 **/LTCG**と[/GENPROFILE または/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)プロファイル ガイド付き最適化のためにインストルメントされたビルドを生成します。 インストルメントされた実行から収集されるデータは、最適化されたイメージの作成に使用されます。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)です。 このオプションの短い形式は **/LTCG:PGI**です。

**:PGOPTIMIZE** (省略可能)<br/>
このオプションは、Visual Studio 2015 以降では推奨されません。 代わりに、 **/LTCG**と[/USEPROFILE](useprofile.md)最適化されたイメージを作成します。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。 このオプションの短い形式は **/LTCG:PGO**です。

**:PGUPDATE** (省略可能)<br/>
このオプションは、Visual Studio 2015 以降では推奨されません。 代わりに、 **/LTCG**と **/USEPROFILE**最適化されたイメージを再構築します。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。 このオプションの短い形式は **/LTCG:PGU**です。

## <a name="remarks"></a>コメント

**/LTCG**オプションは、コンパイラを呼び出してプログラム全体の最適化を実行するようにリンカーに指示します。 または、ガイド付きプロファイルの最適化を実行することもできます。 詳細については、次を参照してください。[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)です。

次の例外を除き、PGO を組み合わせたものにリンカー オプションを追加することはできません **/LTCG**と **/USEPROFILE**の以前の PGO 初期化の組み合わせで指定されたいない **/LTCG**と **/GENPROFILE**オプション。

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

と共に指定されている任意のリンカー オプション、 **/LTCG**と **/GENPROFILE** PGO を初期化するためにオプションを使用してビルドするときに指定する必要はありません **/LTCG**と **/USEPROFILE**。 それらは暗黙的に指定します。

この記事の残りの部分について説明します **/LTCG**リンク時コード生成の観点からです。

**/LTCG**で暗黙的な[/GL](../../build/reference/gl-whole-program-optimization.md)です。

使用してコンパイルされたモジュールに渡される場合、リンカーがリンク時コード生成を呼び出す **/GL**または MSIL モジュール (を参照してください[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md))。 明示的に指定しない場合 **/LTCG**を渡す場合 **/GL** MSIL モジュールをリンカー、最終的にリンカーはこれを検出しを使用して、リンクを再起動または **/LTCG**です。 明示的に指定 **/LTCG**を渡す場合 **/GL** MSIL モジュールをリンカーに最高のパフォーマンスをビルドするとします。

高速パフォーマンスを得るには、使用 **/LTCG: インクリメンタル**です。 このオプションを指定すると、リンカーは、プロジェクト全体ではなく、ソース ファイルの変更によって影響を受ける一連のファイルのみを再び最適化します。 これにより、リンクに必要な時間を大幅に削減できます。 これはインクリメンタル リンクとして同じオプションではありません。

**/LTCG**で使用するためには不適切な[/incremental](../../build/reference/incremental-link-incrementally.md)です。

ときに **/LTCG**を使用してコンパイルされたモジュールをリンクするために使用[/Og](../../build/reference/og-global-optimizations.md)、 [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、 [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、または[/Ox](../../build/reference/ox-full-optimization.md)では、次の最適化が実行されます。

- モジュール間のインライン展開

- 関数を超えたレジスタの割り当て (64 ビット オペレーティング システムのみ)

- カスタム呼び出し規約 (x86 のみ)

- 小さい TLS の変位 (x86 のみ)

- スタックの二重配置 (x86 のみ)

- 強化されたメモリあいまいさを排除 (グローバル変数および入力パラメーターについてより詳細な干渉の情報)

> [!NOTE]
> リンカーは、各関数のコンパイルに使用する最適化を判断し、リンク時に同じ最適化機能を適用します。

使用して **/LTCG**と **/Ogt**二重配置の最適化が発生します。

場合 **/LTCG**と **/Ogs**指定すると、二重配置は実行されません。 サイズにコンパイルされたいくつかの関数で、速度のほとんどのアプリケーションで関数がコンパイルされるかどうか (たとえばを使用して、[最適化](../../preprocessor/optimize.md)プラグマ)、コンパイラ倍揃えを呼び出す場合に、サイズの最適化された関数double 型のアラインメントを必要とする関数。

場合は、コンパイラは、すべての関数の呼び出しサイトを識別できます、コンパイラは関数に明示的な呼び出し規約の修飾子を無視し、関数の呼び出し規約を最適化しようとしています。

- レジスタにパラメーターを渡す

- 配置のパラメーターの順序を変更します。

- 未使用のパラメーターを削除します。

関数は、関数ポインターを通じて呼び出された場合、またはを使用してコンパイルされたモジュールの外部から関数を呼び出した場合 **/GL**コンパイラが関数の呼び出し規約を最適化しません。

> [!NOTE]
> 使用する場合 **/LTCG**を再定義`mainCRTStartup`アプリケーションは、グローバル オブジェクトが初期化される前に実行されるユーザー コードに関連付けられている、予期しない動作を持つことができます。 この問題に対処する 3 つの方法: 再定義しない`mainCRTStartup`、含まれているファイルはコンパイルされません`mainCRTStartup`を使用して **/LTCG**、またはグローバル変数およびオブジェクトを静的に初期化します。

### <a name="ltcg-and-msil-modules"></a>/LTCG モジュールと MSIL モジュール

[/GL](../../build/reference/gl-whole-program-optimization.md) と [/clr](../../build/reference/clr-common-language-runtime-compilation.md) を使用してコンパイルされたモジュールは、 **/LTCG** が指定されている場合にリンカーへの入力として使用できます。

- **/LTCG**ネイティブ オブジェクト ファイルを受け入れることができるし、混合ネイティブ/マネージ オブジェクト ファイル (を使用してコンパイル **/clr**)。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

- **/LTCG:PGI**を使用してコンパイルしたネイティブ モジュールを受け付けない **/GL**と **/clr**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 参照してください[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **全般**プロパティ ページ。

1. **[プログラム全体の最適化]** プロパティを変更します。

適用することも **/LTCG**を選択して特定のビルドに**ビルド** > **ガイド付き最適化のプロファイル**メニュー バーで、またはプロファイルのいずれかを選択してプロジェクトのショートカット メニューの ガイド付き最適化オプション。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>」を参照してください。

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)
