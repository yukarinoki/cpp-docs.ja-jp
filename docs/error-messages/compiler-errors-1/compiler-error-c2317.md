---
title: コンパイラ エラー C2317 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2317
dev_langs:
- C++
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82ff1155db69833cad45d9e5df4ccdf016e661e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2317"></a>コンパイラ エラー C2317
'number' 行目で始まっている 'try' ブロックには catch ハンドラーがありません  
  
 `try` ブロックには少なくとも 1 つの catch ハンドラーが必要です。  
  
 次の例では C2317 が生成されます。  
  
```  
// C2317.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "throw an exception";  
   }  
   // C2317, no catch handler  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2317b.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "throw an exception";  
   }  
   catch(char*) {}  
}  
```