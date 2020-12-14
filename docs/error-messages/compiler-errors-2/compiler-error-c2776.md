---
description: 詳細については、「コンパイラエラー C2776」を参照してください。
title: コンパイラエラー C2776
ms.date: 11/04/2016
f1_keywords:
- C2776
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
ms.openlocfilehash: 75e0121c61fd55aa89e6ffcc6e1ed00137fcaaca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298137"
---
# <a name="compiler-error-c2776"></a>コンパイラエラー C2776

プロパティごとに指定できる ' get ' メソッドは1つだけです

`get` [Property](../../cpp/property-cpp.md)拡張属性で指定できる関数は1つだけです。 このエラー `get` は、複数の関数が指定されている場合に発生します。

次の例では、C2776 が生成されます。

```cpp
// C2776.cpp
struct A {
   __declspec(property(get=GetProp,get=GetPropToo))
   // try the following line instead
   // __declspec(property(get=GetProp))
      int prop;   // C2776
   int GetProp(void);
   int GetPropToo(void);
};
```
