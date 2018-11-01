---
title: /Q オプション (低水準の操作)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: a6dcbd256fa3510955884d3adba4855b23cdbfab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514254"
---
# <a name="q-options-low-level-operations"></a>/Q オプション (低水準の操作)

使用することができます、 **/Q**低水準のコンパイラの次の操作を実行するコンパイラ オプション。

- [/Qfast_transcendentals (超越関数高速)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): 高速超越関数を生成します。

- [/Qifist (_ftol を抑制する呼び出しません)](../../build/reference/qifist-suppress-ftol.md): 抑制`_ftol`浮動小数点型から整数型への変換が必要です (x86 のみ) の場合。

- [/Qimprecise_fwaits (Try ブロック内部の fwaits を削除)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): 削除`fwait`コマンド内で`try`ブロックします。

- [/Qpar (自動並行化)](../../build/reference/qpar-auto-parallelizer.md): とマークされているループの自動並列化を有効、 [#pragma loop()](../../preprocessor/loop.md)ディレクティブ。

- [/Qpar-report (自動並行化レポート作成レベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): 自動並列化のレベルのレポートを有効にします。

- [/Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): 浮動小数点レジスタの読み込みし、メモリと MMX の間の移動に関する登録用に最適化を抑制します。

- [/Qspectre](../../build/reference/qspectre.md): Spectre セキュリティの脆弱性を軽減するために命令を生成します。

- [/Qvec-report (自動ベクター化レポート作成レベル)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): 自動ベクター化のレベルのレポートを有効にします。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
