---
description: 詳細については、「コンパイラエラー C2250」を参照してください。
title: コンパイラ エラー C2250
ms.date: 11/04/2016
f1_keywords:
- C2250
helpviewer_keywords:
- C2250
ms.assetid: f990986f-5c7d-4af4-a25c-b35540f1e217
ms.openlocfilehash: 5d018a01899ac74f148b2f0467feff9d7cecc025
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134842"
---
# <a name="compiler-error-c2250"></a>コンパイラ エラー C2250

' identifier ': ' class:: member ' のあいまいな継承です

派生クラスは、仮想基底クラスの仮想関数の複数のオーバーライドを継承します。 これらのオーバーライドは、派生クラスではあいまいです。

次の例では C2286 が生成されます。

```cpp
// C2250.cpp
// compile with: /c
// C2250 expected
struct V {
   virtual void vf();
};

struct A : virtual V {
   void vf();
};

struct B : virtual V {
   void vf();
};

struct D : A, B {
   // Uncomment the following line to resolve.
   // void vf();
};
```
