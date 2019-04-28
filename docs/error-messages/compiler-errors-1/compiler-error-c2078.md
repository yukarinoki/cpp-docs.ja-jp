---
title: コンパイラ エラー C2078
ms.date: 11/04/2016
f1_keywords:
- C2078
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
ms.openlocfilehash: a800a6efa6e02f323b4b6597f1aa983f13674e83
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182809"
---
# <a name="compiler-error-c2078"></a>コンパイラ エラー C2078

初期化子の数が多すぎます。

初期化子の数が初期化されるオブジェクトの数を超えています。

初期化子リストで内側の中かっこが省略されている場合、コンパイラは、オブジェクトおよび内部のオブジェクトに対する正しい初期化子の割り当てを推測できます。 中かっこを完全な形で使用すれば、あいまいさが排除され、正しい割り当てが行われます。 中かっこを部分的に使用すると、オブジェクトへの初期化子の割り当てがあいまいになり、C2078 が発生することがあります。

次の例では、C2078 を生成し、その修正方法を示しています。

```
// C2078.cpp
// Compile by using: cl /c /W4 C2078.cpp
struct S {
   struct {
      int x, y;
   } z[2];
};

int main() {
   int d[2] = {1, 2, 3};   // C2078
   int e[2] = {1, 2};      // OK

   char a[] = {"a", "b"};  // C2078
   char *b[] = {"a", "b"}; // OK
   char c[] = {'a', 'b'};  // OK

   S s1{1, 2, 3, 4};       // OK
   S s2{{1, 2}, {3, 4}};   // C2078
   S s3{{1, 2, 3, 4}};     // OK
   S s4{{{1, 2}, {3, 4}}}; // OK
}
```