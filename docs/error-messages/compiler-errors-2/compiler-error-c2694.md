---
title: コンパイラ エラー C2694
ms.date: 11/04/2016
f1_keywords:
- C2694
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
ms.openlocfilehash: 4897512f6bd27465b7281d7a27757918128202d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367747"
---
# <a name="compiler-error-c2694"></a>コンパイラ エラー C2694

'override': 基底クラスよりも少ない例外指定を仮想メンバー関数 'base' が仮想関数のオーバーライド

仮想関数がオーバーライドされる[/Za](../../build/reference/za-ze-disable-language-extensions.md)、緩い関数をオーバーライドする必要がある[例外仕様](../../cpp/exception-specifications-throw-cpp.md)します。

次の例では、C2694 が生成されます。

```
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