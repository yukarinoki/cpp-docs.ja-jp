---
description: '詳細情報: 致命的なエラー C1060'
title: 致命的なエラー C1060
ms.date: 11/04/2016
f1_keywords:
- C1060
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
ms.openlocfilehash: 149fd4108aabf603e844c6906e072a9c64578d5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330723"
---
# <a name="fatal-error-c1060"></a>致命的なエラー C1060

ヒープの領域を使い果たしました。

オペレーティング システムまたはランタイム ライブラリがメモリの要求に対応できません。

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>このエラーを解決するには次の方法があります。

1. コンパイラがエラー [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) と [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)も発行する場合は、 [/zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md) コンパイラオプションを使用して、メモリ割り当て制限を低くします。 残りのメモリ割り当てを削減すると、アプリケーションに使用できるヒープ領域が増加します。

   [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)オプションが既に設定されている場合は、削除してみてください。 オプションで指定されたメモリ割り当て制限が高すぎるために、ヒープ領域が足りなくなっている可能性があります。 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)オプションを削除すると、コンパイラは既定の制限を使用します。

1. 64 ビット プラットフォームでコンパイルする場合は、64 ビットのコンパイラ ツールセットを使用します。 詳細については、「 [方法: コマンドラインで64ビット Visual C++ ツールセットを有効](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)にする」を参照してください。

1. 32ビットの Windows では、 [/3gb](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) boot.ini スイッチを使用してみてください。

1. Windows のスワップ ファイルのサイズを大きくします。

1. 実行中のプログラムを終了します。

1. 不必要なインクルード ファイルを除去します。

1. 不要なグローバル変数を削除します。これを行うには、たとえば、サイズの大きな配列を宣言する代わりに、メモリを動的に割り当てます。

1. 不要な宣言を削除します。

1. 現在のファイルを小さなファイルに分割します。
