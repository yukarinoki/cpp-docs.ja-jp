---
title: コンパイラ エラー C2245
ms.date: 11/04/2016
f1_keywords:
- C2245
helpviewer_keywords:
- C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
ms.openlocfilehash: 53288d86a59fe2cd31ddac4af7766360544c65c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603945"
---
# <a name="compiler-error-c2245"></a>コンパイラ エラー C2245

friend と指定された存在しないメンバー関数 'function' (メンバー関数署名がオーバーロードと一致しません)

フレンドとして指定された関数がコンパイラによって検出されませんでした。

次の例では C2245 が生成されます。

```
// C2245.cpp
// compile with: /c
class B {
   void f(int i);
};

class A {
   int m_i;
   friend void B::f(char);   // C2245
   // try the following line instead
   // friend void B::f(int);
};

void B::f(int i) {
   A a;
   a.m_i = 0;
}
```