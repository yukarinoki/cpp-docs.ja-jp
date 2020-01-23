---
title: /Q オプション (低水準の操作)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 9dd3675f200be4f0ec66620bcf3cf05706991b66
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518174"
---
# <a name="q-options-low-level-operations"></a>/Q オプション (低水準の操作)

**/Q**コンパイラオプションを使用すると、次のような低レベルのコンパイラ操作を実行できます。

- [/Qfast_transcendentals (Force Fast 超越関数)](qfast-transcendentals-force-fast-transcendentals.md): Fast 超越関数を生成します。

- [/QIfist (非表示 _ftol)](qifist-suppress-ftol.md): 浮動小数点型から整数型への変換が必要な場合に `_ftol` を抑制します (x86 のみ)。

- [/Qimprecise_fwaits (Try ブロック内の fwaits を削除)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): `try` ブロック内の `fwait` コマンドを削除します。

- [/QIntel-jcc-erratum](qintel-jcc-erratum.md): Intel Jump Conditional CODE (jcc) erratum マイクロコード更新によるパフォーマンスの影響を軽減します。

- [/Qpar (並行化)](qpar-auto-parallelizer.md): [#pragma loop ()](../../preprocessor/loop.md)ディレクティブでマークされているループの自動並列化を有効にします。

- [/Qpar-report (自動並行化レポートレベル)](qpar-report-auto-parallelizer-reporting-level.md): 自動並列化のレポートレベルを有効にします。

- [/Qsafe_fp_loads](qsafe-fp-loads.md): 浮動小数点レジスタの読み込みと、メモリと MMX レジスタ間の移動の最適化を抑制します。

- [/Qspectre](qspectre.md): 特定の Spectre セキュリティの脆弱性を軽減するための手順を生成します。

- [/Qvec-report (自動ベクター化 Reporting Level)](qvec-report-auto-vectorizer-reporting-level.md): 自動ベクター化のレポートレベルを有効にします。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
