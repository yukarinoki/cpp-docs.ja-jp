---
title: フラッシュ (OpenMP) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Flush
dev_langs:
- C++
helpviewer_keywords:
- flush OpenMP directive
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ea89d4feb7a554c2495c11aa8acaeeaa8bc775f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722060"
---
# <a name="flush-openmp"></a>flush (OpenMP)
すべてのスレッドがすべての共有オブジェクトのメモリの同じビューを持つことを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp flush [(var)]  
```  
  
## <a name="arguments"></a>引数

*var*<br/>
(省略可能)同期するオブジェクトを表す変数のコンマ区切りの一覧。 場合`var`が指定されていない、すべてのメモリをフラッシュします。  
  
## <a name="remarks"></a>Remarks  
 **フラッシュ**ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.6.5 flush ディレクティブ](../../../parallel/openmp/2-6-5-flush-directive.md)します。  
  
## <a name="example"></a>例  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
```Output  
Thread 0: read data  
Thread 1: process data  
data = 2  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)