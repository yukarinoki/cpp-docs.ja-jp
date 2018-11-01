---
title: コンパイラの警告 (レベル 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 067d1aef41280f4d14fe799e4f4ee26a9f1b9f5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451513"
---
# <a name="compiler-warning-level-4-c4239"></a>コンパイラの警告 (レベル 4) C4239

標準の拡張機能を使用します 'token': 'type' から 'type' への変換。

この型の変換は、C++ 標準で許可されていませんが、許可されている拡張機能としては、ここです。 この警告が常に、少なくとも 1 つの行の説明の言語規則が違反していることを示す続きます。

## <a name="example"></a>例

次の例では、C4239 が生成されます。

```
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

## <a name="example"></a>例

整数型から列挙型への変換は厳密には許可されません。

次の例では、C4239 が生成されます。

```
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```