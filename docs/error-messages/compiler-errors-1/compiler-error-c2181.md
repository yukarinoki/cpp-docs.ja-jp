---
title: コンパイラ エラー C2181 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2181
dev_langs:
- C++
helpviewer_keywords:
- C2181
ms.assetid: d52b2fe4-566a-40a9-b8e2-8dce1f287668
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f655c4807d86b5325aaab1807558750527535201
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2181"></a>コンパイラ エラー C2181
else 文が if と一致しません。  
  
 各 `else` には一致する `if`が必要です。  
  
 次の例では C2181 が生成されます。  
  
```  
// C2181.cpp  
int main() {  
   int i = 0;  
   else   // C2181  
      i = 1;  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2181b.cpp  
int main() {  
   int i = 0;  
   if(i)  
      i = 0;  
   else  
      i = 1;  
}  
```