---
title: コンパイラ エラー C3754
ms.date: 11/04/2016
f1_keywords:
- C3754
helpviewer_keywords:
- C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
ms.openlocfilehash: e03ac39213429fbbb9f289be3514718985c04b4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386643"
---
# <a name="compiler-error-c3754"></a>コンパイラ エラー C3754

delegate コンス トラクター: メンバー関数 'function' は型 'type' のインスタンスで呼び出すことはできません

関数を含まない型へのポインターを使用して関数呼び出しが行われました。

## <a name="example"></a>例

次の例では、C3754 が生成されます。

```
// C3754a.cpp
// compile with: /clr
using namespace System;

delegate void MyDel();

interface class MyInterface {};

ref struct MyClass : MyInterface {
   void f() {}
};

int main() {
   MyInterface^ p = gcnew MyClass;
   MyDel^ q = gcnew MyDel(p, &MyClass::f);   // C3754
   // try the following line instead
//   MyDel^ q = gcnew MyDel(safe_cast<MyClass^>(p), &MyClass::f);
}
```
