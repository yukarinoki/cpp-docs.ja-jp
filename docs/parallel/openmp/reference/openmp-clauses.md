---
title: OpenMP 句
ms.date: 03/20/2019
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
ms.openlocfilehash: 1c4c7961a173eb47394d03e9aabdd14574e62b08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363891"
---
# <a name="openmp-clauses"></a>OpenMP 句

OpenMP API で使用される句へのリンクを提供します。

Visual C++ では、次の OpenMP 句がサポートされています。

一般属性の場合:

|句|説明|
|------|-----------|
|[if](#if-openmp)|ループを並列で実行するか、シリアルで実行するかを指定します。|
|[num_threads](#num-threads)|スレッド チームのスレッド数を設定します。|
|[注文](#ordered-openmp-clauses)|[順序付き](openmp-directives.md#ordered-openmp-directives)ディレクティブをループで使用する場合は、並列[for](openmp-directives.md#for-openmp)ステートメントで必要です。|
|[スケジュール](#schedule)|[ディレクティブ](openmp-directives.md#for-openmp)に適用されます。|
|[Nowait](#nowait)|ディレクティブ内のバリアをオーバーライドします。|

データ共用属性の場合:

|句|説明|
|------|-----------|
|[プライベート](#private-openmp)|各スレッドが変数の独自のインスタンスを持つ必要があることを指定します。|
|[firstprivate](#firstprivate)|各スレッドが変数の独自のインスタンスを持つ必要があり、変数が並列構成の前に存在するため、変数を変数の値で初期化する必要があることを指定します。|
|[lastprivate](#lastprivate)|外側のコンテキストの変数のバージョンが、最後の反復 (for-loop コンストラクト) または最後のセクション (#pragma セクション) を実行するスレッドのプライベート バージョンと等しく設定されることを指定します。|
|[共有](#shared-openmp)|1 つ以上の変数をすべてのスレッドで共有することを指定します。|
|[default](#default-openmp)|並列領域でのスコープなしの変数の動作を指定します。|
|[reduction](#reduction)|各スレッドに対してプライベートな 1 つ以上の変数が、並列領域の最後にある縮小演算の対象であることを指定します。|
|[copyin](#copyin)|スレッドがスレッド[プライベート](openmp-directives.md#threadprivate)変数のマスタースレッドの値にアクセスできるようにします。|
|[copyprivate](#copyprivate)|1 つ以上の変数をすべてのスレッドで共有することを指定します。|

## <a name="copyin"></a><a name="copyin"></a>コピーイン

スレッドがスレッド[プライベート](openmp-directives.md#threadprivate)変数のマスタースレッドの値にアクセスできるようにします。

```cpp
copyin(var)
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
並列`threadprivate`構成の前に存在する、マスター スレッド内の変数の値で初期化される変数。

### <a name="remarks"></a>解説

`copyin`は、次のディレクティブに適用されます。

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)

詳細については、 [2.7.2.7 コピーを](../../../parallel/openmp/2-7-2-7-copyin.md)参照してください。

### <a name="example"></a>例

の使用例については[、スレッドプライベート](openmp-directives.md#threadprivate)を参照`copyin`してください。

## <a name="copyprivate"></a><a name="copyprivate"></a>Copyprivate

1 つ以上の変数をすべてのスレッドで共有することを指定します。

```cpp
copyprivate(var)
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
共有する 1 つ以上の変数。 複数の変数を指定する場合は、変数名をコンマで区切ります。

### <a name="remarks"></a>解説

`copyprivate`[は、単一](openmp-directives.md#single)のディレクティブに適用されます。

詳細については、 [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md)を参照してください。

### <a name="example"></a>例

```cpp
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default"></a><a name="default-openmp"></a>既定

並列領域でのスコープなしの変数の動作を指定します。

```cpp
default(shared | none)
```

### <a name="remarks"></a>解説

`shared``default`句が指定されていない場合に有効な場合は、並列領域内の変数は[shared](#shared-openmp)句で指定されたかのように扱われます。 `none`は、プライベート 、 [shared](#shared-openmp)、 [、 reduction](#reduction)、 [firstprivate](#private-openmp)、 または[firstprivate](#firstprivate)[lastprivate](#lastprivate)句でスコープが設定されていない並列領域で使用される変数がコンパイラ エラーを引き起こすことを意味します。

`default`は、次のディレクティブに適用されます。

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)

詳細については[、2.7.2.5 のデフォルト](../../../parallel/openmp/2-7-2-5-default.md)を参照してください。

### <a name="example"></a>例

の使用例については[、private](#private-openmp)を`default`参照してください。

## <a name="firstprivate"></a><a name="firstprivate"></a>最初のプライベート

各スレッドが変数の独自のインスタンスを持つ必要があり、変数が並列構成の前に存在するため、変数を変数の値で初期化する必要があることを指定します。

```cpp
firstprivate(var)
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
各スレッドにインスタンスを持ち、並列構成の前に存在するため、変数の値で初期化される変数。 複数の変数を指定する場合は、変数名をコンマで区切ります。

### <a name="remarks"></a>解説

`firstprivate`は、次のディレクティブに適用されます。

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [セクション](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

詳細については、 [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md)を参照してください。

### <a name="example"></a>例

の使用例`firstprivate`については、 [private](#private-openmp)の例を参照してください。

## <a name="if-openmp"></a><a name="if-openmp"></a>if (オープンMP)

ループを並列で実行するか、シリアルで実行するかを指定します。

```cpp
if(expression)
```

### <a name="parameters"></a>パラメーター

*式*<br/>
true (ゼロ以外) と評価された場合に、並列領域のコードを並列実行する整数式。 式が false (ゼロ) に評価されると、並列領域はシリアル (単一のスレッド) で実行されます。

### <a name="remarks"></a>解説

`if`は、次のディレクティブに適用されます。

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)

詳細については、 [2.3 並列構造](../../../parallel/openmp/2-3-parallel-construct.md)を参照してください。

### <a name="example"></a>例

```cpp
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a><a name="lastprivate"></a>ラストプライベート

外側のコンテキストの変数のバージョンが、最後の反復 (for-loop コンストラクト) または最後のセクション (#pragma セクション) を実行するスレッドのプライベート バージョンと等しく設定されることを指定します。

```cpp
lastprivate(var)
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
最後の反復 (for-loop コンストラクト) または最後のセクション (#pragma セクション) を実行するスレッドのプライベート バージョンと等しく設定されている変数。

### <a name="remarks"></a>解説

`lastprivate`は、次のディレクティブに適用されます。

- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)

詳細については、 [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md)を参照してください。

### <a name="example"></a>例

句の使用例`lastprivate`については[、スケジュール](#schedule)を参照してください。

## <a name="nowait"></a><a name="nowait"></a>Nowait

ディレクティブ内のバリアをオーバーライドします。

```cpp
nowait
```

### <a name="remarks"></a>解説

`nowait`は、次のディレクティブに適用されます。

- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

詳細については、 [2.4.1 の構成要素](../../../parallel/openmp/2-4-1-for-construct.md)[、2.4.2 セクションの構成要素](../../../parallel/openmp/2-4-2-sections-construct.md)、および[2.4.3 単一構造](../../../parallel/openmp/2-4-3-single-construct.md)を参照してください。

### <a name="example"></a>例

```cpp
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num_threads"></a><a name="num-threads"></a>num_threads

スレッド チームのスレッド数を設定します。

```cpp
num_threads(num)
```

### <a name="parameters"></a>パラメーター

*num*<br/>
スレッドの数

### <a name="remarks"></a>解説

この`num_threads`句は[、omp_set_num_threads](openmp-functions.md#omp-set-num-threads)関数と同じ機能を持ちます。

`num_threads`は、次のディレクティブに適用されます。

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)

詳細については、 [2.3 並列構造](../../../parallel/openmp/2-3-parallel-construct.md)を参照してください。

### <a name="example"></a>例

句の使用例`num_threads`については[、並列](openmp-directives.md#parallel)を参照してください。

## <a name="ordered"></a><a name="ordered-openmp-clauses"></a>注文

[順序付き](openmp-directives.md#ordered-openmp-directives)ディレクティブをループで使用する場合は、並列[for](openmp-directives.md#for-openmp)ステートメントで必要です。

```cpp
ordered
```

### <a name="remarks"></a>解説

`ordered`は[、for](openmp-directives.md#for-openmp)ディレクティブに適用されます。

詳細については、 [2.4.1 の構築を参照](../../../parallel/openmp/2-4-1-for-construct.md)してください。

### <a name="example"></a>例

句[ordered](openmp-directives.md#ordered-openmp-directives)の使用例`ordered`については、順序付けを参照してください。

## <a name="private"></a><a name="private-openmp"></a>プライベート

各スレッドが変数の独自のインスタンスを持つ必要があることを指定します。

```cpp
private(var)
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
各スレッドにインスタンスを持つ変数。

### <a name="remarks"></a>解説

`private`は、次のディレクティブに適用されます。

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [セクション](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

詳細については、 [2.7.2.1 プライベート](../../../parallel/openmp/2-7-2-1-private.md)を参照してください。

### <a name="example"></a>例

```c
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a><a name="reduction"></a>削減

各スレッドに対してプライベートな 1 つ以上の変数が、並列領域の最後にある縮小演算の対象であることを指定します。

```cpp
reduction(operation:var)
```

### <a name="parameters"></a>パラメーター

*操作*<br/>
並列領域の最後にある変数*var*に対して実行する操作の演算子。

*Var*<br/>
スカラー縮小を行う 1 つ以上の変数。 複数の変数を指定する場合は、変数名をコンマで区切ります。

### <a name="remarks"></a>解説

`reduction`は、次のディレクティブに適用されます。

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)

詳細については[、2.7.2.6 の縮小](../../../parallel/openmp/2-7-2-6-reduction.md)を参照してください。

### <a name="example"></a>例

```cpp
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a><a name="schedule"></a>スケジュール

[ディレクティブ](openmp-directives.md#for-openmp)に適用されます。

```cpp
schedule(type[,size])
```

### <a name="parameters"></a>パラメーター

*type*<br/>
スケジュールの種類 ( `dynamic`、 `guided` `runtime`、 `static`、 、 、 、 のいずれか ) 。

*サイズ*<br/>
(オプション)反復のサイズを指定します。 *size*は整数でなければなりません。 *型*が の場合`runtime`は無効です。

### <a name="remarks"></a>解説

詳細については、 [2.4.1 の構築を参照](../../../parallel/openmp/2-4-1-for-construct.md)してください。

### <a name="example"></a>例

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------
```

## <a name="shared"></a><a name="shared-openmp"></a>共有

1 つ以上の変数をすべてのスレッドで共有することを指定します。

```cpp
shared(var)
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
共有する 1 つ以上の変数。 複数の変数を指定する場合は、変数名をコンマで区切ります。

### <a name="remarks"></a>解説

スレッド間で変数を共有するもう 1 つの方法は[、copyprivate](#copyprivate)句を使用することです。

`shared`は、次のディレクティブに適用されます。

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [セクション](openmp-directives.md#sections-openmp)

詳細については[、2.7.2.4 共有](../../../parallel/openmp/2-7-2-4-shared.md)を参照してください。

### <a name="example"></a>例

の使用例については[、private](#private-openmp)を`shared`参照してください。
