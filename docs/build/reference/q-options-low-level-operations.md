---
description: /Q オプション (低レベルの操作) の詳細情報
title: /Q オプション (低水準の操作)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: f01781dd670c128f65717a05c6a9367e126550e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225714"
---
# <a name="q-options-low-level-operations"></a>/Q オプション (低水準の操作)

**/Q** コンパイラオプションを使用すると、次のような低レベルのコンパイラ操作を実行できます。

- [/Qfast_transcendentals (Force Fast 超越関数)](qfast-transcendentals-force-fast-transcendentals.md): Fast 超越関数を生成します。

- [/QIfist (非表示 _ftol)](qifist-suppress-ftol.md): `_ftol` 浮動小数点型から整数型への変換が必要な場合は抑制します (x86 のみ)。

- [/Qimprecise_fwaits (Try ブロック内の fwaits を削除)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): `fwait` ブロック内のコマンドを削除 **`try`** します。

- [/QIntel-jcc-erratum](qintel-jcc-erratum.md): Intel Jump Conditional CODE (jcc) erratum マイクロコード更新によるパフォーマンスの影響を軽減します。

- [/Qpar (並行化)](qpar-auto-parallelizer.md): [#pragma loop ()](../../preprocessor/loop.md) ディレクティブでマークされているループの自動並列化を有効にします。

- [/Qpar-report (自動並行化レポートレベル)](qpar-report-auto-parallelizer-reporting-level.md): 自動並列化のレポートレベルを有効にします。

- [/Qsafe_fp_loads](qsafe-fp-loads.md): 浮動小数点レジスタの読み込みと、メモリと MMX レジスタ間の移動の最適化を抑制します。

- [/Qspectre](qspectre.md): 特定の Spectre セキュリティの脆弱性を軽減するための手順を生成します。

- [/Qspectre-load](qspectre-load.md): 負荷に基づいて Spectre セキュリティの脆弱性を軽減するための手順を生成します。

- [/Qspectre-load-cf](qspectre-load-cf.md): 負荷がかかる制御フローの指示に基づいて、Spectre セキュリティの脆弱性を軽減するための手順を生成します。

- [/Qvec-report (自動ベクター化 Reporting Level)](qvec-report-auto-vectorizer-reporting-level.md): 自動ベクター化のレポートレベルを有効にします。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
