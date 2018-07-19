---
title: コンパイラの警告 (レベル 1) C4551 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4551
dev_langs:
- C++
helpviewer_keywords:
- C4551
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24ae77139e46e63946e4bb0402d3a697839d6fc8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276959"
---
# <a name="compiler-warning-level-1-c4551"></a>コンパイラの警告 (レベル 1) C4551
関数呼び出しに引数リストがありません。  
  
 関数呼び出しは、関数にパラメーターがない場合でも、関数名の後に始めと終わりかっこを含める必要があります。  
  
 次の例では、C4551 が生成されます。  
  
```  
// C4551.cpp  
// compile with: /W1  
void function1() {  
}  
  
int main() {  
   function1;   // C4551  
   function1();   // OK  
}  
```