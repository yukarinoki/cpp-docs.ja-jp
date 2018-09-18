---
title: omp_set_lock |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_lock OpenMP function
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 390090b0f4bf5f8795373db9f61f8365257ee95b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024912"
---
# <a name="ompsetlock"></a>omp_set_lock
ロックが利用可能になるまで、スレッドの実行をブロックします。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_set_lock(  
   omp_lock_t *lock  
);  
```  
  
### <a name="parameters"></a>パラメーター
  
*lock*<br/>
型の変数[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)で初期化された[omp_init_lock 関数](../../../parallel/openmp/reference/omp-init-lock.md)します。  
  
## <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)します。  
  
## <a name="examples"></a>使用例  
 参照してください[omp_init_lock 関数](../../../parallel/openmp/reference/omp-init-lock.md)の使用例については`omp_set_lock`します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)