---
title: コンパイラの警告 (レベル 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: 198873792743a9ccdee94d44e2a0599348589ee6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163207"
---
# <a name="compiler-warning-level-1-c4258"></a>コンパイラの警告 (レベル 1) C4258

' variable ': for ループからの定義は無視されます。外側のスコープからの定義が使用されます。

[/Ze](../../build/reference/za-ze-disable-language-extensions.md)および[/zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)では、 **for ループの**終了[後に for ループで](../../cpp/for-statement-cpp.md)定義された変数がスコープ外に出ます。 この警告は、ループ変数と同じ名前で、外側のループで定義されている変数が**for**ループを含むスコープで再び使用された場合に発生します。 次に例を示します。

```cpp
// C4258.cpp
// compile with: /Zc:forScope /W1
int main()
{
   int i;
   {
      for (int i =0; i < 1; i++)
         ;
      i = 20;   // C4258 i (in for loop) has gone out of scope
   }
}
```
