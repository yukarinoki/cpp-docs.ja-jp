---
title: コンパイラ エラー C3713 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3713
dev_langs:
- C++
helpviewer_keywords:
- C3713
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0e919add44075516deedfb339c8e1d7487f6ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3713"></a>コンパイラ エラー C3713
'method': イベント ハンドラー メソッド パラメーターが必要、同じ関数、ソースとして 'method'  
  
 ソース イベントのメソッドと同じパラメーターを使用していないイベント ハンドラー メソッドを定義したとします。 このエラーを解決するには、イベント ハンドラー メソッドのソース イベントのメソッドと同じパラメーターを提供します。  
  
 次の例では、C3713 が生成されます。  
  
```  
// C3713.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1(int nValue);  
   // try the following line instead  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713  
   }  
};  
```