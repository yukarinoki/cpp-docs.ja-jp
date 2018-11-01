---
title: コンパイラ エラー C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 8b311052d3a3525090d954c0dc8cee20e985b1b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632698"
---
# <a name="compiler-error-c2681"></a>コンパイラ エラー C2681

'type': 名前の無効な式の型

キャスト演算子が、無効な型から変換しようとしました。 たとえば、使用する場合、 [dynamic_cast](../../cpp/dynamic-cast-operator.md)ポインター型では、元の式に式を変換する演算子はポインターである必要があります。

次の例では、C2681 が生成されます。

```
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```