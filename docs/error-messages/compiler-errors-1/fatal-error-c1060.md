---
title: 致命的なエラー C1060 |Microsoft ドキュメント
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
ms.openlocfilehash: 5aa168c185bafbfd6fadf3f0d5f1320ba4f43d60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226309"
---
# <a name="fatal-error-c1060"></a>致命的なエラー C1060
ヒープの領域を使い果たしました。  
  
 オペレーティング システムまたはランタイム ライブラリがメモリの要求に対応できません。  
  
### <a name="to-fix-this-error-try-the-following-possible-solutions"></a>このエラーを解決するには次の方法があります。  
  
1.  場合は、コンパイラによってエラーが発行[C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)と[C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)を使用して、 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)を下げるには、メモリ割り当て制限コンパイラ オプション。 残りのメモリ割り当てを削減すると、アプリケーションに使用できるヒープ領域が増加します。  
  
     場合、 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)オプションは既に設定されている、それを削除してください。 オプションで指定されたメモリ割り当て制限が高すぎるために、ヒープ領域が足りなくなっている可能性があります。 削除する場合、コンパイラは既定の制限を使用して、 [/Zm](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md)オプション。  
  
2.  64 ビット プラットフォームでコンパイルする場合は、64 ビットのコンパイラ ツールセットを使用します。 詳細については、次を参照してください。[する方法: コマンドラインで 64 ビット Visual c ツールセットを有効にする](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)です。  
  
3.  32 ビット Windows での再試行を使用して、 [3 GB](http://go.microsoft.com/fwlink/p/?linkid=177831) boot.ini スイッチ。  
  
4.  Windows のスワップ ファイルのサイズを大きくします。  
  
5.  実行中のプログラムを終了します。  
  
6.  不必要なインクルード ファイルを除去します。  
  
7.  不要なグローバル変数を削除します。これを行うには、たとえば、サイズの大きな配列を宣言する代わりに、メモリを動的に割り当てます。  
  
8.  不要な宣言を削除します。  
  
9. 現在のファイルを小さなファイルに分割します。