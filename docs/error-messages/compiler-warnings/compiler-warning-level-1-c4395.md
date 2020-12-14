---
description: '詳細情報: コンパイラの警告 (レベル 1) C4395'
title: コンパイラの警告 (レベル 1) C4395
ms.date: 11/04/2016
f1_keywords:
- C4395
helpviewer_keywords:
- C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
ms.openlocfilehash: 12a25f523a4f55bffc3bb68517538b4a9986407e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311293"
---
# <a name="compiler-warning-level-1-c4395"></a>コンパイラの警告 (レベル 1) C4395

' function ': メンバー関数は、initonly データメンバー ' member ' のコピーで呼び出されます

[Initonly (C++/cli)](../../dotnet/initonly-cpp-cli.md)データメンバーでメンバー関数が呼び出されました。  C4395 は、 **initonly** データメンバーが関数によって変更できないことを警告します。

次の例では、C4395 が生成されます。

```cpp
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
