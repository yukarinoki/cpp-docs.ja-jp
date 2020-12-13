---
description: '詳細情報: コンパイラの警告 (レベル 1) C4561'
title: コンパイラの警告 (レベル 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: fc94879039f72bba0734240bc26d152965d6b650
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337288"
---
# <a name="compiler-warning-level-1-c4561"></a>コンパイラの警告 (レベル 1) C4561

' __fastcall ' は '/clr ' オプションと互換性がありません: ' _stdcall ' に変換しています \_

[__Fastcall](../../cpp/fastcall.md)関数呼び出し規約を[/clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラオプションと共に使用することはできません。 コンパイラは、の呼び出しを無視し **`__fastcall`** ます。 この警告を解決するには、の呼び出しを削除するか、 **`__fastcall`** **/clr** を指定せずにコンパイルします。

次の例では、C4561 が生成されます。

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```
