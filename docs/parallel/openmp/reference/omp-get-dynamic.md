---
title: omp_get_dynamic |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d97cae8091f88c283412b36ef757b03c72f7580d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ompgetdynamic"></a>omp_get_dynamic
実行時以降の並列領域で使用できるスレッドの数を調整することができるかどうかを示す値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
int omp_get_dynamic();  
```  
  
## <a name="return-value"></a>戻り値  
 ゼロ以外の場合、スレッドを動的に調整が有効にします。  
  
## <a name="remarks"></a>コメント  
 スレッドの動的な調整を指定した[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)と[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)です。  
  
 詳細については、次を参照してください。 [3.1.7 omp_set_dynamic 関数](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)です。  
  
## <a name="example"></a>例  
 参照してください[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)の使用例については`omp_get_dynamic`します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)