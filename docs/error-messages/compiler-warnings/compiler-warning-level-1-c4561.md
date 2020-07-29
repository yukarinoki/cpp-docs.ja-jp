---
title: コンパイラの警告 (レベル 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: fe8ae1f8ef8180f2d3c5ba9ae2401b9447b22527
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230637"
---
# <a name="compiler-warning-level-1-c4561"></a>コンパイラの警告 (レベル 1) C4561

' __fastcall ' は '/clr ' オプションと互換性がありません: ' _stdcall ' に変換しています \_

[__Fastcall](../../cpp/fastcall.md)関数呼び出し規約を[/clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションと共に使用することはできません。 コンパイラは、の呼び出しを無視し **`__fastcall`** ます。 この警告を解決するには、の呼び出しを削除するか、 **`__fastcall`** **/clr**を指定せずにコンパイルします。

次の例では、C4561 が生成されます。

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```
