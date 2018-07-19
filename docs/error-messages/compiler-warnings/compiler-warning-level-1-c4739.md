---
title: コンパイラの警告 (レベル 1) C4739 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4739
dev_langs:
- C++
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c90acdbc8ab32522e8e7cfac079547caaf84398d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281906"
---
# <a name="compiler-warning-level-1-c4739"></a>コンパイラの警告 (レベル 1) C4739
変数 'var' への参照はそのストレージ領域を超えています  
  
 変数に代入された値が、変数のサイズを超えています。 変数のメモリ位置を超えるメモリが書き込まれるため、データ損失が発生する可能性があります。  
  
 この警告を解決するには、その値を格納できるサイズの変数にのみ値を割り当てます。  
  
 次の例では C4739 が生成されます。  
  
```  
// C4739.cpp  
// compile with: /RTCs /Zi /W1 /c  
char *pc;  
int main() {  
   char c;  
   *(int *)&c = 1;   // C4739  
  
   // OK  
   *(char *)&c = 1;  
}  
```