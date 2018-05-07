---
title: コンパイラ エラー C3196 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3196
dev_langs:
- C++
helpviewer_keywords:
- C3196
ms.assetid: d9c38a13-191d-472d-aa2b-f61a6459d16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fdf2ccd44828993c0241a0b609da55c8eea6ca18
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3196"></a>コンパイラ エラー C3196
'keyword': 複数回使用  
  
 キーワードが複数回使用されました。  
  
 次の例では、C3196 が生成されます。  
  
```  
// C3196.cpp  
// compile with: /clr  
ref struct R abstract abstract {};   // C3196  
ref struct S abstract {};   // OK  
```