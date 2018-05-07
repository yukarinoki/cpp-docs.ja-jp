---
title: コンパイラ エラー C3253 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3253
dev_langs:
- C++
helpviewer_keywords:
- C3253
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89e1452c3893d30fa3beea0e436da61355b902a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3253"></a>コンパイラ エラー C3253
'function': 明示的なオーバーライド エラー  
  
 明示的なオーバーライドが正しく指定されていません。 たとえば、純粋としても指定されているオーバーライドの実装を指定することはできません。 詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)です。  
  
 次の例では、C3253 が生成されます。  
  
```  
// C3253.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
   void b();  
   void c();  
};  
  
public ref struct R : I {  
   virtual void a() = 0, I::a {}   // C3253  
   virtual void b() = I::a {}   // OK  
   virtual void c() = 0;   // OK  
};  
```