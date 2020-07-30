---
title: コンパイラ エラー C2048
ms.date: 11/04/2016
f1_keywords:
- C2048
helpviewer_keywords:
- C2048
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
ms.openlocfilehash: 483e4d706a1c08899e6cd6e1ec561a21ed805014
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210437"
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
