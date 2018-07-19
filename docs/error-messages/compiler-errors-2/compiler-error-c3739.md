---
title: コンパイラ エラー C3739 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3739
dev_langs:
- C++
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 283156f436695c011642dc2603d2cc846a449b3a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264739"
---
# <a name="compiler-error-c3739"></a>コンパイラ エラー C3739
'class': event_receiver の 'layout_dependent' パラメーターが true の場合にのみ、構文がサポート  
  
 イベント インターフェイス全体をフックするしようとしましたが、`layout_dependent`で[event_receiver](../../windows/event-receiver.md)属性が true でない以外の場合は、一度に 1 つのイベントをフックする必要があります。  
  
 次の例では、C3739 が生成されます。  
  
```  
// C3739.cpp  
struct A  
{  
   __event void e();  
};  
  
// event_receiver is implied  
// [ event_receiver(layout_dependent=false)]  
  
// use the following line instead  
// [event_receiver(com, layout_dependent=true), coclass ]  
struct B  
{  
   void f();  
   B(A* a)  
   {  
      __hook(A, a, &B::f);   // C3739  
      // use the following line instead to hook a single event  
      // __hook(&A::e, a, &B::f);  
   }  
};  
  
int main()  
{  
}  
```