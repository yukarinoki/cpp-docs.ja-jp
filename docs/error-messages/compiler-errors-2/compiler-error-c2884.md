---
title: コンパイラ エラー C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d6014aa44dd1c2a5f1b0418a7171b239a754ec33
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220198"
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
