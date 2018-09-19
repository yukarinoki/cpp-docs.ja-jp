---
title: -Ox (ほとんどの速度の最適化を有効にする) |Microsoft Docs
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /ox
dev_langs:
- C++
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d93bfe44fab0400ce4c3c173473601745f85196c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721527"
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (ほとんどの速度の最適化を有効にする)

**/Ox**コンパイラ オプションは、速度を優先する最適化の組み合わせを使用できます。 Visual Studio IDE およびコンパイラのヘルプ メッセージのいくつかのバージョンでは、これと呼ばれる*最大限の最適化*が、 **/Ox**コンパイラ オプションで有効になって、速度最適化のオプションのサブセットのみを使用できます。**/O2**します。

## <a name="syntax"></a>構文

> /Ox

## <a name="remarks"></a>Remarks

**/Ox**コンパイラ オプションにより、 **/O**コンパイラ オプションをその速度を優先します。 **/Ox**コンパイラ オプションは、その他は含まれません[/GF (同一文字列の排除)](../../build/reference/gf-eliminate-duplicate-strings.md)と[/Gy (関数レベルのリンクの有効にする)](../../build/reference/gy-enable-function-level-linking.md) で有効にするオプション[/O1 または/O2 (サイズ最小化し、速度を最大化)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)します。 追加のオプションによって適用される **/O1**と **/O2**文字列またはターゲット アドレスは、デバッグに影響する可能性と厳密な言語への準拠を共有する関数へのポインターが発生することができます。 **/Ox**オプションを含めなくても、ほとんどの最適化を有効にする簡単な方法は、 **/GF**と **/Gy**します。 詳細については、の説明を参照してください、 [/GF](../../build/reference/gf-eliminate-duplicate-strings.md)と[/Gy](../../build/reference/gy-enable-function-level-linking.md)オプション。

**/Ox**コンパイラ オプションは、同じ組み合わせで、次のオプションを使用するとします。

- [/Ob (関数のインライン展開)](../../build/reference/ob-inline-function-expansion.md)でオプションのパラメーターは 2 (**/Ob2**)

- [/Og (グローバルの最適化)](../../build/reference/og-global-optimizations.md)

- [/Oi (組み込み関数の生成)](../../build/reference/oi-generate-intrinsic-functions.md)

- [/Ot (実行の高速なコード)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (フレーム ポインターの省略)](../../build/reference/oy-frame-pointer-omission.md)

**/Ox**から相互に排他的です。

- [/O1 (サイズ最小化)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/O2 (速度を最大化)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/Od (無効 (デバッグ))](../../build/reference/od-disable-debug.md)

速度に対するバイアスを取り消すことができます、 **/Ox**コンパイラ オプションを指定する場合 **/Oxs**を組み合わせる、 **/Ox**コンパイラ オプションを使用[/Os (優先小コード)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)します。 オプションの組み合わせでは、コード サイズを小さくも優先します。

リリース ビルドの場合、ファイル レベルが使用可能なすべての最適化を適用する指定した勧め[/O2 (速度)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)の代わりに **/Ox**、および[/O1 (サイズを最小限に抑える)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)代わりに **/Oxs**します。 リリースでさらに多くの最適化がビルドも検討、 [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプションと[/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)リンカー オプション。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **構成プロパティ**、オープン**C/C++** 選択し、**最適化**プロパティ ページ。

1. 変更、**最適化**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)