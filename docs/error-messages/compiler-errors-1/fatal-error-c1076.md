---
title: 致命的なエラー C1076
ms.date: 03/08/2019
f1_keywords:
- C1076
helpviewer_keywords:
- C1076
ms.assetid: 84ac1180-3e8a-48e8-9f77-7f18a778b964
ms.openlocfilehash: ca5117342d406983e8cba675c2589d2431d09d38
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204179"
---
# <a name="fatal-error-c1076"></a>致命的なエラー C1076

> コンパイラの制限 : 内部ヒープの上限に達しました。上限を変更するには /Zm オプションを使用してください。

このエラーは、シンボルが多すぎるか、テンプレートのインスタンス生成が多すぎることが原因で発生する場合があります。 Visual Studio 2015 以降、このメッセージは、並列ビルドプロセスが多すぎることによって発生する Windows 仮想メモリの負荷が原因で発生する可能性があります。 この場合、`#pragma hdrstop` ディレクティブを使用する場合を除き、 **/zm**オプションを使用することをお勧めします。

このエラーを解決するには、次の方法があります。

1. プリコンパイル済みヘッダーで `#pragma hdrstop` ディレクティブを使用する場合は、 [/zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)オプションを使用して、コンパイラのメモリ制限を[C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)エラーメッセージに指定された値に設定します。 Visual Studio でこの値を設定する方法の詳細については、「 [/zm (プリコンパイル済みヘッダーのメモリ割り当て制限の指定)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)」の「解説」を参照してください。

1. **/Maxcpucount**オプションを使用して指定された並列処理の数を MSBUILD に減らすことを検討してください。EXE と共に、 **/mp**オプションを CL にします。EXCEL.EXE. 詳細については、「[プリコンパイル済みヘッダー (PCH) の問題と推奨事項](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/)」を参照してください。

1. 64 ビット オペレーティング システムで 32 ビット ホスト コンパイラを使用している場合は、代わりに 64 ビット ホスト コンパイラを使用します。 詳細については、「[方法: コマンドラインで64ビットC++ビジュアルツールセットを有効](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)にする」を参照してください。

1. 不必要なインクルード ファイルを除去します。

1. 不要なグローバル変数を削除します。これを行うには、たとえば、サイズの大きな配列を宣言する代わりに、メモリを動的に割り当てます。

1. 不要な宣言を削除します。

ビルドの開始直後に C1076 が発生した場合、 **/zm**に指定された値は、プログラムに対して高すぎる可能性があります。 **/Zm**値を減らします。
