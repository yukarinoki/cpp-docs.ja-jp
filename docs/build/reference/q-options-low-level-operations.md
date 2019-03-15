---
title: /Q オプション (低水準の操作)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 5bbb63b4f437f8aefd5c84c1c1c4bd20bdb965cb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819910"
---
# <a name="q-options-low-level-operations"></a>/Q オプション (低水準の操作)

使用することができます、 **/Q**低水準のコンパイラの次の操作を実行するコンパイラ オプション。

- [/Qfast_transcendentals (超越関数高速)](qfast-transcendentals-force-fast-transcendentals.md):高速超越関数を生成します。

- [/Qifist (_ftol を呼び出さない)](qifist-suppress-ftol.md):抑制`_ftol`浮動小数点型から整数型への変換が必要です (x86 のみ) の場合。

- [/Qimprecise_fwaits (Try ブロック内部の fwaits を削除)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md):`fwait` ブロックの中にある `try` コマンドを削除します。

- [/Qpar (自動並行化)](qpar-auto-parallelizer.md):[#pragma loop()](../../preprocessor/loop.md) ディレクティブでマークされているループの自動並列化を有効にします。

- [/Qpar-report (自動並行化レポート作成レベル)](qpar-report-auto-parallelizer-reporting-level.md):自動並列化のレポート レベルを有効にします。

- [/Qsafe_fp_loads](qsafe-fp-loads.md):浮動小数点レジスタの読み込み、メモリと MMX レジスタとの間の移動の最適化を抑制します。

- [/Qspectre](qspectre.md):Spectre セキュリティの脆弱性を軽減するために命令を生成します。

- [/Qvec-report (自動ベクター化レポート作成レベル)](qvec-report-auto-vectorizer-reporting-level.md):自動ベクター化のレポート レベルを有効にします。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)
