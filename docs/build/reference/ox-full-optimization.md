---
title: /Ox (ほとんどの速度の最適化を有効にする)
description: MSVC/Ox オプションは、いくつかのコンパイラ最適化オプションを1つのオプションに統合します。
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /Ox
- /Oxs
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
ms.openlocfilehash: 10893fe1cf032f2ab56f27aa4af95b050c2ec37e
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180839"
---
# <a name="ox-enable-most-speed-optimizations"></a>`/Ox`(ほとんどの速度の最適化を有効にします)

コンパイラオプションを使用すると、 **`/Ox`** 速度を優先する最適化を組み合わせることができます。 一部のバージョンの Visual Studio IDE とコンパイラのヘルプメッセージでは、*完全な最適化*と呼ばれていますが、コンパイラオプションを使用すると、 **`/Ox`** によって有効になる速度最適化オプションのサブセットのみが有効になり **`/O2`** ます。

## <a name="syntax"></a>構文

> **`/Ox`**

## <a name="remarks"></a>解説

**`/Ox`** コンパイラオプションは、 **`/O`** 速度を優先するコンパイラオプションを有効にします。 **`/Ox`** コンパイラオプションには、またはによって有効にされた ( [ `/GF` 重複する文字列の排除)](gf-eliminate-duplicate-strings.md)オプションと[ `/Gy` (関数レベルのリンクの有効化](gy-enable-function-level-linking.md)) オプションが含まれていません ( [ `/O1` `/O2` サイズを最小化し、速度を最大](o1-o2-minimize-size-maximize-speed.md)にします)。 とによって適用される追加オプションを使用すると、 **`/O1`** **`/O2`** ターゲットアドレスを共有するために、文字列または関数へのポインターが発生する可能性があります。これは、デバッグと厳密な言語準拠に影響する可能性があります **`/Ox`** オプションは、およびを含めずに、ほとんどの最適化を有効にする簡単な方法です **`/GF`** **`/Gy`** 。 詳細については、 [`/GF`](gf-eliminate-duplicate-strings.md) オプションとオプションの説明を参照してください [`/Gy`](gy-enable-function-level-linking.md) 。

**`/Ox`** コンパイラオプションは、次のオプションを組み合わせて使用する場合と同じです。

- [ `/Ob` (インライン関数の展開)。](ob-inline-function-expansion.md)オプションのパラメーターは 2 ( **`/Ob2`** ) です。

- [`/Oi`(組み込み関数の生成)](oi-generate-intrinsic-functions.md)

- [`/Ot`(高速コードを優先)](os-ot-favor-small-code-favor-fast-code.md)

- [`/Oy`(フレームポインターの省略)](oy-frame-pointer-omission.md)

**`/Ox`** 相互に排他的:

- [`/O1`(サイズの最小化)](o1-o2-minimize-size-maximize-speed.md)

- [`/O2`(速度を最大にする)](o1-o2-minimize-size-maximize-speed.md)

- [`/Od`(無効 (デバッグ))](od-disable-debug.md)

**`/Ox`** **`/Oxs`** **`/Ox`** コンパイラオプションをと組み合わせて使用する[ `/Os` (小さいコードを優先する)](os-ot-favor-small-code-favor-fast-code.md)ことを指定した場合、コンパイラオプションの速度に近づくまでバイアスを取り消すことができます。 結合されたオプションは、より小さなコードサイズを優先します。  オプションは、 **`/Oxs`** **`/Ox`** **`/Os`** オプションがその順序で表示されるタイミングを指定する場合とまったく同じです。

リリースビルドに使用できるすべてのファイルレベルの最適化を適用するには、で[はなく `/O2` ](o1-o2-minimize-size-maximize-speed.md) **`/Ox`** 、 [ `/O1` (サイズの最小化)](o1-o2-minimize-size-maximize-speed.md)を指定することをお勧めし **`/Oxs`** ます。 リリースビルドをさらに最適化するには、 [ `/GL` (プログラム全体の最適化)](gl-whole-program-optimization.md)コンパイラオプションと[ `/LTCG` (リンク時のコード生成)](ltcg-link-time-code-generation.md)リンカーオプションについても検討してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **最適化**] プロパティページを選択します。

1. **最適化**プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>

## <a name="see-also"></a>関連項目

[`/O`オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
