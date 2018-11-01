---
title: コンパイラの警告 (レベル 1) C4395
ms.date: 11/04/2016
f1_keywords:
- C4395
helpviewer_keywords:
- C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
ms.openlocfilehash: 27503b94a18b949637293201203e18793f5e7788
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676357"
---
# <a name="compiler-warning-level-1-c4395"></a>コンパイラの警告 (レベル 1) C4395

'function': initonly データ メンバー 'member' のコピーでメンバー関数が呼び出されます

メンバー関数が呼び出された、 [initonly (C +/cli CLI)](../../dotnet/initonly-cpp-cli.md)データ メンバー。  C4395、 **initonly**データ メンバーは、関数によって変更されることはできません。

次の例では、C4395 が生成されます。

```
// C4395.cpp
// compile with: /W1 /clr
public value class V {
public:
   V(int data) : m_data(data) {}

   void Mutate() {
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);
      m_data *= 2;
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);
   }

   int m_data;
};

public ref class R {
public:
   static void f() {
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
      v.Mutate();   // C4395
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
   }

private:
   initonly static V v = V(4);
};

int main() {
   R::f();
}
```