---
title: コンパイラの警告 (レベル 1) C4114 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4114
dev_langs:
- C++
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78402d4487eecde00c55ea5e0aad913d97226325
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283924"
---
# <a name="compiler-warning-level-1-c4114"></a>コンパイラの警告 (レベル 1) C4114
同じ型の修飾子が 2 度以上使われています。  
  
 型修飾子を使用する型の宣言または定義 (**const**、 `volatile`、**署名**、または`unsigned`) も複数回です。 これにより、Microsoft 拡張機能 (/Ze) で警告が表示され、エラーは、ANSI 互換 (/Za) でします。  
  
 次の例では、C4114 が生成されます。  
  
```  
// C4114.cpp  
// compile with: /W1 /c  
volatile volatile int i;   // C4114  
```  
  
 次の例では、C4114 が生成されます。  
  
```  
// C4114_b.cpp  
// compile with: /W1 /c  
static const int const * ii;   // C4114  
static const int * const iii;   // OK  
```