---
description: '詳細情報: コンパイラの警告 (レベル 2) C4356'
title: コンパイラの警告 (レベル 2) C4356
ms.date: 11/04/2016
f1_keywords:
- C4356
helpviewer_keywords:
- C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
ms.openlocfilehash: 328f177c90b34f17f8f8c5ec480cb829a22f2f14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173572"
---
# <a name="compiler-warning-level-2-c4356"></a>コンパイラの警告 (レベル 2) C4356

' member ': 静的データメンバーを派生クラスで初期化することはできません

静的データメンバーの初期化の形式が正しくありません。 コンパイラで初期化が受け入れられました。 警告を回避するには、基底クラスを使用してメンバーを初期化します。

この警告を非表示にするには、 [warning](../../preprocessor/warning.md) プラグマを使用します。

次の例では、C4356 が生成されます。

```cpp
// C4356.cpp
// compile with: /W2 /EHsc
#include <iostream>

template <class T>
class C {
   static int n;
};

class D : C<int> {};

int D::n = 0; // C4356
// try the following line instead
// int C<int>::n = 0;

class A {
public:
   static int n;
};

class B : public A {};

int B::n = 10;   // C4356
// try the following line instead
// int A::n = 99;

int main() {
   using namespace std;
   cout << B::n << endl;
}
```
