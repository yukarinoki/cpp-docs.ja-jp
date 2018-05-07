---
title: コンパイラ エラー C2325 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2325
dev_langs:
- C++
helpviewer_keywords:
- C2325
ms.assetid: e6b0a186-3f2a-4adf-beae-fadd75492bf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095959dd432de52c2a0d32cbd7198ea434223407
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2325"></a>コンパイラ エラー C2325
'type': 'name' の右側に予期しない型  
  
 不適切な型のデストラクター、呼び出しが行われました。  
  
 次の例では、C2325 が生成されます。  
  
```  
// C2325.cpp  
// compile with: /c  
class A {};  
typedef A* pA_t;  
void f() {  
    A** ppa = new A *;  
    ppa->~A*;   // C2325  
  
   pA_t *ppa2 = new pA_t;  
   ppa2->~pA_t();   // OK  
}  
```