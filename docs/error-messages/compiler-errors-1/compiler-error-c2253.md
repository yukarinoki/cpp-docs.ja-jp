---
title: コンパイラ エラー C2253 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2253
dev_langs:
- C++
helpviewer_keywords:
- C2253
ms.assetid: bd6445ae-b2c1-4669-9657-a8f4acf80b16
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 022db574e40317417c64cf9143c7d9b88468ca1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2253"></a>コンパイラ エラー C2253
'function': 純粋関数または抽象オーバーライド指定子の仮想関数でのみ許可されます  
  
 非仮想関数が純粋に指定された`virtual`です。  
  
 次の例では、C2253 が生成されます。  
  
```  
// C2253.cpp  
// compile with: /c  
class A {  
public:  
   void func1() = 0;   // C2253 not virtual  
   virtual void func2() = 0;   // OK  
};  
```  
  
 次の例では、C2253 が生成されます。  
  
```  
// C2253_2.cpp  
// compile with: /clr /c  
ref struct A {  
   property int Prop_3 {  
      int get() abstract;   // C2253  
      // try the following line instead  
      // virtual int get() abstract;  
  
      void set(int i) abstract;   // C2253  
      // try the following line instead  
      // virtual void set(int i) abstract;  
   }  
};  
```