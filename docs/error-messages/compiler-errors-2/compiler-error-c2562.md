---
title: コンパイラ エラー C2562 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2562
dev_langs:
- C++
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab3fd1a5eae008785a688bcbade674425fc8b2ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2562"></a>コンパイラ エラー C2562
'identifier': 'void' 関数の値を返す  
  
 関数として宣言されて`void`値が返されます。  
  
 このエラーは、不正な関数プロトタイプで発生することができます。  
  
 関数の宣言で戻り値の型を指定する場合、このエラーを解決する可能性があります。  
  
 次の例では、C2562 が生成されます。  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```