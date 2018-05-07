---
title: コンパイラ エラー C3765 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3765
dev_langs:
- C++
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb8370a5c9c25fee211636214a82f22c05ccb311
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3765"></a>コンパイラ エラー C3765
'event': event_receiver とマークされている 'type' クラス/構造体にイベントを定義することはできません  
  
 クラスが付いている場合、 [event_receiver](../../windows/event-receiver.md)属性、クラスを含めることはできません、 [_ _event](../../cpp/event.md)宣言します。  
  
 次の例では、C3765 が生成されます。  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```