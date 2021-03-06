---
description: 詳細情報:/GL (プログラム全体の最適化)
title: /GL (プログラム全体の最適化)
ms.date: 03/05/2021
f1_keywords:
- /GL
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.openlocfilehash: 509deaae8881c4875a9ec2ddf4d5f1ee7744a2cf
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236551"
---
# <a name="gl-whole-program-optimization"></a>`/GL` (プログラム全体の最適化)

プログラム全体の最適化を有効にします。

## <a name="syntax"></a>構文

> **`/GL`**[**`-`**]

## <a name="remarks"></a>解説

プログラム全体の最適化により、コンパイラはプログラム内のすべてのモジュールに関する情報を使用して最適化を実行できます。 プログラム全体の最適化を行わないと、最適化はモジュール単位 (コンパイル単位) ごとに実行されます。

プログラム全体の最適化は既定でオフになっており、明示的に有効にする必要があります。 ただし、を使用して明示的に無効にすることもでき **`/GL-`** ます。

すべてのモジュールに関する情報を使用して、コンパイラは次のことを実行できます。

- 関数の境界を越えてレジスタの使用を最適化します。

- グローバルデータの変更を追跡し、負荷とストアの数を減らすことができるようにします。

- ポインターの逆参照によって変更された項目のセットを追跡し、必要な読み込みとストアを減らします。

- 関数が別のモジュールで定義されている場合でも、モジュール内の関数をインライン化します。

*`.obj`* で生成されたファイルは **`/GL`** 、やなどのリンカーユーティリティでは使用できません [`EDITBIN`](editbin-reference.md) [`DUMPBIN`](dumpbin-reference.md) 。

とを使用してプログラムをコンパイルする場合は、 **`/GL`** [`/c`](c-compile-without-linking.md) /ltcg リンカーオプションを使用して出力ファイルを作成する必要があります。

[`/ZI`](z7-zi-zi-debug-information-format.md) と共に使用することはできません。 **`/GL`**

現在のバージョンので生成されるファイルの形式は、 **`/GL`** 多くの場合、新しいバージョンの Visual Studio および MSVC ツールセットでは読み取ることができません。 すべてのバージョンの Visual Studio でファイルのコピーを配布する場合は *`.lib`* 、ユーザーが使用する予定で、今後は、 *`.lib`* *`.obj`* によって生成されるファイルで構成されたファイルを配布しないようにし **`/GL`** ます。 詳細については、「 [バイナリ互換性に関する制限事項](../../porting/binary-compat-2015-2017.md#restrictions)」を参照してください。

*`.obj`* およびプリコンパイル済みヘッダーファイルによって生成されたファイルは、ファイルを作成し **`/GL`** たのと *`.lib`* *`.lib`* 同じコンピューター上にリンクされていない限り、ファイルのビルドには使用でき **`/GL`** *`.obj`* ません。 *`.obj`* ファイルのプリコンパイル済みヘッダーファイルからの情報は、リンク時に必要です。

で使用できる最適化と、プログラム全体の最適化の制限事項の詳細については、「」を参照してください [`/LTCG`](ltcg-link-time-code-generation.md) 。  **`/GL`** では、ガイド付き最適化のプロファイルも使用できます。 ガイド付き最適化のプロファイル用にコンパイルするときに、プロファイルガイド付き最適化から関数の順序を設定する場合 [`/Gy`](gy-enable-function-level-linking.md) は、または/gyを暗黙的に使用するコンパイラオプションを指定してコンパイルする必要があります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

開発環境でを指定する方法の詳細につい **`/GL`** ては、「 [ `/LTCG` (リンク時のコード生成)](ltcg-link-time-code-generation.md) 」を参照してください。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)\
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
