---
title: コンパイラの警告 (レベル 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: 24a3ca8b35266e93f298314f45015b7a480e2af0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563788"
---
# <a name="compiler-warning-level-1-c4561"></a>コンパイラの警告 (レベル 1) C4561

'_ _fastcall' と互換性のない、'/clr' オプション: への変換 '\__stdcall'

[_ _Fastcall](../../cpp/fastcall.md)で関数呼び出し規約は使用できません、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプション。 コンパイラへの呼び出しは無視`__fastcall`します。 この警告を解決するへの呼び出しを削除するか **_ _fastcall**なしでコンパイルまたは **/clr**します。

次の例では、C4561 が生成されます。

```
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```