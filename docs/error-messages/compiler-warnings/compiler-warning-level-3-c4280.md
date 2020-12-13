---
description: '詳細情報: コンパイラの警告 (レベル 3) C4280'
title: コンパイラの警告 (レベル 3) C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: e2ef8d4961bf4046d2501d5724ff487bb1526ce2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344134"
---
# <a name="compiler-warning-level-3-c4280"></a>コンパイラの警告 (レベル 3) C4280

' operator-> ' は型 ' type ' を介して自己再帰的でした

コードによって、 **演算子 >** が正しく呼び出されないようにすることができます。

次の例では、C4280 が生成されます。

```cpp
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```
