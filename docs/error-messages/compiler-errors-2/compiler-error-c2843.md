---
description: 詳細については、「コンパイラエラー C2843」を参照してください。
title: コンパイラ エラー C2843
ms.date: 11/04/2016
f1_keywords:
- C2843
helpviewer_keywords:
- C2843
ms.assetid: 9d3f2ac4-eea5-4fed-abeb-e752f442bfcc
ms.openlocfilehash: 3ca201167d6745de8d0b0e8f27a414eebe8a75a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119958"
---
# <a name="compiler-error-c2843"></a>コンパイラ エラー C2843

'member': マネージド型または WinRT 型の非静的データ メンバーのアドレスを取得できません

マネージドまたは WinRT クラスまたはインターフェイスの非静的データ メンバーのアドレスを取得するには、インスタンスが必要です。

次の例では、C2843 を生成し、その修正方法を示しています。

```cpp
// C2843_2.cpp
// compile with: /clr
public ref class C {
public:
   int m_i;
};

ref struct MyStruct {
   static void sf() {}
   void f() {}
};

int main() {
   MyStruct ^ps = gcnew MyStruct;
   void (__clrcall MyStruct::*F1)() = & MyStruct::f;   // C2843
   void (__clrcall MyStruct::*F2)() = & ps->f;   // C2843
   void (__clrcall MyStruct::*F3)();   // C2843

   void (__clrcall *F5)() = MyStruct::sf;   // OK
   void (__clrcall *F6)() = & ps->sf;   // OK

   interior_ptr<int> i = &C::m_i; // C2843
   C ^x = gcnew C();
   interior_ptr<int> ii = &x->m_i;
}
```
