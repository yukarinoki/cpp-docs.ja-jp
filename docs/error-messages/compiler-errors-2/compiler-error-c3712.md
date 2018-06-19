---
title: コンパイラ エラー C3712 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3712
dev_langs:
- C++
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df27d74f276f70cb93a7e862e452b3a6d0eb4e55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277164"
---
# <a name="compiler-error-c3712"></a>コンパイラ エラー C3712
'method': イベント ハンドラー メソッドが 'method' には、ソースと同じ型の返す必要があります  
  
 ソース イベントのメソッドと同じ型が返されませんでしたするイベント ハンドラー メソッドを定義したとします。 このエラーを解決するには、イベント ハンドラーのメソッドに、ソース イベントのメソッドと同じ戻り値の型を指定します。  
  
 次の例では、C3712 が生成されます。  
  
```  
// C3712.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   int handler1() { return 0; }  
   // try the following line instead  
   // void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
};  
```