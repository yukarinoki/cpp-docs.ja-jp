---
title: omp_set_num_threads |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_num_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 335cb283026a019d6c6a03565c5dbec541140db3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
オーバーライドされない限り、後続の並列領域で、スレッドの数を設定、 [num_threads](../../../parallel/openmp/reference/num-threads.md)句。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `num_threads`  
 並行領域内のスレッドの数。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.1.1 omp_set_num_threads 関数](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)の使用例については`omp_set_num_threads`します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)