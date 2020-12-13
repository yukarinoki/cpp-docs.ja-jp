---
description: 詳細については、「コンパイラエラー C2034」を参照してください。
title: コンパイラエラー C2034
ms.date: 11/04/2016
f1_keywords:
- C2034
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
ms.openlocfilehash: cbc3f8788e495a95b1eb5fb848322815b6f78d57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175418"
---
# <a name="compiler-error-c2034"></a>コンパイラエラー C2034

' identifier ': ビットフィールドの型が、ビット数に対して小さすぎます。

ビットフィールド宣言のビット数が基本データ型のサイズを超えています。

次の例では、C2034 が生成されます。

```cpp
// C2034.cpp
struct A {
   char test : 9;   // C2034, char has 8 bits
};
```

考えられる解決策:

```cpp
// C2034b.cpp
// compile with: /c
struct A {
   char test : 8;
};
```
