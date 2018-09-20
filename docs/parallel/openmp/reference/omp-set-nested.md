---
title: omp_set_nested |Microsoft Docs
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
ms.openlocfilehash: 1d66c71bdd897471527ead5cc896471bec61193c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409221"
---
# <a name="ompsetnested"></a>omp_set_nested

入れ子になった並列処理を有効にします。

## <a name="syntax"></a>構文

```
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>パラメーター

*val*<br/>
0 以外の場合は、入れ子になった並列処理を使用できます。 0 の場合、入れ子になった並列処理を無効にします。

## <a name="remarks"></a>Remarks

入れ子になった OMP 並列処理をオンに`omp_set_nested`、かを設定して、 [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)環境変数。

設定`omp_set_nested`の設定を上書き、`OMP_NESTED`環境変数。

有効な場合、環境変数は、並行領域を入れ子にする場合にスレッドの数が指数関数的に増加するためにそれ以外の場合に運用上のプログラムを中断できます。  例 4 に設定する OMP スレッドの数を 6 回再帰的に検索が 4,096 (4 の 6 乗) を必要とする関数は一般にスレッド、スレッドの数がプロセッサの数を超えた場合、アプリケーションのパフォーマンスが低下します。 1 つの例外は、I/O バインドのアプリケーションになります。

使用[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)の現在の設定を表示する`omp_set_nested`します。

詳細については、次を参照してください。 [3.1.9 omp_set_nested 関数](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)します。

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