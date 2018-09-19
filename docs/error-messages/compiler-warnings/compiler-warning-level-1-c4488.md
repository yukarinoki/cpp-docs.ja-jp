---
title: コンパイラの警告 (レベル 1) C4488 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4488
dev_langs:
- C++
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2cccedada47519ada55353cb44faab0e34cf03
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118272"
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