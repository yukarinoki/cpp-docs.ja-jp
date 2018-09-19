---
title: omp_set_num_threads |Microsoft Docs
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
ms.openlocfilehash: 849bdade5c6abfad07ebed262fb367487d3e1415
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047890"
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
によってオーバーライドされない限り、後続の並列領域でスレッドの数を設定、 [num_threads](../../../parallel/openmp/reference/num-threads.md)句。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
### <a name="parameters"></a>パラメーター
  
*num_threads*<br/>
並列領域でスレッドの数。  
  
## <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。 [3.1.1 omp_set_num_threads 関数](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)します。  
  
## <a name="example"></a>例  
 参照してください[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)の使用例については`omp_set_num_threads`します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)