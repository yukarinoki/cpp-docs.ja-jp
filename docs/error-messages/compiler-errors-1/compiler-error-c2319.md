---
title: コンパイラ エラー C2319 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2319
dev_langs:
- C++
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fa9d2c0aeae56ea678a9f2aa2cbfabfc43e71c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222395"
---
# <a name="compiler-error-c2319"></a>コンパイラ エラー C2319
'try/catch' の後に複合ステートメントを指定する必要があります。 '{' が必要です  
  
 `try` または `catch` ステートメントの後に `try` または `catch` ブロックが見つかりません。 ブロックは中かっこで囲む必要があります。  
  
 次の例では C2319 が生成されます。  
  
```  
// C2319.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( C ) ;    // C2319  
   // try the following line instead  
   // catch( C ) {}  
}  
```