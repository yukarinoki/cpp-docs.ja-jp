---
title: コンパイラ エラー C2073
ms.date: 11/04/2016
f1_keywords:
- C2073
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
ms.openlocfilehash: 2b45d512224ec32459e6da040a6abb0211278e78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303321"
---
# <a name="compiler-error-c2073"></a>コンパイラ エラー C2073

'identifier': 部分的に初期化された配列の要素は、既定のコンス トラクターをいる必要があります

少なすぎます初期化子は、ユーザー定義型または定数の配列に指定されました。 配列メンバーを明示的な初期化子と、対応するコンス トラクターが指定されていない場合は、既定のコンス トラクターを指定する必要があります。

次の例では、C2073 が生成されます。

```
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```