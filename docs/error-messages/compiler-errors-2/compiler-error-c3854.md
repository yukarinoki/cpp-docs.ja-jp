---
title: コンパイラ エラー C3854
ms.date: 11/04/2016
f1_keywords:
- C3854
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
ms.openlocfilehash: 3b48e2c65003537102864fdafe7db70b06ade029
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265530"
---
# <a name="compiler-error-c3854"></a>コンパイラ エラー C3854

関数に '=' の左辺の式が評価されます。 関数 (関数は左辺値ではありません) に割り当てることはできません。

参照を再初期化することはできません。 関数への参照を逆参照には、関数、割り当てることはできません、右辺値が生成されます。 そのため、関数への参照を割り当てることはできません。

次の例では、C3854 が生成されます。

```
// C3854.cpp
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);
typedef int (* pFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   pFunc_t pf = &afunc;   // OK initializing a pointer to function

   *pf = &afunc;   // C3854
   // try the following line instead
   // pf = &afunc;
   *rf = &afunc;   // C3854
}
```