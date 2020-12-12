---
description: 詳細については、「コンパイラエラー C2911」を参照してください。
title: コンパイラ エラー C2911
ms.date: 11/04/2016
f1_keywords:
- C2911
helpviewer_keywords:
- C2911
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
ms.openlocfilehash: c3890a6017e96b4b5f2f9dc7b5711fd98f29b947
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270539"
---
# <a name="compiler-error-c2911"></a>コンパイラ エラー C2911

'member': 現在のスコープ内で宣言または定義できません

名前空間、クラス、または関数の内部では、同じ名前空間、クラス、または関数のメンバー、または同じ名前空間、クラス、または関数で囲まれているメンバーだけを定義できます。

次の例では C2911 が生成されます。

```cpp
// C2911.cpp
struct A;

namespace M {
   struct D;
}

namespace N {
   struct C;

   namespace O {
      struct B;
   }

   // in N
   struct ::A {};   // C2911  A is member of global NS
   struct O::B{};   // OK B is in O, O is inside of N
   struct C {};     // OK C is member of N
   struct M::D {};  // C2911 D is member of M, M not enclosed by N
}
```
