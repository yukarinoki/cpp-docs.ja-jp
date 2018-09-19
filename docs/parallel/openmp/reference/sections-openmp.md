---
title: セクション (OpenMP) |マイクロソフトのドキュメント
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
ms.openlocfilehash: d3b369cfbd68edd32b644c9a4ec0520329507b6e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708033"
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
  
## <a name="arguments"></a>引数

*句*<br/>
(省略可能)0 個以上の句。 サポートされている句の一覧については、「解説」を参照してください。**セクション**します。

## <a name="remarks"></a>Remarks  
 **セクション**ディレクティブは、0 個以上含めることができます**セクション**ディレクティブ。  
  
 **セクション**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 場合**並列**が指定されても、`clause`句受け入れ可能で、**並列**または**セクション**ディレクティブを除く`nowait`。  
  
 詳細については、次を参照してください。 [2.4.2 sections のコンストラクト](../../../parallel/openmp/2-4-2-sections-construct.md)します。  
  
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