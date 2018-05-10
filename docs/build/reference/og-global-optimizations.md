---
title: -Og (グローバルの最適化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 09/22/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
dev_langs:
- C++
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03ef87f31e478bfbc8691b7e678186dd1a0621e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="og-global-optimizations"></a>/Og (グローバルの最適化)

非推奨。 ローカルおよびグローバルの最適化は、自動レジスタ割り当て、およびループ最適化します。 いずれかを使用することをお勧め[/O1 (サイズを最小限に抑える)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)または[/O2 (速度)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)代わりにします。

## <a name="syntax"></a>構文

> /Og

## <a name="remarks"></a>コメント

**/Og**は推奨されなくなりました。 これらの最適化は既定では一般に有効になりました。 最適化の詳細については、次を参照してください。 [/O1、/O2 (サイズの最小化、最大速度)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)または[/Ox (有効にする最も速度の最適化)](../../build/reference/ox-full-optimization.md)です。

次の最適化が 利用可能な **/Og**:

- ローカルおよびグローバルの共通部分式の削除

     この最適化では、共通部分式の値は 1 回計算します。 次の例では場合の値`b`と`c`3 つの式の間で変更しないで、コンパイラでの計算を割り当てることができます`b + c`を一時変数には変数を使用してください`b + c`:

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

     ローカルの共通部分最適化のため、コンパイラは、共通部分式のコードの短いセクションです。 グローバルの共通部分最適化は、コンパイラは、すべての関数に共通部分式を検索します。

- 自動レジスタ割り当て

     この最適化により、レジスタにも頻繁に使用されるストアの変数と部分式は、コンパイラ`register`キーワードは無視されます。

- ループの最適化

     この最適化は、ループの本体から不変の部分式を削除します。 最適なループには、ループの実行するたびに値が変わる式だけが含まれています。 次の例では、式で`x + y`ループの本体に反映されません。

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

     最適化後に、`x + y`ループが実行されるたびにではなく 1 回計算されます。

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

     設定するエイリアスと仮定できますコンパイラがない場合は、ループの最適化ははるかに効果的な[_ _restrict](../../cpp/extension-restrict.md)、 [noalias](../../cpp/noalias.md)、または[制限](../../cpp/restrict.md)です。

    > [!NOTE]
    > 有効にするにまたはを使用して、関数によってごとにグローバルな最適化を無効にすることができます、`optimize`と共にプラグマ、`g`オプション。

 関連情報については、次を参照してください。 [/Oi (組み込み関数の生成)](../../build/reference/oi-generate-intrinsic-functions.md)と[/Ox (有効にする最も速度の最適化)](../../build/reference/ox-full-optimization.md)です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. コンパイラ オプションを入力して、**追加オプション**ボックス。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)

[コンパイラ オプション](../../build/reference/compiler-options.md)

[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)