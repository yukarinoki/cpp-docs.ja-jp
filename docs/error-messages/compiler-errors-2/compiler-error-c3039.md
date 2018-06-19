---
title: コンパイラ エラー C3039 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3039
dev_langs:
- C++
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bdcfa36d270dc842eec0508969c650e7b30bee4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243725"
---
# <a name="compiler-error-c3039"></a>コンパイラ エラー C3039
'var' : OpenMP 'for' ステートメントのインデックス変数を減少変数にすることはできません  
  
 インデックス変数は暗黙的にプライベートであるため、囲む [parallel](../../parallel/openmp/reference/reduction.md) ディレクティブ内の [reduction](../../parallel/openmp/reference/parallel.md) 句で、変数を使用することはできません。  
  
## <a name="example"></a>例  
 次の例では C3039 が生成されます。  
  
```  
// C3039.cpp  
// compile with: /openmp /c  
int g_i;  
  
int main() {  
   int i;  
  
   #pragma omp parallel reduction(+: i)  
   {  
      #pragma omp for  
      for (i = 0; i < 10; ++i)   // C3039  
         g_i += i;  
   }  
}  
```