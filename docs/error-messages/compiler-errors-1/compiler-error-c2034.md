---
title: コンパイラ エラー C2034
ms.date: 11/04/2016
f1_keywords:
- C2034
helpviewer_keywords:
- C2034
ms.assetid: 953d70fa-bde9-4ce6-a55d-741e7bc63ff4
ms.openlocfilehash: 4b4fe769f78e5f826ba08d4819019210f21f860f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400477"
---
# <a name="compiler-error-c2034"></a>コンパイラ エラー C2034

'identifier': 型のビット フィールドのビット数には小さすぎます

ビット フィールドの宣言内のビット数は、基本型のサイズを超えています。

次の例では、C2034 が生成されます。

```
// C2034.cpp
struct A {
   char test : 9;   // C2034, char has 8 bits
};
```

考えられる解決方法:

```
// C2034b.cpp
// compile with: /c
struct A {
   char test : 8;
};
```