---
title: コンパイラの警告 (レベル 4) C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: fcb66fca7e5b8708171849f885518c15b8355ac4
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541731"
---
# <a name="compiler-warning-level-4-c4239"></a>コンパイラの警告 (レベル 4) C4239

非標準の拡張機能が使用されています: ' token ': ' type ' から ' type ' への変換

この型変換はC++標準では許可されていませんが、ここでは拡張機能として許可されています。 この警告には、違反している言語規則について説明する、少なくとも1行の説明が続きます。

## <a name="example"></a>使用例

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

## <a name="example"></a>使用例

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