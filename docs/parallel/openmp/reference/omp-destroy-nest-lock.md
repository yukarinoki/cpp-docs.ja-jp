---
title: omp_destroy_nest_lock |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_destroy_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_destroy_nest_lock OpenMP function
ms.assetid: 0ab1352b-668f-43dd-b441-31ec4cc53e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a01ff1b0e8b37a9bd8d380b6e0e59794412e51f8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ompdestroynestlock"></a>omp_destroy_nest_lock
入れ子にできるロックの初期化を解除します。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_destroy_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `lock`  
 型の変数[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)で初期化された[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)です。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)の使用例については`omp_destroy_nest_lock`します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)