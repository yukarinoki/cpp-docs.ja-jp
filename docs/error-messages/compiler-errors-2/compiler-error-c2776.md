---
title: コンパイラ エラー C2776
ms.date: 11/04/2016
f1_keywords:
- C2776
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
ms.openlocfilehash: 200fbc5c42a6b735c072c093ec4cb4f081031824
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652144"
---
# <a name="compiler-error-c2776"></a>コンパイラ エラー C2776

プロパティごとに 1 つだけの 'get' メソッドを指定できます。

いずれかを指定することができますのみ`get`で機能、[プロパティ](../../cpp/property-cpp.md)拡張属性。 このエラーが発生したときに複数`get`関数を指定します。

次の例では、C2776 が生成されます。

```
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