---
title: セクション (OpenMP) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- section
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- sections OpenMP directive
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60bc94685a7e6128e22cc3545ae8702abe6d472e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="sections-openmp"></a>sections (OpenMP)
すべてのスレッド間で分配するコード セクションを識別します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `clause` (省略可能)  
 0 個以上の句。 サポートされている句の一覧については、「解説」セクションを参照してください**セクション**です。  
  
## <a name="remarks"></a>コメント  
 **セクション**ディレクティブは、0 個以上を含めることができます**セクション**ディレクティブです。  
  
 **セクション**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 場合**並列**も指定すると、`clause`できます句によって受け入れられる、**並列**または**のセクションでは**、ディレクティブを除く`nowait`です。  
  
 詳細については、次を参照してください。 [2.4.2 sections のコンストラクト](../../../parallel/openmp/2-4-2-sections-construct.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 0  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)