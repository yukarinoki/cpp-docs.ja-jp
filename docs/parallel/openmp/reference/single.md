---
title: 1 つ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Single
dev_langs:
- C++
helpviewer_keywords:
- single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ff1a255933b79d39b6eedbb9362ff76a34e0f8a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716990"
---
# <a name="single"></a>single
コードのセクションは、シングル スレッドで実行する必要があります指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>パラメーター  

`clause`  
(省略可能)0 個以上の句。 サポートされている句の一覧については、「解説」を参照してください。**単一**します。  
  
## <a name="remarks"></a>Remarks  
 **単一**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 [マスター](../../../parallel/openmp/reference/master.md)ディレクティブを使用して、コードのセクションをマスター スレッドでのみ実行するように指定できます。  
  
 詳細については、次を参照してください。 [2.4.3 の 1 つ構築](../../../parallel/openmp/2-4-3-single-construct.md)します。  
  
## <a name="example"></a>例  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
```Output  
read input  
compute results  
compute results  
write output  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)