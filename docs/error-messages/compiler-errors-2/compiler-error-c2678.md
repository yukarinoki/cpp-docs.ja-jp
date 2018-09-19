---
title: コンパイラ エラー C2678 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2678
dev_langs:
- C++
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2af18a98304cafc70441acda7ef0ebb1a827d88
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035358"
---
# <a name="compiler-error-c2678"></a>コンパイラ エラー C2678

二項演算子 'operator' : 型 'type' の左オペランドを扱う演算子が定義されていません (または変換できません)

この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。

## <a name="example"></a>例

左側のオペランドが const で修飾されていても、演算子が非 const 引数を受け取るように定義されている場合に、C2678 が発生する可能性があります。

次の例では、C2678 を生成し、その修正方法を示しています。

```
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

## <a name="example"></a>例

C2678 は、ネイティブ メンバーを固定せずにその中でメンバー関数を呼び出した場合にも発生する可能性があります。

次の例では、C2678 を生成し、その修正方法を示しています。

```
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
