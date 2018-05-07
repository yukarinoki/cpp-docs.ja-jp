---
title: コンパイラ エラー C3731 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3731
dev_langs:
- C++
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7b87b59fa7a3e3695da88b5ddb30a84837f6e60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3731"></a>コンパイラ エラー C3731
互換性のないイベント 'function1' とハンドラー 'function2';イベント ソースとイベント ハンドラーが同じ型にする必要があります。  
  
 イベント ソースとイベント レシーバーは、同じ型を持つ必要があります (たとえば`native`と`com`型)。 このエラーを解決するには、イベント ソースとイベント ハンドラーの一致の種類を作成します。  
  
 次の例では、C3731 が生成されます。  
  
```  
// C3731.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
[event_source(native)]  
struct A {  
   __event void MyEvent();  
};  
  
[event_receiver(managed)]  
// try the following line instead  
// [event_receiver(native)]  
struct B {  
   void func();  
   B(A a) {  
      __hook(&A::MyEvent, &a, &B::func);   // C3731  
   }  
};  
  
int main() {  
}  
```