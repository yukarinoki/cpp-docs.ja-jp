---
title: コンパイラの警告 (レベル 2) C4146 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a94d2aed0b455fda646214f4488c53045b7f6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296690"
---
# <a name="compiler-warning-level-2-c4146"></a>コンパイラの警告 (レベル 2) C4146
単項マイナス符号付く型に、結果はまだ署名されていない演算子  
  
 符号なしの型は、ため、単項マイナス (否定) 通常なさない符号なしの型に適用される場合にのみ負でない値を保持できます。 オペランドと結果の両方は、負でないです。  
  
 実際には、このエラーは、プログラマが-2147483648 をある最小の整数値を express しようとするときに発生します。 この値は、式が 2 つのステージで処理されるため、-2147483648 として記述することはできません。  
  
1.  2147483648 数が評価されます。 2147483647 の整数型の最大値よりも大きいため、型の 2147483648 が[int](../../c-language/integer-types.md)が`unsigned int`です。  
  
2.  単項マイナスはも含めて 2147483648 符号なしの結果で、値に適用されます。  
  
 結果の符号なしの型には、予期しない動作を可能性があります。 比較では、結果を使用する場合、署名されていない比較される可能性があります、たとえば、もう一方のオペランドが、`int`です。 これは、次のサンプル プログラムが 1 つの行を出力する理由について説明します。  
  
 必要な 2 行目`1 is greater than the most negative int`、ためには出力されません`((unsigned int)1) > 2147483648`は false。  
  
 型が含まれます limits.h から INT_MIN を使用して、C4146 を回避できます**int を署名**です。  
  
## <a name="example"></a>例  
 次の例では、C4146 が生成されます。  
  
```  
// C4146.cpp  
// compile with: /W2  
#include <stdio.h>  
  
void check(int i)   
{  
    if (i > -2147483648)   // C4146  
        printf_s("%d is greater than the most negative int\n", i);  
}  
  
int main()   
{  
    check(-100);  
    check(1);  
}  
```