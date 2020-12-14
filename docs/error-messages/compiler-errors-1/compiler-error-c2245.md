---
description: 詳細については、「コンパイラエラー C2245」を参照してください。
title: コンパイラ エラー C2245
ms.date: 11/04/2016
f1_keywords:
- C2245
helpviewer_keywords:
- C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
ms.openlocfilehash: b304fa30164576ed9d2c1f3fcf21dfe2f8e2cbc2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302219"
---
# <a name="compiler-error-c2245"></a>コンパイラ エラー C2245

friend と指定された存在しないメンバー関数 'function' (メンバー関数署名がオーバーロードと一致しません)

フレンドとして指定された関数がコンパイラによって検出されませんでした。

次の例では C2245 が生成されます。

```cpp
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
