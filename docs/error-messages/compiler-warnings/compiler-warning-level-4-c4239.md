---
description: '詳細情報: コンパイラの警告 (レベル 4) C4239'
title: コンパイラの警告 (レベル 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 635795392b5544f4985305a02e8534188c049224
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334856"
---
# <a name="compiler-warning-level-4-c4239"></a>コンパイラの警告 (レベル 4) C4239

非標準の拡張機能が使用されています: ' token ': ' type ' から ' type ' への変換

この型変換は C++ 標準では許可されていませんが、ここでは拡張機能として許可されています。 この警告には、違反している言語規則について説明する、少なくとも1行の説明が続きます。

## <a name="examples"></a>例

次の例では、C4239 が生成されます。

```cpp
// C4239.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

void func(void) {
   C & rC = C();   // C4239
   const C & rC2 = C();   // OK
   rC2;
}
```

整数型から列挙型への変換は、厳密には許可されていません。

次の例では、C4239 が生成されます。

```cpp
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```
