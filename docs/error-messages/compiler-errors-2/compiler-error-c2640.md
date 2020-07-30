---
title: コンパイラエラー C2640
ms.date: 11/04/2016
f1_keywords:
- C2640
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
ms.openlocfilehash: eb712379ff3ce25a435f4810f5552bc97f635cdd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212684"
---
# <a name="compiler-error-c2640"></a>コンパイラエラー C2640

' identifier ': __based 修飾子は参照では無効です

修飾子は、 **`__based`** ポインターに対してのみ使用できます。

次の例では、C2640 が生成されます。

```cpp
// C2640.cpp
void f(int i) {
    void *vp;
    int _based(vp) &vr = I;  // C2640
}
```
