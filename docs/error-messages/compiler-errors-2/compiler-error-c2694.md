---
description: 詳細については、「コンパイラエラー C2694」を参照してください。
title: コンパイラエラー C2694
ms.date: 11/04/2016
f1_keywords:
- C2694
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
ms.openlocfilehash: 4da5362a9c20a2bae10d2a201650f4312d455164
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326658"
---
# <a name="compiler-error-c2694"></a>コンパイラエラー C2694

' override ': オーバーライドする仮想関数は、基底クラスの仮想メンバー関数 ' base ' よりも制限の緩い例外指定を含んでいます

仮想関数がオーバーライドされましたが、 [/za](../../build/reference/za-ze-disable-language-extensions.md)では、オーバーライドする関数には制限の緩い [例外指定](../../cpp/exception-specifications-throw-cpp.md)がありました。

次の例では、C2694 が生成されます。

```cpp
// C2694.cpp
// compile with: /Za /c
class MyBase {
public:
   virtual void f(void) throw(int) {
   }
};

class Derived : public MyBase {
public:
   void f(void) throw(...) {}   // C2694
   void f2(void) throw(int) {}   // OK
};
```
