---
title: 並列 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- parallel
dev_langs:
- C++
helpviewer_keywords:
- parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e0436dbbc75690d38b5930a491b7058ee095341
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692286"
---
# <a name="parallel"></a>parallel
同時に複数のスレッドで実行されるコードである並列領域を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `clause` (省略可能)  
 0 個以上の句。  サポートされている句の一覧については、「解説」セクションを参照してください**並列**です。  
  
## <a name="remarks"></a>コメント  
 **並列**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [shared](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **並列**でも使用できます、[セクション](../../../parallel/openmp/reference/sections-openmp.md)と[の](../../../parallel/openmp/reference/for-openmp.md)ディレクティブです。  
  
 詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)です。  
  
## <a name="example"></a>例  
 次の例では、スレッドの数を設定し、並行領域を定義する方法を示します。 既定では、スレッドの数は、コンピューター上の論理プロセッサの数と同じです。 たとえば、ハイパースレッディングが有効になっている 1 つの物理プロセッサを搭載したマシンがある場合は、2 つの論理プロセッサと 2 つのスレッドがあります。  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 1  
Hello from thread 2  
Hello from thread 3  
```  
  
## <a name="comment"></a>コメント  
 出力の順序は、別のコンピューターで異なることに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)