---
title: コンパイラの警告 (レベル 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: a192fb9d8dc046bb3493b90b85371175520ccf95
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230728"
---
# <a name="compiler-warning-level-1-c4258"></a>コンパイラの警告 (レベル 1) C4258

' variable ': for ループからの定義は無視されます。外側のスコープからの定義が使用されます。

[/Ze](../../build/reference/za-ze-disable-language-extensions.md)および[/zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)では、ループの終了後[に for](../../cpp/for-statement-cpp.md)ループで定義された変数がスコープ外に出 **`for`** ます。 この警告は、ループ変数と同じ名前で、外側のループで定義されている変数が、ループを含むスコープで再び使用された場合に発生し **`for`** ます。 次に例を示します。

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
