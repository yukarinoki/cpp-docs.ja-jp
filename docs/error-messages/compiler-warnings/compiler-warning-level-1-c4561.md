---
title: コンパイラの警告 (レベル 1) C4561 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4561
dev_langs:
- C++
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4862d7f570faea3e362a505e67bddaf504b32de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4561"></a>コンパイラの警告 (レベル 1) C4561
'_ _fastcall' と互換性のない、'/clr' オプション: への変換 '\__stdcall'  
  
 [_ _Fastcall](../../cpp/fastcall.md)で関数呼び出し規約は使用できません、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプション。 コンパイラへの呼び出しは無視`__fastcall`です。 この警告を解決するへの呼び出しを削除するか **_ _fastcall**なしでコンパイルまたは **/clr**です。  
  
 次の例では、C4561 が生成されます。  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```