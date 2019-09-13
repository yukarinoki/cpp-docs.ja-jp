---
title: /Q オプション (低水準の操作)
ms.date: 01/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 6348226aa38d1f2eefdf9e19e27c4c87bd2f0812
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927667"
---
# <a name="q-options-low-level-operations"></a>/Q オプション (低水準の操作)

**/Q**コンパイラオプションを使用すると、次のような低レベルのコンパイラ操作を実行できます。

- [/Qfast_transcendentals (高速超越関数の強制)](qfast-transcendentals-force-fast-transcendentals.md):高速超越関数を生成します。

- [/QIfist (_ftol を非](qifist-suppress-ftol.md)表示にする):浮動`_ftol`小数点型から整数型への変換が必要な場合に、を抑制します (x86 のみ)。

- [/Qimprecise_fwaits (Try ブロック内の fwaits を削除する)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md):`fwait` ブロックの中にある `try` コマンドを削除します。

- [/Qpar (自動並行化)](qpar-auto-parallelizer.md):[#pragma loop()](../../preprocessor/loop.md) ディレクティブでマークされているループの自動並列化を有効にします。

- [/Qpar-report (自動並行化レポートレベル)](qpar-report-auto-parallelizer-reporting-level.md):自動並列化のレポート レベルを有効にします。

- [/Qsafe_fp_loads](qsafe-fp-loads.md):浮動小数点レジスタの読み込みと、メモリと MMX レジスタ間の移動の最適化を抑制します。

- [/Qspectre](qspectre.md):特定の Spectre セキュリティの脆弱性を軽減するための手順を生成します。

- [/Qvec-report (自動ベクター化レポートレベル)](qvec-report-auto-vectorizer-reporting-level.md):自動ベクター化のレポート レベルを有効にします。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
