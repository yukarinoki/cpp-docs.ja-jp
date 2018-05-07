---
title: コンパイラの警告 (レベル 1) C4405 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4405
dev_langs:
- C++
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9971113cc34efc5aa29e4066094517530b186839
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4405"></a>コンパイラの警告 (レベル 1) C4405
'identifier': 識別子は予約語  
  
 インライン アセンブラーの予約語は、変数名として使用されます。 予期しない結果が発生する可能性があります。 この警告を解決するには、インライン アセンブリの予約語と変数名を避けるためです。 次の例では、C4405 が生成されます。  
  
```  
// C4405.cpp  
// compile with: /W1  
// processor: x86  
void func1() {  
   int mov = 0, i = 0;  
   _asm {  
      mov mov, 0;   // C4405  
      // instead, try ..  
      // mov i, 0;  
   }  
}  
  
int main() {  
}  
```