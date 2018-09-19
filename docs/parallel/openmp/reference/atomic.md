---
title: アトミック |Microsoft Docs
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
ms.openlocfilehash: e7e9e9ecad2f6ea53e2f922799340eee47dd4a7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037490"
---
# <a name="atomic"></a>アトミック
指定するアトミックに更新されるメモリの場所。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>パラメーター  
*式*<br/>
複数の書き込みから保護するメモリ位置の値を含むステートメント。 有効な式のフォームの詳細については、OpenMP 仕様を参照してください。  
  
## <a name="remarks"></a>Remarks  
 `atomic`ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.6.4 atomic 構築](../../../parallel/openmp/2-6-4-atomic-construct.md)します。  
  
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