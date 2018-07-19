---
title: コンパイラの警告 (レベル 1) C4374 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4374
dev_langs:
- C++
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb6304fa921d4b67c5dc33bfa54fbcbb3a722511
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276673"
---
# <a name="compiler-warning-level-1-c4374"></a>コンパイラの警告 (レベル 1) C4374
'function1': インターフェイス メソッドは非仮想メソッド 'function2' によって実装されません  
  
 コンパイラが予期されましたが、[仮想](../../cpp/virtual-specifier.md)メソッド定義のキーワードです。  
  
 次の例では、C4374 が生成されます。  
  
```  
// C4374.cpp  
// compile with: /clr /W1 /c /WX  
public interface class I {  
   void f();  
};  
  
public ref struct B {  
   void f() {  
      System::Console::WriteLine("B::f()");  
   }  
};  
  
public ref struct C {  
   virtual void f() {  
      System::Console::WriteLine("C::f()");  
   }  
};  
  
public ref struct D : B, I {};   // C4374  
public ref struct E : C, I {};   // OK  
```