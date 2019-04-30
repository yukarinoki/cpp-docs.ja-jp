---
title: コンパイラ エラー C2634
ms.date: 11/04/2016
f1_keywords:
- C2634
helpviewer_keywords:
- C2634
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
ms.openlocfilehash: 99b6ce006d91c36d6bcd58e607d2bc8946ee6e55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360399"
---
# <a name="compiler-error-c2634"></a>コンパイラ エラー C2634

' & class::member': 参照メンバーへのポインターは無効です

参照メンバーへのポインターが宣言されています。

次の例では、C2634 が生成されます。

```
// C2634.cpp
int mem;
struct S {
   S() : rf(mem) { }
   int &rf;
};
int (S::*pdm) = &S::rf;   // C2634
```