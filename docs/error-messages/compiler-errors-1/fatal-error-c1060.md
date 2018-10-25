---
title: 致命的なエラー C1060 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1060
dev_langs:
- C++
helpviewer_keywords:
- C1060
ms.assetid: feaf305c-c84c-4160-b974-50e283412849
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09d9c0292840daf65effca09775ff85a156b00f8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053917"
---
# <a name="fatal-error-c1060"></a>致命的なエラー C1060

ヒープの領域を使い果たしました。

オペレーティング システムまたはランタイム ライブラリがメモリの要求に対応できません。

### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>このエラーを解決するには次の方法があります。

1. コンパイラはエラーも発行する場合[C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)と[C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)を使用して、 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)コンパイラ オプションで、メモリ割り当て制限を低きます。 残りのメモリ割り当てを削減すると、アプリケーションに使用できるヒープ領域が増加します。

   場合、 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)オプションは既に設定されている、それを削除してください。 オプションで指定されたメモリ割り当て制限が高すぎるために、ヒープ領域が足りなくなっている可能性があります。 削除する場合、コンパイラは既定の制限を使用して、 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)オプション。

1. 64 ビット プラットフォームでコンパイルする場合は、64 ビットのコンパイラ ツールセットを使用します。 詳しくは、次を参照してください。[方法: コマンドラインで 64 ビット Visual c ツールセットを有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)します。

1. 32 ビットの Windows で試すを使用して、 [3 GB](https://support.microsoft.com/help/833721/available-switch-options-for-the-windows-xp-and-the-windows-server-200) boot.ini スイッチ。

1. Windows のスワップ ファイルのサイズを大きくします。

1. 実行中のプログラムを終了します。

1. 不必要なインクルード ファイルを除去します。

1. 不要なグローバル変数を削除します。これを行うには、たとえば、サイズの大きな配列を宣言する代わりに、メモリを動的に割り当てます。

1. 不要な宣言を削除します。

9. 現在のファイルを小さなファイルに分割します。