---
title: コンパイラ エラー C3714 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3714
dev_langs:
- C++
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0046463b7354d0b764e29701bddb117496858e14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3714"></a>コンパイラ エラー C3714
'method': イベント ハンドラー メソッドがあります、同じ呼び出し規約、ソースとして 'method'  
  
 ソース イベントのメソッドとして同じ呼び出し規約を使用していないイベント ハンドラー メソッドを定義したとします。 このエラーを解決するには、イベント ハンドラー メソッドのソース イベントのメソッドと同じ呼び出し規約を提供します。 たとえば、次のコードでの呼び出し規約は、`handler1`と`event1`一致 ([_ _cdecl](../../cpp/cdecl.md)または[_ _stdcall](../../cpp/stdcall.md)または他のユーザー)。 削除する両方の宣言から規約キーワードを呼び出すことがも、問題の解決し、なる`event1`と`handler1`に既定値に、 [thiscall](../../cpp/thiscall.md)呼び出し規約です。 参照してください[呼び出し規約](../../cpp/calling-conventions.md)詳細についてはします。  
  
 次の例では、C3714 が生成されます。  
  
```  
// C3714.cpp  
// compile with: /c  
// processor: x86  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void __cdecl event1();  
   // try the following line instead  
   // __event void __stdcall event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void __stdcall handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714  
   }  
};  
```