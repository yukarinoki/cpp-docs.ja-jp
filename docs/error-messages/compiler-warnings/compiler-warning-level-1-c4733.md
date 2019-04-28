---
title: コンパイラの警告 (レベル 1) C4733
ms.date: 11/04/2016
f1_keywords:
- C4733
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
ms.openlocfilehash: 0d0b0b912ef15294f9a4362a79dffd6d7eeabed8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221116"
---
# <a name="compiler-warning-level-1-c4733"></a>コンパイラの警告 (レベル 1) C4733

インライン asm は 'FS:0 'に割り当てる: ハンドラーは安全なハンドラーとして登録されていません

安全な例外では、ハンドラーが有効な例外ハンドラーとして登録されていない可能性がありますので、新しい例外ハンドラーを追加する FS:0 で値を変更する関数が動作しない (を参照してください[/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md))。

この警告を解決するには、いずれか fs:0 または警告をこれをオフにして[します。SAFESEH](../../assembler/masm/dot-safeseh.md)を安全な例外ハンドラーを指定します。

次の例では、C4733 が生成されます。

```
// C4733.cpp
// compile with: /W1 /c
// processor: x86
#include "stdlib.h"
#include "stdio.h"
void my_handler()
{
   printf("Hello from my_handler\n");
   exit(1);
}

int main()
{
   _asm {
      push    my_handler
      mov     eax, DWORD PTR fs:0
      push    eax
      mov     DWORD PTR fs:0, esp   // C4733
   }

   *(int*)0 = 0;
}
```