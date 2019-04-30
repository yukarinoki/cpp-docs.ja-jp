---
title: コンパイラ エラー C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d920629dc0697d0f2fdd05ac5aca6118b89b88cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378857"
---
# <a name="compiler-error-c2884"></a>コンパイラ エラー C2884

'name': ローカル関数 'function' と競合してを使用して宣言によって導入されました。

関数を複数回定義しようとしました。 最初の定義は、ローカルの定義です。 持つ名前空間からの 2 つ目は、`using`宣言します。

次の例では、C2884 が生成されます。

```
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```