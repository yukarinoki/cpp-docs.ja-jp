---
description: 詳細については、「コンパイラエラー C2635」を参照してください。
title: コンパイラエラー C2635
ms.date: 11/04/2016
f1_keywords:
- C2635
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
ms.openlocfilehash: 8ecc6faaefb3dea5f0cfcded4d6817a807580254
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123384"
---
# <a name="compiler-error-c2635"></a>コンパイラエラー C2635

' identifier1 * ' を ' identifier2 ' に変換できません \* 。仮想基底クラスからの変換は暗黙的です。

変換には、基底クラスから派生クラスへのキャストが必要です **`virtual`** が、これは許可されていません。

次の例では、C2635 が生成されます。

```cpp
// C2635.cpp
class B {};
class D : virtual public B {};
class E : public B {};

int main() {
   B b;
   D d;
   E e;

   D * pD = &d;
   E * pE = &e;
   pD = (D*)&b;   // C2635
   pE = (E*)&b;   // OK
}
```
