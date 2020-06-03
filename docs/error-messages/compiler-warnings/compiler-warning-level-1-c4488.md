---
title: コンパイラの警告 (レベル 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: b83845f0ed0efeee6485780c7e4f828e40473e9e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186700"
---
# <a name="compiler-warning-level-1-c4488"></a>コンパイラの警告 (レベル 1) C4488

' function ': インターフェイスメソッド ' interface_method ' を実装するには、' keyword ' キーワードが必要です

クラスは、直接継承元のインターフェイスのすべてのメンバーを実装する必要があります。 実装されたメンバーは、パブリックアクセシビリティを持つ必要があり、virtual としてマークする必要があります。

## <a name="example"></a>例

C4488 は、実装されたメンバーがパブリックでない場合に発生する可能性があります。 次の例では、C4488 が生成されます。

```cpp
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

C4488 は、実装されたメンバーが virtual とマークされていない場合に発生する可能性があります。 次の例では、C4488 が生成されます。

```cpp
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```
