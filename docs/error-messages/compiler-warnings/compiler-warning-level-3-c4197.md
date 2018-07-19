---
title: コンパイラの警告 (レベル 3) C4197 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4197
dev_langs:
- C++
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa119e0b1afd3f660dd04040965006f1b52cad01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290427"
---
# <a name="compiler-warning-level-3-c4197"></a>コンパイラの警告 (レベル 3) C4197
'type': キャストのトップレベルの volatile は無視されます  
  
 コンパイラで修飾されている r 値型へのキャストを検出しました[揮発性](../../cpp/volatile-cpp.md)、または volatile で修飾する一部の型に右辺値の型のキャスト。 C 標準 (6.5.3)、に従って修飾の型に関連付けられているプロパティは左辺値式に対してのみ有効です。  
  
 次の例では、C4197 が生成されます。  
  
```  
// C4197.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <signal.h>  
#include <stdlib.h>  
  
void sigproc(int);  
struct S  
{  
   int i;  
} s;  
  
int main()  
{  
   signal(SIGINT, sigproc);  
   s.i = 1;  
   S *pS = &s;  
   for ( ; (volatile int)pS->i ; )   // C4197  
      break;  
   // for ( ; *(volatile int *)&pS->i ; )   // OK  
   //    break;  
}  
  
void sigproc(int) // ctrl-C  
{  
   signal(SIGINT, sigproc);  
   s.i = 0;  
}  
  
```