---
title: /LTCG (リンク時のコード生成)
description: MSVC リンカーオプション/LTCG は、プログラム全体の最適化のためのリンク時のコード生成を可能にします。
ms.date: 07/08/2020
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
ms.openlocfilehash: 6c0009e5236f33119ed411dc81ce6a4385f21a2a
ms.sourcegitcommit: f7fbdc39d73e1fb3793c396fccf7a1602af7248b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "91662269"
---
# <a name="ltcg-link-time-code-generation"></a>`/LTCG` (リンク時のコード生成)

を使用すると、 **`/LTCG`** プログラム全体の最適化を実行したり、ガイド付き最適化のプロファイル (pgo) インストルメンテーションを作成したり、トレーニングを実行したり、ガイド付き最適化ビルドを作成したりすることができます。

## <a name="syntax"></a>構文

> **`/LTCG`**[**`:`**{**`INCREMENTAL`**|**`NOSTATUS`**|**`STATUS`**|**`OFF`**}]

これらのオプションは、Visual Studio 2015 から非推奨とされます。

> **`/LTCG:`**{**`PGINSTRUMENT`**|**`PGOPTIMIZE`**|**`PGUPDATE`**}

### <a name="arguments"></a>引数

**`INCREMENTAL`**<br/>
Optionalリンカーが、プロジェクト全体ではなく、編集の影響を受けるファイルに対して、プログラム全体の最適化またはリンク時のコード生成 (LTCG) のみを適用するように指定します。 を指定した場合、既定では、このフラグは設定されません **`/LTCG`** 。また、プロジェクト全体がプログラム全体の最適化を使用してリンクされます。

**`NOSTATUS`** &#124; **`STATUS`**<br/>
(省略可能) リンクの何パーセントが完了したかを示す進行状況のインジケーターをリンカーによって表示するかどうかを指定します。 既定では、この状態情報は表示されません。

**`OFF`**<br/>
(省略可能) リンク時のコード生成を無効にします。 この動作は、 **`/LTCG`** コマンドラインでが指定されていない場合と同じです。

**`PGINSTRUMENT`**<br/>
(省略可能) このオプションは、Visual Studio 2015 から非推奨とされます。 代わりに、 **`/LTCG`** および[ `/GENPROFILE` または `/FASTGENPROFILE` ](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)を使用して、ガイド付き最適化のプロファイル用にインストルメント化されたビルドを生成します。 インストルメント化された実行から収集されるデータは、最適化されたイメージの作成に使用されます。 詳細については、「[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。 このオプションの短い形式は **`/LTCG:PGI`** です。

**`PGOPTIMIZE`**<br/>
(省略可能) このオプションは、Visual Studio 2015 から非推奨とされます。 代わりに、およびを使用し **`/LTCG`** て、  [`/USEPROFILE`](useprofile.md) 最適化されたイメージを作成します。 詳細については、「[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。 このオプションの短い形式は **`/LTCG:PGO`** です。

**`PGUPDATE`**<br/>
(省略可能) このオプションは、Visual Studio 2015 から非推奨とされます。 代わりに、およびを使用し **`/LTCG`** て、  **`/USEPROFILE`** 最適化されたイメージをリビルドします。 詳細については、「[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。 このオプションの短い形式は **`/LTCG:PGU`** です。

## <a name="remarks"></a>解説

オプションは、 **`/LTCG`** コンパイラを呼び出してプログラム全体の最適化を実行するようにリンカーを設定します。 または、ガイド付き最適化のプロファイルを実行することもできます。 詳細については、「[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。

次の例外を除き、との PGO の組み合わせにリンカーオプションを追加することはできません **`/LTCG`** **`/USEPROFILE`** 。これは **`/LTCG`** 、およびオプションの以前の pgo 初期化の組み合わせでは指定されませんでした **`/GENPROFILE`** 。

- [`/BASE`](base-base-address.md)

- [`/FIXED`](fixed-fixed-base-address.md)

- **`/LTCG`**

- [`/MAP`](map-generate-mapfile.md)

- [`/MAPINFO`](mapinfo-include-information-in-mapfile.md)

- [`/NOLOGO`](nologo-suppress-startup-banner-linker.md)

- [`/OUT`](out-output-file-name.md)

- [`/PGD`](pgd-specify-database-for-profile-guided-optimizations.md)

- [`/PDB`](pdb-use-program-database.md)

- [`/PDBSTRIPPED`](pdbstripped-strip-private-symbols.md)

- [`/STUB`](stub-ms-dos-stub-file-name.md)

- [`/VERBOSE`](verbose-print-progress-messages.md)

およびを使用して PGO を初期化するオプションと共に指定されたすべてのリンカーオプションは、 **`/LTCG`** **`/GENPROFILE`** とを使用してビルドするときに指定する必要はありません。これらは暗黙的に指定され **`/LTCG`** **`/USEPROFILE`** ます。

この記事の残りの部分では、によって実行されるリンク時のコード生成について説明し **`/LTCG`** ます。

**`/LTCG`** は、で暗黙的に使用され [`/GL`](gl-whole-program-optimization.md) ます。

リンカーは、または MSIL モジュールを使用してコンパイルされたモジュールが渡されると、リンク時のコード生成を呼び出し **`/GL`** ます (「 [ `.netmodule` リンカー入力とし](netmodule-files-as-linker-input.md)てのファイル」を参照してください)。 **`/LTCG`** または MSIL モジュールをリンカーに渡すときに明示的にを指定しない場合 **`/GL`** 、リンカーは最終的にこの状況を検出し、を使用してリンクを再起動し **`/LTCG`** ます。 **`/LTCG`** **`/GL`** と MSIL モジュールをリンカーに渡して、最速のビルドパフォーマンスを実現するには、明示的にを指定します。

さらに高速なパフォーマンスを実現するには、を使用 **`/LTCG:INCREMENTAL`** します。 このオプションは、プロジェクト全体ではなく、ソースファイルの変更によって影響を受けるファイルのみを再最適化するようにリンカーに指示します。 このオプションを使用すると、必要なリンク時間を大幅に短縮できます。 このオプションは、 [インクリメンタルリンク](incremental-link-incrementally.md)と同じオプションではありません。

**`/LTCG`** は、では使用 [`/INCREMENTAL`](incremental-link-incrementally.md) できません。

を使用して、、、 **`/LTCG`** 、またはを使用してコンパイルされたモジュールをリンクすると、 [`/Og`](og-global-optimizations.md) [`/O1`](o1-o2-minimize-size-maximize-speed.md) [`/O2`](o1-o2-minimize-size-maximize-speed.md) [`/Ox`](ox-full-optimization.md) 次の最適化が実行されます。

- クロス モジュールのインライン化

- プロシージャ間のレジスタ割り当て (64 ビット オペレーティング システムのみ)

- カスタムの呼び出し規約 (x86 のみ)

- 小規模な TLS 変位 (x86 のみ)

- スタックの二重配置 (x86 のみ)

- メモリのあいまいさ排除の強化 (グローバル変数および入力パラメーターの干渉情報の改善)

> [!NOTE]
> リンカーにより、各関数のコンパイルにどの最適化が使用されたかが判断され、リンク時に同じ最適化が適用されます。

およびを使用する **`/LTCG`** と、 **`/O2`** ダブルアラインメントの最適化が行われます。

**`/LTCG`** とが指定されている場合 **`/O1`** 、double アラインメントは実行されません。 アプリケーション内のほとんどの関数が、サイズに対してコンパイルされたいくつかの関数 (たとえば、プラグマを使用して) をコンパイルした場合、 [`optimize`](../../preprocessor/optimize.md) サイズに合わせて最適化された関数は、2つの配置を必要とする関数を呼び出すと、コンパイラによって二重に配置されます。

コンパイラで関数のすべての呼び出しサイトを特定できる場合、コンパイラでは関数に対する明示的な呼び出し規約の修飾子が無視され、関数の呼び出し規約の最適化が試行されます。

- レジスタでパラメーターを渡す

- 配置のためにパラメーターを並べ替える

- 使用されていないパラメーターを削除する

関数が関数ポインターを通じて呼び出された場合、またはを使用してコンパイルされたモジュールの外部から関数が呼び出された場合 **`/GL`** 、コンパイラは関数の呼び出し規約の最適化を試行しません。

> [!NOTE]
> とを使用する場合 **`/LTCG`** `mainCRTStartup` 、アプリケーションは、グローバルオブジェクトが初期化される前に実行されるユーザーコードに関連する、予測できない動作を持つことができます。 この問題に対処するには、再定義しない `mainCRTStartup` 、を使用してを含むファイルをコンパイルしない、 `mainCRTStartup` **`/LTCG`** グローバル変数とオブジェクトを静的に初期化する、の3つの方法があります。

### <a name="ltcg-and-msil-modules"></a>`/LTCG` および MSIL モジュール

およびを使用してコンパイルされたモジュール [`/GL`](gl-whole-program-optimization.md) [`/clr`](clr-common-language-runtime-compilation.md) は、が指定されている場合にリンカーへの入力として使用でき **`/LTCG`** ます。

- **`/LTCG`** ネイティブオブジェクトファイル、および (を使用してコンパイルされた) 混在したネイティブ/マネージオブジェクトファイルを受け入れることができ **`/clr`** ます。 **`/clr:pure`** および **`/clr:safe`** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 以降ではサポートされていません。

- **`/LTCG:PGI`** およびを使用してコンパイルされたネイティブモジュールを受け入れません。 **`/GL`****`/clr`**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」を参照してください。

1. **構成プロパティ**の  >  **[全般**] プロパティページを選択します。

1. **[プログラム全体の最適化]** プロパティを変更します。

**`/LTCG`** **Build**  >  また、メニューバーで [ビルド**プロファイルガイド付き最適化**] を選択するか、プロジェクトのショートカットメニューの [ガイド付き最適化のプロファイル] オプションのいずれかを選択して、特定のビルドにも適用できます。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkTimeCodeGeneration%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーリファレンス](linking.md)\
[MSVC リンカー オプション](linker-options.md)
