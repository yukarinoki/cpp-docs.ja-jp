---
description: 詳細については、「コンパイラエラー C2884」を参照してください。
title: コンパイラ エラー C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: 008c72ba24bdea260fffc4a49145ecf67c610b15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332334"
---
# <a name="compiler-error-c2884"></a>コンパイラ エラー C2884

' name ': using 宣言によって導入されたローカル関数 ' function ' と競合しています

関数を複数回定義しようとしました。 最初の定義はローカル定義です。 2つ目は、宣言を持つ名前空間のものです **`using`** 。

次の例では、C2884 が生成されます。

```cpp
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
