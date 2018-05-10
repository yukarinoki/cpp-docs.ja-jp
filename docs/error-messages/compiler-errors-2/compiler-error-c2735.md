---
title: コンパイラ エラー C2735 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2735
dev_langs:
- C++
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ab970aa4e46ed0206f311e100f7ee777907aff8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2735"></a>コンパイラ エラー C2735
'keyword' キーワードは、仮パラメーターの型指定子では使用できません。  
  
 このコンテキストで、キーワードが正しくありません。  
  
 次の例では、C2735 が生成されます。  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```