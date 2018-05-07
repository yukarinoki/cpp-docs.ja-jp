---
title: コンパイラ エラー C2318 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2318
dev_langs:
- C++
helpviewer_keywords:
- C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d20c3dfe8122b8795238d09ab2b376dcd91d437
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2318"></a>コンパイラ エラー C2318
この catch ハンドラーと関連付けられた try ブロックはありません。  
  
 `catch` ハンドラーが定義されていますが、その前に `try` ブロックがありません。  
  
 次の例では C2318 が生成されます。  
  
```  
// C2318.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   // no try block  
   catch( int ) {}   // C2318  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2318b.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try{}  
   catch( int ) {}  
}  
```