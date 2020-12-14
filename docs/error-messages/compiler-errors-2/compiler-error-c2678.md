---
description: 詳細については、「コンパイラエラー C2678」を参照してください。
title: コンパイラエラー C2678
ms.date: 11/04/2016
f1_keywords:
- C2678
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
ms.openlocfilehash: 9314d3d0201e38c2ce13b48f59356e04e0925a3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220865"
---
# <a name="compiler-error-c2678"></a>コンパイラエラー C2678

二項演算子 'operator' : 型 'type' の左オペランドを扱う演算子が定義されていません (または変換できません)

この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。

左側のオペランドが const で修飾されていても、演算子が非 const 引数を受け取るように定義されている場合に、C2678 が発生する可能性があります。

## <a name="examples"></a>例

次の例では、C2678 を生成し、その修正方法を示しています。

```cpp
// C2678a.cpp
// Compile by using: cl /EHsc /W4 C2678a.cpp
struct Combo {
   int number;
   char letter;
};

inline Combo& operator+=(Combo& lhs, int rhs) {
   lhs.number += rhs;
   return lhs;
}

int main() {
   Combo const combo1{ 42, 'X' };
   Combo combo2{ 13, 'Z' };

   combo1 += 6; // C2678
   combo2 += 9; // OK - operator+= matches non-const Combo
}
```

C2678 は、ネイティブ メンバーを固定せずにその中でメンバー関数を呼び出した場合にも発生する可能性があります。

次の例では、C2678 を生成し、その修正方法を示しています。

```cpp
// C2678.cpp
// compile with: /clr /c
struct S { int _a; };

ref class C {
public:
   void M( S param ) {
      test = param;   // C2678

      // OK
      pin_ptr<S> ptest = &test;
      *ptest = param;
   }
   S test;
};
```
