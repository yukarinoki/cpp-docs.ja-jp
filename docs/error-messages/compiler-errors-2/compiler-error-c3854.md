---
description: 詳細については、「コンパイラエラー C3854」を参照してください。
title: コンパイラ エラー C3854
ms.date: 11/04/2016
f1_keywords:
- C3854
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
ms.openlocfilehash: f6c2399ff4c38cfbb306bd90e5bb5e96b34220eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328156"
---
# <a name="compiler-error-c3854"></a>コンパイラ エラー C3854

' = ' の左側の式は関数に評価されます。 関数に割り当てることはできません (関数は左辺値ではありません)

参照を再初期化することはできません。 関数への参照を逆参照すると、代入できない右辺値である関数が生成されます。 したがって、関数への参照を使用してを割り当てることはできません。

次の例では、C3854 が生成されます。

```cpp
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
