---
title: OpenMP 関数 |Microsoft Docs
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP functions
- omp_destroy_lock
- omp_destroy_nest_lock
- omp_get_dynamic
- omp_get_max_threads
- omp_get_nested
- omp_get_num_procs
- omp_get_num_threads
- omp_get_thread_num
- omp_get_wtick
- omp_get_wtime
- omp_in_parallel
- omp_init_lock
- omp_init_nest_lock
- omp_set_dynamic
- omp_set_lock
- omp_set_nest_lock
- omp_set_nested
- omp_set_num_threads
- omp_test_lock
- omp_test_nest_lock
- omp_unset_lock
- omp_unset_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- OpenMP functions
- omp_destroy_lock OpenMP function
- omp_destroy_nest_lock OpenMP function
- omp_get_dynamic OpenMP function
- omp_get_max_threads OpenMP function
- omp_get_nested OpenMP function
- omp_get_num_procs OpenMP function
- omp_get_num_threads OpenMP function
- omp_get_thread_num OpenMP function
- omp_get_wtick OpenMP function
- omp_get_wtime OpenMP function
- omp_in_parallel OpenMP function
- omp_init_lock OpenMP function
- omp_init_nest_lock OpenMP function
- omp_set_dynamic OpenMP function
- omp_set_lock OpenMP function
- omp_set_nest_lock OpenMP function
- omp_set_nested OpenMP function
- omp_set_num_threads OpenMP function
- omp_test_lock OpenMP function
- omp_test_nest_lock OpenMP function
- omp_unset_lock OpenMP function
- omp_unset_nest_lock OpenMP function
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de3ea54a1526e7b340f804a21d990b6a691d0eee
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066423"
---
# <a name="openmp-functions"></a>OpenMP 関数

OpenMP API で使用される関数へのリンクを提供します。

OpenMP の標準の Visual C の実装には、次の関数が含まれています。

|関数|説明|
|--------|-----------|
|[omp_destroy_lock](#omp-destroy-lock)|ロックは初期化されません。|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|入れ子にできるロックの初期化を解除します。|
|[omp_get_dynamic](#omp-get-dynamic)|今後の並列領域で使用できるスレッドの数を実行時に調整できるかどうかを示す値を返します。|
|[omp_get_max_threads](#omp-get-max-threads)|並行領域なし場合、で利用できるスレッドの数を示す整数を返します[num_threads](openmp-clauses.md#num-threads)コードでその時点で定義されています。|
|[omp_get_nested](#omp-get-nested)|入れ子になった並列処理が有効かどうかを示す値を返します。|
|[omp_get_num_procs](#omp-get-num-procs)|関数を呼び出すときに使用できるプロセッサの数を返します。|
|[omp_get_num_threads](#omp-get-num-threads)|並列領域でスレッドの数を返します。|
|[omp_get_thread_num](#omp-get-thread-num)|そのスレッド チーム内で実行するスレッドのスレッド数を返します。|
|[omp_get_wtick](#omp-get-wtick)|プロセッサのクロックのティック間の秒数を返します。|
|[omp_get_wtime](#omp-get-wtime)|ある時点から経過した時間の秒の値を返します。|
|[omp_in_parallel](#omp-in-parallel)|並列領域内から呼び出された場合、0 以外の値を返します。|
|[omp_init_lock](#omp-init-lock)|単純なロックを初期化します。|
|[omp_init_nest_lock](#omp-init-nest-lock)|ロックを初期化します。|
|[omp_set_dynamic](#omp-set-dynamic)|今後の並列領域で使用できるスレッドの数を実行時に調整できることを示します。|
|[omp_set_lock](#omp-set-lock)|ロックが利用可能になるまで、スレッドの実行をブロックします。|
|[omp_set_nest_lock](#omp-set-nest-lock)|ロックが利用可能になるまで、スレッドの実行をブロックします。|
|[omp_set_nested](#omp-set-nested)|入れ子になった並列処理を有効にします。|
|[omp_set_num_threads](#omp-set-num-threads)|によってオーバーライドされない限り、今後の並列領域でスレッドの数を設定、 [num_threads](openmp-clauses.md#num-threads)句。|
|[omp_test_lock](#omp-test-lock)|ロックを設定しようとしていますが、スレッドの実行をブロックしません。|
|[omp_test_nest_lock](#omp-test-nest-lock)|入れ子にできるロックを設定しようとしていますが、スレッドの実行をブロックしません。|
|[omp_unset_lock](#omp-unset-lock)|ロックを解放します。|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|入れ子にできるロックを解放します。|

## <a name="omp-destroy-lock"></a>omp_destroy_lock 関数

ロックは初期化されません。

```
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_lock_t](openmp-data-types.md#omp-lock-t)で初期化された[omp_init_lock 関数](#omp-init-lock)します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_lock 関数](#omp-init-lock)の使用例については`omp_destroy_lock`します。

## <a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

入れ子にできるロックの初期化を解除します。

```
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t)で初期化された[omp_init_nest_lock](#omp-init-nest-lock)します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_nest_lock](#omp-init-nest-lock)の使用例については`omp_destroy_nest_lock`します。

## <a name="omp-get-dynamic"></a>omp_get_dynamic

今後の並列領域で使用できるスレッドの数を実行時に調整できるかどうかを示す値を返します。

```
int omp_get_dynamic();
```

### <a name="return-value"></a>戻り値

0 以外の値は、スレッドが動的に調整を意味します。

### <a name="remarks"></a>Remarks

スレッドの動的な調整を指定した[omp_set_dynamic](#omp-set-dynamic)と[OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic)します。

詳細については、次を参照してください。 [3.1.7 omp_set_dynamic 関数](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)します。

### <a name="example"></a>例

参照してください[omp_set_dynamic](#omp-set-dynamic)の使用例については`omp_get_dynamic`します。

## <a name="omp-get-max-threads"></a>omp_get_max_threads

並行領域なし場合、で利用できるスレッドの数を示す整数を返します[num_threads](openmp-clauses.md#num-threads)コードでその時点で定義されています。

```
int omp_get_max_threads( )
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.1.3 omp_get_max_threads 関数](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)します。

### <a name="example"></a>例

```
// omp_get_max_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(8);
    printf_s("%d\n", omp_get_max_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));
}
```

```Output
8
8
8
8
8
```

## <a name="omp-get-nested"></a>omp_get_nested

入れ子になった並列処理が有効かどうかを示す値を返します。

```
int omp_get_nested( );
```

### <a name="return-value"></a>戻り値

0 以外の値では、入れ子になった並列処理が有効になっていることを意味します。

### <a name="remarks"></a>Remarks

入れ子になった並列処理を指定した[omp_set_nested](#omp-set-nested)と[OMP_NESTED](openmp-environment-variables.md#omp-nested)します。

詳細については、次を参照してください。 [3.1.10 omp_get_nested 関数](../../../parallel/openmp/3-1-10-omp-get-nested-function.md)します。

### <a name="example"></a>例

参照してください[omp_set_nested](#omp-set-nested)の使用例については`omp_get_nested`します。

## <a name="omp-get-num-procs"></a>omp_get_num_procs

関数を呼び出すときに使用できるプロセッサの数を返します。

```
int omp_get_num_procs();
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.1.5 omp_get_num_procs 関数](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md)します。

### <a name="example"></a>例

```
// omp_get_num_procs.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    printf_s("%d\n", omp_get_num_procs( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_procs( ));
        }
}
```

```Output
// Expect the following output when the example is run on a two-processor machine:
2
2
```

## <a name="omp-get-num-threads"></a>omp_get_num_threads

並列領域でスレッドの数を返します。

```
int omp_get_num_threads( );
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.1.2 omp_get_num_threads 関数](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md)します。

### <a name="example"></a>例

```
// omp_get_num_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_num_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));
}
```

```Output
1
4
1
3
1
```

## <a name="omp-get-thread-num"></a>omp_get_thread_num

そのスレッド チーム内で実行するスレッドのスレッド数を返します。

```
int omp_get_thread_num( );
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.1.4 omp_get_thread_num 関数](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md)します。

### <a name="example"></a>例

参照してください[並列](openmp-directives.md#parallel)の使用例については`omp_get_thread_num`します。

## <a name="omp-get-wtick"></a>omp_get_wtick

プロセッサのクロックのティック間の秒数を返します。

```
double omp_get_wtick( );
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.3.2 omp_get_wtick 関数](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md)します。

### <a name="example"></a>例

参照してください[omp_get_wtime](#omp-get-wtime)の使用例については`omp_get_wtick`します。

## <a name="omp-get-wtime"></a>omp_get_wtime

ある時点から経過した時間の秒の値を返します。

```
double omp_get_wtime( );
```

### <a name="return-value"></a>戻り値

いくつか任意が一貫性のあるポイントからの経過時間の秒数値を返します。

### <a name="remarks"></a>Remarks

そのポイントは、今後の比較ができるようにするプログラムの実行中に一貫性のある残ります。

詳細については、次を参照してください。 [3.3.1 omp_get_wtime 関数](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)します。

### <a name="example"></a>例

```
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="omp-in-parallel"></a>omp_in_parallel

並列領域内から呼び出された場合、0 以外の値を返します。

```
int omp_in_parallel( );
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.1.6 omp_in_parallel 関数](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md)します。

### <a name="example"></a>例

```
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="omp-init-lock"></a>omp_init_lock 関数

単純なロックを初期化します。

```
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_lock_t](openmp-data-types.md#omp-lock-t)します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)します。

### <a name="example"></a>例

```
// omp_init_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t my_lock;

int main() {
   omp_init_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num( );
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_lock(&my_lock);
         printf_s("Thread %d - starting locked region\n", tid);
         printf_s("Thread %d - ending locked region\n", tid);
         omp_unset_lock(&my_lock);
      }
   }

   omp_destroy_lock(&my_lock);
}
```

```Output
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
```

## <a name="omp-init-nest-lock"></a>omp_init_nest_lock

ロックを初期化します。

```
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t)します。

### <a name="remarks"></a>Remarks

入れ子の最初の数には 0 です。

詳細については、次を参照してください。 [3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)します。

### <a name="example"></a>例

```
// omp_init_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t my_lock;

void Test() {
   int tid = omp_get_thread_num( );
   omp_set_nest_lock(&my_lock);
   printf_s("Thread %d - starting nested locked region\n", tid);
   printf_s("Thread %d - ending nested locked region\n", tid);
   omp_unset_nest_lock(&my_lock);
}

int main() {
   omp_init_nest_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_nest_lock(&my_lock);
            if (i % 3)
               Test();
            omp_unset_nest_lock(&my_lock);
        }
    }

    omp_destroy_nest_lock(&my_lock);
}
```

```Output
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
```

## <a name="omp-set-dynamic"></a>omp_set_dynamic

今後の並列領域で使用できるスレッドの数を実行時に調整できることを示します。

```
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>パラメーター

*val*<br/>
今後の並列領域で使用できるスレッドの数をランタイムに調整できるかどうかを示す値。  0 以外の場合、ランタイムは、スレッドの数を調整できます 0 の場合、ランタイムはスレッドの数を動的に調整されません。

### <a name="remarks"></a>Remarks

スレッドの数はによって設定された値を超えることはありません[omp_set_num_threads](#omp-set-num-threads)または[OMP_NUM_THREADS](openmp-environment-variables.md#omp-num-threads)します。

使用[omp_get_dynamic](#omp-get-dynamic)の現在の設定を表示する`omp_set_dynamic`します。

設定`omp_set_dynamic`の設定を上書き、 [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic)環境変数。

詳細については、次を参照してください。 [3.1.7 omp_set_dynamic 関数](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)します。

### <a name="example"></a>例

```
// omp_set_dynamic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_dynamic(9);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_dynamic( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_dynamic( ));
        }
}
```

```Output
1
1
```

## <a name="omp-set-lock"></a>omp_set_lock

ロックが利用可能になるまで、スレッドの実行をブロックします。

```
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_lock_t](openmp-data-types.md#omp-lock-t)で初期化された[omp_init_lock 関数](#omp-init-lock)します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)します。

### <a name="examples"></a>使用例

参照してください[omp_init_lock 関数](#omp-init-lock)の使用例については`omp_set_lock`します。

## <a name="omp-set-nest-lock"></a>omp_set_nest_lock

ロックが利用可能になるまで、スレッドの実行をブロックします。

```
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t)で初期化された[omp_init_nest_lock](#omp-init-nest-lock)します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)します。

### <a name="examples"></a>使用例

参照してください[omp_init_nest_lock](#omp-init-nest-lock)の使用例については`omp_set_nest_lock`します。

## <a name="omp-set-nested"></a>omp_set_nested

入れ子になった並列処理を有効にします。

```
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>パラメーター

*val*<br/>
0 以外の値は 0 が入れ子になった並列処理を無効に、入れ子になった並列処理を利用できます。

### <a name="remarks"></a>Remarks

入れ子になった OMP 並列処理をオンに`omp_set_nested`、かを設定して、 [OMP_NESTED](openmp-environment-variables.md#omp-nested)環境変数。

設定`omp_set_nested`の設定を上書き、`OMP_NESTED`環境変数。

環境変数を有効にすると、並行領域を入れ子にする場合にスレッドの数が指数関数的に増えるため、それ以外の場合に運用上のプログラムを中断できます。  たとえば、4 に設定する OMP スレッドの数を 6 回の再帰の回数を関数には、4,096 (4 の 6 乗) が必要です。 スレッド。 除く O バインドのアプリケーションとアプリケーションのパフォーマンス一般的に低下プロセッサよりも多くのスレッドがある場合。

使用[omp_get_nested](#omp-get-nested)の現在の設定を表示する`omp_set_nested`します。

詳細については、次を参照してください。 [3.1.9 omp_set_nested 関数](../../../parallel/openmp/3-1-9-omp-set-nested-function.md)します。

### <a name="example"></a>例

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

## <a name="omp-set-num-threads"></a>omp_set_num_threads

によってオーバーライドされない限り、今後の並列領域でスレッドの数を設定、 [num_threads](openmp-clauses.md#num-threads)句。

```
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>パラメーター

*num_threads*<br/>
並列領域でスレッドの数。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.1.1 omp_set_num_threads 関数](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)します。

### <a name="example"></a>例

参照してください[omp_get_num_threads](#omp-get-num-threads)の使用例については`omp_set_num_threads`します。

## <a name="omp-test-lock"></a>omp_test_lock 関数

ロックを設定しようとしていますが、スレッドの実行をブロックしません。

```
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_lock_t](openmp-data-types.md#omp-lock-t)で初期化された[omp_init_lock 関数](#omp-init-lock)します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.5 omp_test_lock 関数と omp_test_nest_lock 関数](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)します。

### <a name="example"></a>例

```
// omp_test_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t simple_lock;

int main() {
    omp_init_lock(&simple_lock);

    #pragma omp parallel num_threads(4)
    {
        int tid = omp_get_thread_num();

        while (!omp_test_lock(&simple_lock))
            printf_s("Thread %d - failed to acquire simple_lock\n",
                     tid);

        printf_s("Thread %d - acquired simple_lock\n", tid);

        printf_s("Thread %d - released simple_lock\n", tid);
        omp_unset_lock(&simple_lock);
    }

    omp_destroy_lock(&simple_lock);
}
```

```Output
Thread 1 - acquired simple_lock
Thread 1 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - acquired simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - acquired simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - released simple_lock
Thread 3 - failed to acquire simple_lock
Thread 3 - acquired simple_lock
Thread 3 - released simple_lock
```

## <a name="omp-test-nest-lock"></a>omp_test_nest_lock

入れ子にできるロックを設定しようとしていますが、スレッドの実行をブロックしません。

```
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t)で初期化された[omp_init_nest_lock](#omp-init-nest-lock)します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.5 omp_test_lock 関数と omp_test_nest_lock 関数](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)します。

### <a name="example"></a>例

```
// omp_test_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t nestable_lock;

int main() {
   omp_init_nest_lock(&nestable_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num();
      while (!omp_test_nest_lock(&nestable_lock))
         printf_s("Thread %d - failed to acquire nestable_lock\n",
                tid);

      printf_s("Thread %d - acquired nestable_lock\n", tid);

      if (omp_test_nest_lock(&nestable_lock)) {
         printf_s("Thread %d - acquired nestable_lock again\n",
                tid);
         printf_s("Thread %d - released nestable_lock\n",
                tid);
         omp_unset_nest_lock(&nestable_lock);
      }

      printf_s("Thread %d - released nestable_lock\n", tid);
      omp_unset_nest_lock(&nestable_lock);
   }

   omp_destroy_nest_lock(&nestable_lock);
}
```

```Output
Thread 1 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock again
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - acquired nestable_lock
Thread 2 - acquired nestable_lock again
Thread 2 - released nestable_lock
Thread 2 - released nestable_lock
```

## <a name="omp-unset-lock"></a>omp_unset_lock 関数

ロックを解放します。

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_lock_t](openmp-data-types.md#omp-lock-t)で初期化された[omp_init_lock 関数](#omp-init-lock)スレッドによって所有されている、および関数で実行します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_lock 関数](#omp-init-lock)の使用例については`omp_unset_lock`します。

## <a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

入れ子にできるロックを解放します。

```
void omp_unset_nest_lock( 
   omp_nest_lock_t *lock 
);
```

### <a name="parameters"></a>パラメーター

*lock*<br/>
型の変数[omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t)で初期化された[omp_init_nest_lock](#omp-init-nest-lock)スレッドによって所有されている、および関数で実行します。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。 [3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)します。

### <a name="example"></a>例

参照してください[omp_init_nest_lock](#omp-init-nest-lock)の使用例については`omp_unset_nest_lock`します。
