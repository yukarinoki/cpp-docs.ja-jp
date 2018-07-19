---
title: コンパイラ エラー C3016 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3016
dev_langs:
- C++
helpviewer_keywords:
- C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 905cc529029fb8495f85b1ec695c49e4ba3999f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241818"
---
# <a name="compiler-error-c3016"></a>コンパイラ エラー C3016
'var': OpenMP 'for' ステートメントのインデックス変数は、符号付きの整数型を含んでいなければなりません  
  
 OpenMP `for` ステートメントのインデックス変数は、符号付きの整数型である必要があります。  
  
 次の例では C3016 が生成されます。  
  
```  
// C3016.cpp  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel  
   {  
      unsigned int i = 0;  
      // Try the following line instead:  
      // int i = 0;  
  
      #pragma omp for  
      for (i = 0; i <= 10; ++i)   // C3016  
      {  
      }  
   }  
}  
```