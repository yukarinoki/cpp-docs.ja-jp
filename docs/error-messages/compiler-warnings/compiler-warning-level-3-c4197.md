---
title: コンパイラの警告 (レベル 3) C4197 |Microsoft Docs
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
ms.openlocfilehash: 7e3651a305b8654b9d7d36238885233b8e583f27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043613"
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