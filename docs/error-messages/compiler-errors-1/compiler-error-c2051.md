---
description: 詳細については、「コンパイラエラー C2051」を参照してください。
title: コンパイラエラー C2051
ms.date: 11/04/2016
f1_keywords:
- C2051
helpviewer_keywords:
- C2051
ms.assetid: 81c0469a-78e2-49fa-bd76-97cdb135e3ea
ms.openlocfilehash: ceea0466ef5f285c9cf7b3aa6bdf312ec25f283e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175015"
---
# <a name="compiler-error-c2051"></a>コンパイラエラー C2051

case 式が定数ではありません

Case 式は整数定数でなければなりません。

次の例では、C2051 が生成されます。

```cpp
// C2051.cpp
class X {};

int main() {
   static X x;
   int i = 0;

   switch (i) {
      case x:   // C2051 use constant expression to resolve error
         break;
      default:
         break;
   }
}
```

考えられる解決策:

```cpp
// C2051b.cpp
class X {};

int main() {
   static X x;
   int i = 0;

   switch (i) {
      case 1:
         break;
      default:
         break;
   }
}
```
