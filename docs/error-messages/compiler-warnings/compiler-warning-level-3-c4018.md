---
title: コンパイラの警告 (レベル 3) C4018 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4018
dev_langs:
- C++
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb784c8a368b5f5836deaff17d07542519ba980
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290336"
---
# <a name="compiler-warning-level-3-c4018"></a>コンパイラの警告 (レベル 3) C4018
'expression': signed と unsigned の数値が一致しません  
  
 符号付きと符号なし数値を比較すると、署名付きの値を符号なしに変換するため、コンパイラが必要です。  
  
 符号付きと符号なしの型をテストするときに 2 つの型のいずれかにキャストする場合、この警告を解決する可能性があります。  
  
 次の例では、C4018 が生成されます。  
  
```  
// C4018.cpp  
// compile with: /W3  
int main() {  
   unsigned int uc = 0;  
   int c = 0;  
   unsigned int c2 = 0;  
  
   if (uc < c) uc = 0;   // C4018  
  
   // OK  
   if (uc == c2) uc = 0;  
}  
```