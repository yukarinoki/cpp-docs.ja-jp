---
title: コンパイラ エラー C2764
ms.date: 11/04/2016
f1_keywords:
- C2764
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
ms.openlocfilehash: ba16431fc71a0e594b77dcc6dab62ed6c49c9137
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257492"
---
# <a name="compiler-error-c2764"></a>コンパイラ エラー C2764

'param': テンプレート パラメーターは、使用または部分的特殊化 'specialization' を推論できません。

テンプレート パラメーターは、部分的特殊化では使用されません。 これにより、部分的特殊化をテンプレート パラメーターを推測できないため、使用できなくなります。

## <a name="example"></a>例

次の例では、C2764 が生成されます。

```
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