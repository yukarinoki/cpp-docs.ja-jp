---
title: /Og (グローバルの最適化)
description: 非推奨の MSVC コンパイラオプション/Og について説明します。以前は、グローバルな最適化を有効にするために使用しています。
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
ms.openlocfilehash: c1cab53ccb391bd7d6ca7660e2750f53aa7c72e4
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180852"
---
# <a name="og-global-optimizations"></a>`/Og`(グローバルな最適化)

非推奨になりました。 ローカルおよびグローバルの最適化、自動レジスタ割り当て、およびループの最適化を提供します。 代わりに、 [ `/O1` (サイズを最小化する)](o1-o2-minimize-size-maximize-speed.md)または[ `/O2` (最大速度)](o1-o2-minimize-size-maximize-speed.md)のいずれかを使用することをお勧めします。

## <a name="syntax"></a>構文

> **`/Og`**

## <a name="remarks"></a>解説

**`/Og`** は非推奨とされます。 最適化が有効になっている場合、これらの最適化は既定で有効になります。 最適化の詳細については、「」 [ `/O1` `/O2` (サイズの最小化、速度の最大化)](o1-o2-minimize-size-maximize-speed.md)、または[ `/Ox` (最も高速な最適化を有効にする)](ox-full-optimization.md)を参照してください。

では、次の最適化を使用でき **`/Og`** ます。

- ローカルとグローバルの共通部分式の削除

   この最適化では、共通部分式の値が1回計算されます。 次の例では、との値 `b` が `c` 3 つの式の間で変更されない場合、コンパイラはの計算を `b + c` 一時変数に割り当て、その変数をに使用でき `b + c` ます。

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

   ローカルの共通部分式の最適化では、コンパイラは、共通部分式のコードの短いセクションを調べます。 グローバルな共通部分式の最適化では、コンパイラは関数全体で共通の部分式を検索します。

- 自動レジスタ割り当て

   この最適化により、コンパイラは、頻繁に使用される変数と部分式をレジスタに格納できます。`register`キーワードは無視されます。

- ループの最適化

   この最適化によって、ループの本体から不変部分式が削除されます。 最適なループには、ループの各実行によって値が変化する式だけが含まれます。 次の例では、式は `x + y` ループ本体では変更されません。

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

   最適化後、 `x + y` は、ループが実行されるたびではなく、1回計算されます。

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

   、、またはを使用して設定した別名がコンパイラによって想定されていない場合は、ループの最適化の方がはるかに効果的です [`__restrict`](../../cpp/extension-restrict.md) [`noalias`](../../cpp/noalias.md) [`restrict`](../../cpp/restrict.md) 。

   > [!NOTE]
   > プラグマをオプションと共に使用して、関数ごとにグローバル最適化を有効または無効にすることができ `optimize` `g` ます。

関連情報については、「 [ `/Oi` (組み込み関数の生成)](oi-generate-intrinsic-functions.md) 」および「 [ `/Ox ` (ほとんどの速度の最適化を有効にする)](ox-full-optimization.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] ボックスにコンパイラオプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
