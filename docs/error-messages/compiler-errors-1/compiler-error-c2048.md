---
description: 詳細については、「コンパイラエラー C2048」を参照してください。
title: コンパイラ エラー C2048
ms.date: 11/04/2016
f1_keywords:
- C2048
helpviewer_keywords:
- C2048
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
ms.openlocfilehash: cc87d0ca1670daa4cb137f4c3053030d188884e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175080"
---
# <a name="compiler-error-c2048"></a>コンパイラ エラー C2048

switch 文の中に 2 つ以上の 'default' があります。

**`switch`** ステートメントに複数のラベルが含まれてい **`default`** ます。 エラーを解決するには、いずれかの **`default`** ラベルを削除します。

次の例では C2048 が生成されます。

```cpp
// C2048.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
      default:   // C2048
         a = 3;
   }
}
```

考えられる解決策:

```cpp
// C2048b.cpp
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
