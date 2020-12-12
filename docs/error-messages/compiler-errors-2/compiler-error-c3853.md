---
description: 詳細については、「コンパイラエラー C3853」を参照してください。
title: コンパイラ エラー C3853
ms.date: 11/04/2016
f1_keywords:
- C3853
helpviewer_keywords:
- C3853
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
ms.openlocfilehash: c10306fd8626475a0ac3dbb7b9e14b7773e4157b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328188"
---
# <a name="compiler-error-c3853"></a>コンパイラ エラー C3853

' = ': 参照から関数への参照または代入を再初期化することはできません。

関数は左辺値ではないため、関数を通じて参照に割り当てることはできません。

次のサンプルでは、C3853 が生成されます。

```cpp
// C3853.cpp
// compile with: /EHsc
#include <iostream>
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   rf = afunc;   // C3853, can't reassign to a ref that's an lvalue
   int i = 99;
   int & ri = i;
   std::cout << i << std::endl;
   ri = 0;   // OK, i = 88;
   std::cout << i << std::endl;
}
```
