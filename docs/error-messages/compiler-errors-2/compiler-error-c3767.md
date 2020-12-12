---
description: 詳細については、「コンパイラエラー C3767」を参照してください。
title: コンパイラ エラー C3767
ms.date: 11/04/2016
f1_keywords:
- C3767
helpviewer_keywords:
- C3767
ms.assetid: 5247cdcd-639c-4527-bd37-37e74c4e8fab
ms.openlocfilehash: 6d8780dde6ba6d831b1e47c174ef3609086c46ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291845"
---
# <a name="compiler-error-c3767"></a>コンパイラ エラー C3767

'関数' : 候補の関数はアクセス可能ではありません。

クラスで定義されたフレンド関数は、グローバル名前空間スコープで定義および宣言された関数として扱われることを想定していません。 ただし、引数依存の検索で検出することはできます。

C3767 は、互換性に影響する変更によって発生することもあります。ネイティブ型は、 **/clr** コンパイルでは既定でプライベートになりました。詳細については、「 [型の可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) 」を参照してください。

## <a name="example"></a>例

次の例では、C3767 が生成されます。

```cpp
// C3767a.cpp
// compile with: /clr
using namespace System;
public delegate void TestDel();

public ref class MyClass {
public:
   static event TestDel^ MyClass_Event;
};

public ref class MyClass2 : public MyClass {
public:
   void Test() {
      MyClass^ patient = gcnew MyClass;
      patient->MyClass_Event();
    }
};

int main() {
   MyClass^ x = gcnew MyClass;
   x->MyClass_Event();   // C3767

   // OK
   MyClass2^ y = gcnew MyClass2();
   y->Test();
};
```

次の例では、C3767 が生成されます。

```cpp
// C3767c.cpp
// compile with: /clr /c

ref class Base  {
protected:
   void Method() {
      System::Console::WriteLine("protected");
   }
};

ref class Der : public Base {
   void Method() {
      ((Base^)this)->Method();   // C3767
      // try the following line instead
      // Base::Method();
   }
};
```
