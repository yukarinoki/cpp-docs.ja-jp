---
description: 詳細については、「コンパイラエラー C2764」を参照してください。
title: コンパイラエラー C2764
ms.date: 11/04/2016
f1_keywords:
- C2764
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
ms.openlocfilehash: c700286a840c518597947f21f0455bc711f68275
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239533"
---
# <a name="compiler-error-c2764"></a>コンパイラエラー C2764

' param ': テンプレートパラメーターが、部分的特殊化 ' 特殊化 ' で使用されていないか、推論できされています

テンプレートパラメーターは部分的特殊化では使用されません。 これにより、テンプレートパラメーターを推測できないため、部分的特殊化は使用できなくなります。

## <a name="example"></a>例

次の例では、C2764 が生成されます。

```cpp
// C2764.cpp
#include <stdio.h>
template <class T1, class T2>
struct S  {
   int m_i;
};

template <class T1, class T2>
struct S<int, T2*> {   // C2764
// try the following line instead
// struct S<T1(*)(T2), T2*> {
   char m_c;
};

int main() {
   S<int, char> s1;
   S<void (*)(short), short *> s2;
   s2.m_c = 10;
   s1.m_i = s2.m_c;
   printf_s("%d\n", s1.m_i);
}
```
