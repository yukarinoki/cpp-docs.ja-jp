---
title: アトミック |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- atomic
dev_langs:
- C++
helpviewer_keywords:
- atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf6287ff3c44d508a3e4293340e652edb201282f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694408"
---
# <a name="atomic"></a>アトミック
指定するアトミックに更新されるメモリの場所。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>パラメーター  
 `expression`  
 複数書き込みから保護するメモリ位置の値を含むステートメント。 有効な式のフォームの詳細については、OpenMP 仕様を参照してください。  
  
## <a name="remarks"></a>コメント  
 `atomic`ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.6.4 atomic 構築](../../../parallel/openmp/2-6-4-atomic-construct.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
```Output  
Number of threads: 10  
```  
  
## <a name="see-also"></a>関連項目  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)