---
title: コンパイラ エラー C2064 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2064
dev_langs:
- C++
helpviewer_keywords:
- C2064
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3e5e21d7c33c84bb531b53c08aefbfce9dc7fd8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2064"></a>コンパイラ エラー C2064
N 引数を取り込む関数には評価されません。  
  
 式を使用して関数の呼び出しが行われています。 この式は、指定された引数値を取り込む関数へのポインターとして評価されません。  
  
 この例のコードでは、関数ではないものを関数として呼び出そうとしています。 次の例では C2064 が生成されます。  
  
```  
// C2064.cpp  
int i, j;  
char* p;  
void func() {  
   j = i();    // C2064, i is not a function  
   p();        // C2064, p doesn't point to a function  
}  
```  
  
 オブジェクト インスタンスのコンテキストから、静的でないメンバー関数へのポインターを呼び出す必要があります。 次の例では C2064 が生成され、その修正方法が示されています。  
  
```  
// C2064b.cpp  
struct C {  
   void func1(){}  
   void func2(){}  
};  
  
typedef void (C::*pFunc)();  
  
int main() {  
   C c;  
   pFunc funcArray[2] = {&C::func1, &C::func2};  
   (funcArray[0])();    // C2064   
   (c.*funcArray[0])(); // OK - function called in instance context  
}  
  
```  
  
 クラス内で、メンバー関数ポインターは、呼び出し元のオブジェクトのコンテキストも示す必要があります。 次の例では C2064 が生成され、その修正方法が示されています。  
  
```  
// C2064d.cpp  
// Compile by using: cl /c /W4 C2064d.cpp  
struct C {  
   typedef void (C::*pFunc)();  
   pFunc funcArray[2];  
   void func1(){}  
   void func2(){}  
   C() {  
      funcArray[0] = &C::func1;  
      funcArray[1] = &C::func2;  
   }  
   void func3() {  
      (funcArray[0])();   // C2064  
      (this->*funcArray[0])(); // OK - called in this instance context  
   }  
};  
```