---
title: コンパイラの警告 (レベル 1) C4733 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4733
dev_langs:
- C++
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59d702867fb4950b97ee2d2c6249c26229aac975
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281932"
---
# <a name="compiler-warning-level-1-c4733"></a>コンパイラの警告 (レベル 1) C4733
インライン asm は 'FS:0' に割り当てる: ハンドラーは安全なハンドラーとして登録されていません  
  
 安全な例外では、ハンドラーが有効な例外ハンドラーとして登録されていないため、新しい例外ハンドラーを追加する FS:0 で値を変更する関数は機能しません (を参照してください[/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md))。  
  
 この警告を解決するのには、fs:0、または警告これをオフにして使用[です。SAFESEH](../../assembler/masm/dot-safeseh.md)を安全な例外ハンドラーを指定します。  
  
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