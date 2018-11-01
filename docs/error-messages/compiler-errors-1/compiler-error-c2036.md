---
title: コンパイラ エラー C2036
ms.date: 11/04/2016
f1_keywords:
- C2036
helpviewer_keywords:
- C2036
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
ms.openlocfilehash: 47e691a045b3d1bd79226bdda8d96d24e2a80d80
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450054"
---
# <a name="compiler-error-c2036"></a>コンパイラ エラー C2036

'identifier': サイズが不明です

操作`identifier`特定できない、データ オブジェクトのサイズが必要です。

## <a name="example"></a>例

次の例では、C2036 が生成されます。

```
// C2036.c
// a C program
struct A* pA;
struct B { int i; } *pB;
int main() {
   pA++;   // C2036, size of A not known
   ((char*)pA)++;   // OK

   pB++;   // OK
}
```

## <a name="example"></a>例

次の例では、C2036 が生成されます。

```
// C2036_2.cpp
// a C++ program
struct A* pA;
int main() {
   pA++;   // C2036, size of A not known
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)
}
```