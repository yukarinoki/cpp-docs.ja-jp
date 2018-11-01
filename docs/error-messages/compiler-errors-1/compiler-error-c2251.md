---
title: コンパイラ エラー C2251
ms.date: 11/04/2016
f1_keywords:
- C2251
helpviewer_keywords:
- C2251
ms.assetid: fefe050c-f8d3-4316-b237-8007dbcdd3bf
ms.openlocfilehash: b7ffb5b8d425e74523e491827ffb8878b8e03b38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452339"
---
# <a name="compiler-error-c2251"></a>コンパイラ エラー C2251

名前空間 'namespace' にはメンバー 'member' がありません。'member' は正しいですか。

コンパイラは、指定された名前空間で識別子を見つけられませんでした。

次の例では C2251 が生成されます。

```
// C2251.cpp
// compile with: /c
namespace A {
   namespace B {
      void f1();
   }

   using namespace B;
}

void A::f1() {}   // C2251
void A::B::f1() {}   // OK
```