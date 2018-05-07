---
title: コンパイラ エラー C2041 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2041
dev_langs:
- C++
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 747dd5621aec556e89fee2ab8e7ff512736e408c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2041"></a>コンパイラ エラー C2041
指定された文字 'character' 基本 'number' の  
  
 指定した文字は、ベース (8 進数または 16 進数) などの有効な数字ではありません。  
  
 次の例では、C2041 が生成されます。  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 考えられる解決方法:  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```