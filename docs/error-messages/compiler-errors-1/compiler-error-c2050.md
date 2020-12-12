---
description: 詳細については、「コンパイラエラー C2050」を参照してください。
title: コンパイラエラー C2050
ms.date: 11/04/2016
f1_keywords:
- C2050
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
ms.openlocfilehash: a6e6221b0985ee509953b517ae04de9f0962fe3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175041"
---
# <a name="compiler-error-c2050"></a>コンパイラエラー C2050

switch 式が整数ではありません

式は、 **`switch`** 整数以外の値に評価されます。 このエラーを解決するには、switch ステートメントで整数値のみを使用します。

次の例では、C2050 が生成されます。

```cpp
// C2050.cpp
int main() {
   int a = 1;
   switch ("a") {   // C2050
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```

考えられる解決策:

```cpp
// C2050b.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```
