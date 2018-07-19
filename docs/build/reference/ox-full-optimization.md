---
title: -Ox (ほとんどの速度の最適化を有効にする) |Microsoft ドキュメント
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
ms.openlocfilehash: 569563bff030904988e93db749438eaeb58ce9db
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378386"
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (ほとんどの速度の最適化を有効にする)

**/Ox**コンパイラ オプションにより、速度を優先の最適化の組み合わせ。 Visual Studio IDE とコンパイラ ヘルプ メッセージの一部のバージョンでは、これと呼ばれる*最大限の最適化*、ですが、 **/Ox**コンパイラ オプションを有効にして有効になっている速度の最適化オプションのサブセットのみ **/O2**です。

## <a name="syntax"></a>構文

> /Ox

## <a name="remarks"></a>コメント

**/Ox**コンパイラ オプションにより、 **/O**コンパイラ オプションをそのスピードを優先します。 **/Ox**コンパイラ オプションは、その他は含まれません[/GF (同一文字列の除去)](../../build/reference/gf-eliminate-duplicate-strings.md)と[/Gy (関数レベルのリンクを有効にする)](../../build/reference/gy-enable-function-level-linking.md) で有効にするオプション[/O1 または/O2 (サイズを最小限に抑える、速度)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)です。 追加のオプションによって適用 **/O1**と **/O2**を文字列またはターゲット アドレスは、デバッグに影響する可能性と厳密な言語の適合性を共有する関数へのポインターが発生することができます。 **/Ox**オプションを含めずにほとんどの最適化を有効にする簡単な方法は、 **/GF**と **/Gy**です。 詳細については、の説明を参照してください、 [/GF](../../build/reference/gf-eliminate-duplicate-strings.md)と[/Gy](../../build/reference/gy-enable-function-level-linking.md)オプション。

**/Ox**コンパイラ オプションは、同じ組み合わせで、次のオプションを使用します。

- [/Ob (関数のインライン展開)](../../build/reference/ob-inline-function-expansion.md)で、オプション パラメーターは 2 (**/Ob2**)

- [/Og (グローバルの最適化)](../../build/reference/og-global-optimizations.md)

- [/Oi (組み込み関数の生成)](../../build/reference/oi-generate-intrinsic-functions.md)

- [/Ot (実行速度の優先高速コード)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (フレーム ポインターの省略)](../../build/reference/oy-frame-pointer-omission.md)

**/Ox**から同時には。

- [/O1 (サイズを最小限に抑える)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/O2 (速度を最大限に)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/Od (無効 (デバッグ))](../../build/reference/od-disable-debug.md)

速度に対するバイアスを取り消すことができます、 **/Ox**コンパイラ オプションを指定する場合 **/Oxs**、どの結合、 **/Ox**コンパイラ オプションを[/Os (優先 Smallコード)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)です。 オプションの組み合わせでは、コード サイズを小さくが優先されます。

リリース ビルドの場合、ファイル レベルが使用可能なすべての最適化を適用する指定をお勧めする[/O2 (速度)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)の代わりに **/Ox**、および[/O1 (サイズを最小限に抑える)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)代わりに **/Oxs**です。 さらに多くの最適化のリリースでは、次のビルド、向けも検討、 [/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプションと[/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)リンカー オプション。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **構成プロパティ**、開かれている**C/C++** を選択し、**最適化**プロパティ ページ。

1. 変更、**最適化**プロパティです。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)  
[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)