---
title: num_threads |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd57950d083c4f89ee2aa5962ad1e07a55a9a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="numthreads"></a>num_threads
スレッドのチームのスレッドの数を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
num_threads(num)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `num`  
 スレッドの数  
  
## <a name="remarks"></a>コメント  
 `num_threads`句と同じ機能には、 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)関数。  
  
 `num_threads` 次のディレクティブに適用されます。  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)です。  
  
## <a name="example"></a>例  
 参照してください[並列](../../../parallel/openmp/reference/parallel.md)の使用例については`num_threads`句。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)