---
title: コンパイラの警告 (レベル 2) C4356
ms.date: 11/04/2016
f1_keywords:
- C4356
helpviewer_keywords:
- C4356
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
ms.openlocfilehash: 218aac1cc98d9b119490a547d63b4b5ee83e53df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402464"
---
# <a name="compiler-warning-level-2-c4356"></a>コンパイラの警告 (レベル 2) C4356

'member': 静的データ メンバーは派生クラスを使って初期化できません

静的データ メンバーの初期化が正しくありません。 コンパイラでは、初期化が受け入れられます。 警告を回避するには、基本クラスを使用してメンバーを初期化します。

使用して、[警告](../../preprocessor/warning.md)この警告を抑制するプラグマ。

次の例では、C4356 が生成されます。

```
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