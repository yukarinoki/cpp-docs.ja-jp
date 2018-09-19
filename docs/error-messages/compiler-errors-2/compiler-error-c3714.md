---
title: コンパイラ エラー C3714 |Microsoft Docs
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
ms.openlocfilehash: 7102378acc2fe12335f1f2b3579f93cf02161b16
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109653"
---
# <a name="compiler-error-c3714"></a>コンパイラ エラー C3714

'method': イベント ハンドラー メソッドが必要と同じ呼び出し規約、ソースとして 'method'

ソース イベントのメソッドとして同じ呼び出し規約を使用していないイベント ハンドラー メソッドを定義しました。 このエラーを解決するには、イベント ハンドラー メソッドのソース イベントのメソッドとして同じ呼び出し規約を付けます。 たとえば、次のコードの呼び出し規約、`handler1`と`event1`一致 ([_ _cdecl](../../cpp/cdecl.md)または[_ _stdcall](../../cpp/stdcall.md)または他のユーザー)。 削除する規約キーワードを両方の宣言から呼び出すことも、問題を解決され原因`event1`と`handler1`の既定値が、 [thiscall](../../cpp/thiscall.md)呼び出し規約。 参照してください[呼び出し規則](../../cpp/calling-conventions.md)詳細についてはします。

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