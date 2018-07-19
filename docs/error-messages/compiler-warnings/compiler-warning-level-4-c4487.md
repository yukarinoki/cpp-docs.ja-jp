---
title: コンパイラの警告 (レベル 4) C4487 |Microsoft ドキュメント
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
ms.openlocfilehash: 80008dbcfbebe4e91398e651e361efe7df30b641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293183"
---
# <a name="compiler-warning-level-4-c4487"></a>コンパイラの警告(レベル 4) C4487
'derived_class_function': 継承された非仮想メソッド 'base_class_function' と一致しますが、'new' に明示的に設定されていません  
  
 派生クラスで関数が非仮想基底クラス関数と同じシグネチャを持ちます。 C4487 は、派生クラスの関数が基底クラスの関数をオーバーライドできません。 派生クラスとしての関数を明示的にマーク`new`この警告を解決します。  
  
 詳細については、次を参照してください。 [new (の新しいスロット vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C4487 を生成します。  
  
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