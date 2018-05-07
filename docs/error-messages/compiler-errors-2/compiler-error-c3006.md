---
title: コンパイラ エラー C3006 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3006
dev_langs:
- C++
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3019a4017170b13da21820931a572370db1862e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3006"></a>コンパイラ エラー C3006
'clause': OpenMP 'directive' ディレクティブ上の句には、必要な引数がありません  
  
 OpenMP ディレクティブに必要な引数がありません。  
  
 次の例では C3006 が生成されます。  
  
```  
// C3006.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel shared   // C3006  
   // Try the following line instead:  
   // #pragma omp parallel shared(x) {}  
  
}  
```