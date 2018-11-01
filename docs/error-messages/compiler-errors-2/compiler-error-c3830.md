---
title: コンパイラ エラー C3830
ms.date: 11/04/2016
f1_keywords:
- C3830
helpviewer_keywords:
- C3830
ms.assetid: c9798f88-5001-4067-9fb1-09957ddc6fa8
ms.openlocfilehash: 5c484b2b9267bf5f9be3593c20c8b261dafde206
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631414"
---
# <a name="compiler-error-c3830"></a>コンパイラ エラー C3830

'type1': 'type2'、値の型はインターフェイス クラスからのみ継承できますから継承できません。

値型では、基本クラスを継承できません。  詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3830 が生成されます。

```
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
