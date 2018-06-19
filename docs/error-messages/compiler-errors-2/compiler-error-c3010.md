---
title: コンパイラ エラー C3010 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3010
dev_langs:
- C++
helpviewer_keywords:
- C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3421a7611bd7e749670c62e52526e296fd3f6c14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242060"
---
# <a name="compiler-error-c3010"></a>コンパイラ エラー C3010
'label': OpenMP 構造化ブロックからのジャンプは許可されていません  
  
 コードは、OpenMP ブロックの内部または外部にジャンプできません。  
  
 次の例では C3010 が生成されます。  
  
```  
// C3010.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel   
   {  
      #pragma omp parallel  
      {  
         goto lbl3;  
      }  
   }  
   lbl3:;   // C3010  
}  
```