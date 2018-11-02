---
title: コンパイラの警告 (レベル 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: c816c1b3f5481ccff19fd2a2377c5fc98f950fee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577828"
---
# <a name="compiler-warning-level-1-c4488"></a>コンパイラの警告 (レベル 1) C4488

'function': 'keyword' キーワード 'interface_method' インターフェイス メソッドを実装する必要があります

クラスは、直接継承するインターフェイスのすべてのメンバーを実装する必要があります。 実装されるメンバーは、パブリック アクセシビリティがあり、virtual に指定する必要があります。

## <a name="example"></a>例

C4488 は、実装されるメンバーがパブリックでない場合に発生することができます。 次の例では、C4488 が生成されます。

```
// C4488.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

// implemented member not public
ref class B : MyI { virtual void f1() {} };  // C4488

// OK
ref class C : MyI {
public:
   virtual void f1() {}
};
```

## <a name="example"></a>例

C4488 は、実装されるメンバーが仮想にマークされていない場合に発生することができます。 次の例では、C4488 が生成されます。

```
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```