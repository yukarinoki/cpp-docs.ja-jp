---
description: 詳細については、「コンパイラエラー C2681」を参照してください。
title: コンパイラエラー C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 3b002e6260787e60377d726bcceb6db41fce532a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267782"
---
# <a name="compiler-error-c2681"></a>コンパイラエラー C2681

' type ': 名前の式の型が無効です。

キャスト演算子が無効な型から変換しようとしました。 たとえば、 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 演算子を使用して式をポインター型に変換する場合、ソース式はポインターである必要があります。

次の例では、C2681 が生成されます。

```cpp
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```
