---
title: コンパイラの警告 (レベル 3) C4243
ms.date: 11/04/2016
f1_keywords:
- C4243
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
ms.openlocfilehash: 5900202a88eb7dc0575c5e97a58b20b0ef290a49
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161556"
---
# <a name="compiler-warning-level-3-c4243"></a>コンパイラの警告 (レベル 3) C4243

' type1 ' から ' type1 ' への ' 変換型 ' 変換が存在しますが、アクセスできません

派生クラスへのポインターは基底クラスへのポインターに変換されますが、派生クラスは、プライベートまたは保護されたアクセスで基底クラスを継承します。

次の例では、C4243 が生成されます。

```cpp
// C4243.cpp
// compile with: /W3
// C4243 expected
struct B {
   int f() {
      return 0;
   };
};

struct D : private B {};
struct E : public B {};

int main() {
   // Delete the following 2 lines to resolve.
   int (D::* d)() = (int(D::*)()) &B::f;
   d;

   int (E::* e)() = (int(E::*)()) &B::f; // OK
   e;
}
```
