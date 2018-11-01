---
title: コンパイラ エラー C2104
ms.date: 11/04/2016
f1_keywords:
- C2104
helpviewer_keywords:
- C2104
ms.assetid: 2ea78896-72a6-4901-a1fa-f33ea88ad61b
ms.openlocfilehash: 086952b9f2b2b84851565bd2b4dafefa15808079
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502554"
---
# <a name="compiler-error-c2104"></a>コンパイラ エラー C2104

' &' では、ビット フィールドが無視されます

ビット フィールドのアドレスを取得することはできません。

次の例では、C2104 が生成されます。

```
// C2104.cpp
struct X {
   int sb : 1;
};

int main() {
   X x;
   &x.sb;   // C2104
   x.sb;   // OK
}
```