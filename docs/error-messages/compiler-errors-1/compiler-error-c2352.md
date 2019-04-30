---
title: コンパイラ エラー C2352
ms.date: 11/04/2016
f1_keywords:
- C2352
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
ms.openlocfilehash: 387738faa5b55e60cbb9df2185efcb94098011d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388801"
---
# <a name="compiler-error-c2352"></a>コンパイラ エラー C2352

'class::function' : 静的でないメンバー関数の呼び出しが正しくありません

`static` メンバー関数は、静的でないメンバー関数を呼び出しました。 または、静的でないメンバー関数がクラスの外部から静的関数として呼び出されました。

次の例では、C2352 を生成し、その修正方法を示しています。

```
// C2352.cpp
// compile with: /c
class CMyClass {
public:
   static void func1();
   void func2();
   static void func3() {
      func2();   // C2352 calls nonstatic func2
      func1();   // OK calls static func1
   }
};
```

次の例では、C2352 を生成し、その修正方法を示しています。

```
// C2352b.cpp
class MyClass {
public:
   void MyFunc() {}
   static void MyFunc2() {}
};

int main() {
   MyClass::MyFunc();   // C2352
   MyClass::MyFunc2();   // OK
}
```