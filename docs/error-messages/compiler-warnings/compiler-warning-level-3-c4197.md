---
title: コンパイラの警告 (レベル 3) C4197
ms.date: 11/04/2016
f1_keywords:
- C4197
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
ms.openlocfilehash: 6de07411a51c8436356e044cb397a65513827fdf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442576"
---
# <a name="compiler-warning-level-3-c4197"></a>コンパイラの警告 (レベル 3) C4197

'type': キャストのトップレベルの volatile は無視されます

修飾されている、右辺値の型へのキャストが検出されました[揮発性](../../cpp/volatile-cpp.md)、または volatile で修飾されているいくつかの型に右辺値の型のキャスト。 C の標準 (6.5.3)、修飾型に関連付けられているプロパティは、左辺値式に対してのみ意味を持つです。

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