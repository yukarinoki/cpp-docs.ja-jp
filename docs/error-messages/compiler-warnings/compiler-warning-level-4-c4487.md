---
title: コンパイラの警告 (レベル 4) C4487 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4487
dev_langs:
- C++
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffc1a25d362cad95f2aad43d626e4918955903f5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135842"
---
# <a name="compiler-warning-level-4-c4487"></a>コンパイラの警告(レベル 4) C4487

'derived_class_function': 継承された非仮想メソッド 'base_class_function' と一致しますが、'new' に明示的に設定されていません

派生クラスで、関数には、非仮想基底クラス関数と同じシグネチャがあります。 C4487 は、派生クラスの関数が基底クラスの関数をオーバーライドできません。 派生クラスとしての関数を明示的にマーク`new`この警告を解決します。

詳細については、次を参照してください。 [new (新規のスロット vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C4487 が生成されます。

```
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```