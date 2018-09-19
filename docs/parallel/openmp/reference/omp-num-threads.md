---
title: OMP_NUM_THREADS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39f45b9c81d5339b2b6afe4c77fdc9bac6b5d731
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091167"
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
によってオーバーライドされない限り、並列の領域でスレッドの最大数を設定[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)または[num_threads](../../../parallel/openmp/reference/num-threads.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
### <a name="parameters"></a>パラメーター
  
*num*<br/>
Visual C の実装では 64 まで、並列領域で必要なスレッドの最大数。  
  
## <a name="remarks"></a>Remarks  
 **OMP_NUM_THREADS**で環境変数をオーバーライドできます、 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)関数または[num_threads](../../../parallel/openmp/reference/num-threads.md)します。  
  
 既定値`num`Visual C の OpenMP 標準の実装は、ハイパー スレッド Cpu などの仮想プロセッサの数。  
  
 詳細については、次を参照してください。 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)します。  
  
## <a name="example"></a>例  
 次のコマンド セット、 **OMP_NUM_THREADS**環境変数を 16。  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 次のコマンドの現在の設定の表示、 **OMP_NUM_THREADS**環境変数。  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>関連項目  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)