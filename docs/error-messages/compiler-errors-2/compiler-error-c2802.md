---
title: コンパイラ エラー C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: f872a4753907cd78c9118c22498777d5acc5b2fd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214582"
---
# <a name="compiler-error-c2802"></a>コンパイラ エラー C2802

静的メンバー ' operator operator ' に仮引数がありません。

メンバー関数によって宣言された演算子には、 **`static`** 少なくとも1つのパラメーターが必要です。

次の例では、C2802 が生成されます。

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
