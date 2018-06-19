---
title: omp_set_nested |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6539167b936efdc4c9f407cd951c9c582b0a138
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692182"
---
# <a name="ompsetnested"></a>omp_set_nested
入れ子になった並列処理を有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `val`  
 ゼロ以外の場合は、入れ子になった並列処理を使用できます。 0 の場合、入れ子になった並列処理を無効にします。  
  
## <a name="remarks"></a>コメント  
 入れ子になった OMP 並列処理をオンにすると`omp_set_nested`、かを設定して、 [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)環境変数。  
  
 設定`omp_set_nested`の設定を上書き、`OMP_NESTED`環境変数。  
  
 有効にすると、環境変数は並列領域を入れ子にする場合に、スレッドの数が指数関数的に増加するために運用それ以外の場合、プログラムを分割できます。  たとえば、OMP スレッド数が 4 に設定を 6 回再帰的に検索が 4,096 (6 のべき乗に 4) を必要とする関数の一般的にスレッド、スレッドの数がプロセッサの数を超えた場合、アプリケーションのパフォーマンスが低下します。 1 つの例外は、I/O バインドのアプリケーションになります。  
  
 使用して[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)の現在の設定を表示する`omp_set_nested`です。  
  
 詳細については、次を参照してください。 [3.1.9 omp_set_nested 関数](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>関連項目  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)