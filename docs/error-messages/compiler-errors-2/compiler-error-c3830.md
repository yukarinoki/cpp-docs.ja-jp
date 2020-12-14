---
description: 詳細については、「コンパイラエラー C3830」を参照してください。
title: コンパイラ エラー C3830
ms.date: 11/04/2016
f1_keywords:
- C3830
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
ms.openlocfilehash: 6d5dff2b45a79d3156533caf8020497f422d2474
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249231"
---
# <a name="compiler-error-c3830"></a>コンパイラ エラー C3830

' type1 ': ' type1 ' から継承することはできません。値型はインターフェイスクラスからのみ継承できます

値型は基底クラスを継承できません。  詳細については、「[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3830 が生成されます。

```cpp
// C3830a.cpp
// compile with: /clr /c
public value struct MyStruct4 {
   int i;
};

public value class MyClass : public MyStruct4 {};   // C3830

// OK
public interface struct MyInterface4 {
   void i();
};

public value class MyClass2 : public MyInterface4 {
public:
   virtual void i(){}
};
```
