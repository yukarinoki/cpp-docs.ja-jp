---
title: コンパイラの警告 (レベル 1) C4020 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4020
dev_langs:
- C++
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bb7926e22802178ff3cbcb710fbc9b74e7138f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274568"
---
# <a name="compiler-warning-level-1-c4020"></a>コンパイラの警告 (レベル 1) C4020
'function': 実引数が多すぎます  
  
 関数呼び出しで指定された実引数の数は、関数プロトタイプまたは定義で仮パラメーターの数を超えています。 コンパイラは、関数の呼び出し規則に従って余分な実際のパラメーターを渡します。  
  
 次の例では、C4020 が生成されます。  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 考えられる解決方法:  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```