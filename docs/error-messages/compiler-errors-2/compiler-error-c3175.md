---
description: 詳細については、「コンパイラエラー C3175」を参照してください。
title: コンパイラエラー C3175
ms.date: 11/04/2016
f1_keywords:
- C3175
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
ms.openlocfilehash: 278d8de3d18aaa3437f4d2c0b1d8c9e3306630a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242081"
---
# <a name="compiler-error-c3175"></a>コンパイラエラー C3175

' function1 ': アンマネージド関数 ' function2 ' からマネージド型のメソッドを呼び出すことはできません

アンマネージ関数は、マネージクラスのメンバー関数を呼び出すことはできません。

次の例では、C3175 が生成されます。

```cpp
// C3175_2.cpp
// compile with: /clr

ref struct A {
   static void func() {
   }
};

#pragma unmanaged   // remove this line to resolve

void func2() {
   A::func();   // C3175
}

#pragma managed

int main() {
   A ^a = gcnew A;
   func2();
}
```
