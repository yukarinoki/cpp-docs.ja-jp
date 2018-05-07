---
title: コンパイラの警告 (レベル 4) C4389 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4389
dev_langs:
- C++
helpviewer_keywords:
- C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44a51ad6c6cf01744a99402c4db9c7cbd8f82339
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4389"></a>コンパイラの警告 (レベル 4) C4389
'operator': signed と unsigned の数値が一致しません  
  
 操作には、符号付きと符号なしの変数が関係しています。 これは、結果、データが失われる。  
  
 次の例では、C4389 が生成されます。  
  
```  
// C4389.cpp  
// compile with: /W4  
#pragma warning(default: 4389)  
  
int main()  
{  
   int a = 9;  
   unsigned int b = 10;  
   if (a == b)   // C4389  
      return 0;  
   else  
      return 0;  
};  
```