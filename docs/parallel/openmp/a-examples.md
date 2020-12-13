---
description: '詳細情報: A. 例'
title: A. 例
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: d52b59f9f83cf791c03fb49ca726273a2c977e58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342544"
---
# <a name="a-examples"></a>A. 例

このドキュメントで定義されているコンストラクトの例を次に示します。 ディレクティブの後に続くステートメントは、必要な場合にのみ複合で、複合でないステートメントは、その前のディレクティブからインデントされます。

## <a name="a1-a-simple-loop-in-parallel"></a>..1 単純なループを並列処理する

次の例では、 [parallel for](2-directives.md#251-parallel-for-construct) ディレクティブを使用してループを並列化する方法を示します。 ループ反復変数は既定ではプライベートであるため、プライベート句で明示的に指定する必要はありません。

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>1. 2 条件付きコンパイル

次の例は、OpenMP マクロ [_OPENMP](2-directives.md#22-conditional-compilation)を使用した条件付きコンパイルの使用方法を示しています。 OpenMP コンパイルでは、 `_OPENMP` マクロが定義されます。

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

定義されたプリプロセッサ演算子を使用すると、1つのディレクティブで複数のマクロをテストできます。

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>A. 3 個の並列領域

[Parallel](2-directives.md#23-parallel-construct)ディレクティブは、粒度の粗い並列プログラムで使用できます。 次の例では、並列領域の各スレッドが、 `x` スレッド番号に基づいて、使用するグローバル配列のどの部分を決定するかを決定します。

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>4. nowait 句

並列領域内に多数の独立したループがある場合は、次のように [nowait](2-directives.md#241-for-construct) 句を使用して、ディレクティブの最後に暗黙的なバリアを回避でき `for` ます。

```cpp
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```

## <a name="a5-the-critical-directive"></a>. 5. critical ディレクティブ

次の例には、いくつかの [重要な](2-directives.md#262-critical-construct) ディレクティブが含まれています。 この例は、タスクをデキューして作業するキューモデルを示しています。 同じタスクをデキューする多くのスレッドに対して保護するには、デキュー操作がセクション内に存在する必要があり `critical` ます。 この例の2つのキューは独立しているため、 `critical` *xaxis* と *y 軸数値* の異なる名前を持つディレクティブによって保護されています。

```cpp
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```

## <a name="a6-the-lastprivate-clause"></a>. 6 a.6 lastprivate 句

正しい実行は、ループの最後のイテレーションが変数に代入した値によって異なる場合があります。 このようなプログラムでは、変数の値がループが順番に実行される場合と同じになるように、 [a.6 lastprivate](2-directives.md#2723-lastprivate) 句の引数としてすべての変数を列挙する必要があります。

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

前の例で `i` は、並列領域の最後にあるの値は、シーケンシャルな場合と同じになり `n-1` ます。

## <a name="a7-the-reduction-clause"></a>. 7 リダクション句

次の例は、 [リダクション](2-directives.md#2726-reduction) 句を示しています。

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>8つの並列セクション

次の例 ( [セクション 2.4.2](2-directives.md#242-sections-construct)) では、関数 *xaxis*、 *y 軸数値*、および *zaxis* を同時に実行できます。 最初の `section` ディレクティブは省略可能です。  すべて `section` のディレクティブは、構造体の構文の範囲内に出現する必要があり `parallel sections` ます。

```cpp
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```

## <a name="a9-single-directives"></a>. 9 の単一ディレクティブ

次の例は、 [単一](2-directives.md#243-single-construct) のディレクティブを示しています。 この例では、1つのスレッド (通常、ディレクティブが発生した最初のスレッド) のみが `single` 進行状況メッセージを出力します。 ユーザーは、どのスレッドがセクションを実行するかを判断する必要はありません `single` 。 他のすべてのスレッドは、セクションをスキップ `single` し、コンストラクトの最後のバリアで停止し `single` ます。 セクションを実行するスレッドを待たずに他のスレッドを続行できる場合は、 `single` `nowait` ディレクティブで句を指定でき `single` ます。

```cpp
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```

## <a name="a10-sequential-ordering"></a>10順次順序

[順序](2-directives.md#266-ordered-construct) 指定されたセクションは、並列で実行される作業からの出力を順番に並べ替える場合に便利です。 次のプログラムでは、順番にインデックスを出力します。

```cpp
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```

## <a name="a11-a-fixed-number-of-threads"></a>. 11 固定数のスレッド

プログラムによっては、事前の固定された数のスレッドを使用して正常に実行される場合があります。  スレッド数の動的調整の既定の設定は実装によって定義されるため、このようなプログラムでは、動的スレッド機能を無効にして、移植性を維持するためにスレッド数を明示的に設定できます。 次の例では、 [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)、 [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function)を使用してこれを行う方法を示します。

```cpp
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

この例では、プログラムは16個のスレッドによって実行される場合にのみ、正しく実行されます。 実装で16個のスレッドをサポートできない場合、この例の動作は実装定義になります。

並列領域を実行するスレッドの数は、動的スレッドの設定に関係なく、並列領域の間は一定のままです。 動的スレッド機構は、並列領域の開始時に使用するスレッドの数を決定し、その領域の存続期間中は定数を保持します。

## <a name="a12-the-atomic-directive"></a>. 12 atomic ディレクティブ

次の例では、 [atomic](2-directives.md#264-atomic-construct)ディレクティブを使用して、競合状態 ( *x* の要素の同時更新) を回避しています。

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

`atomic`この例でディレクティブを使用する利点は、x の2つの異なる要素の更新を並行して実行できることです。 代わりに、 [critical](2-directives.md#262-critical-construct) ディレクティブを使用すると、 *x* の要素に対するすべての更新が直列に実行されます (ただし、保証された順序ではありません)。

ディレクティブは、 `atomic` その直後の C または C++ ステートメントにのみ適用されます。  その結果、この例では、 *y* の要素はアトミックに更新されません。

## <a name="a13-a-flush-directive-with-a-list"></a>. 13. リストを含むフラッシュディレクティブ

次の例では、ディレクティブを使用して、 `flush` スレッドのペア間で特定のオブジェクトをポイントツーポイントで同期します。

```cpp
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```

## <a name="a14-a-flush-directive-without-a-list"></a>. 14. リストを含まないフラッシュディレクティブ

次の例 ( [セクション 2.6.5](2-directives.md#265-flush-directive)) では、ディレクティブによって影響を受ける共有オブジェクトが、 `flush` 影響を受けていない共有オブジェクトのリストと区別されます。

```cpp
// omp_flush_without_list.c
#include <omp.h>

int x, *p = &x;

void f1(int *q)
{
    *q = 1;
    #pragma omp flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

void f2(int *q)
{
    #pragma omp barrier
    *q = 2;

    #pragma omp barrier
    // a barrier implies a flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

int g(int n)
{
    int i = 1, j, sum = 0;
    *p = 1;

    #pragma omp parallel reduction(+: sum) num_threads(10)
    {
        f1(&j);
        // i, n and sum were not flushed
        //   because they were not accessible in f1
        // j was flushed because it was accessible
        sum += j;
        f2(&j);
        // i, n, and sum were not flushed
        //   because they were not accessible in f2
        // j was flushed because it was accessible
        sum += i + j + *p + n;
    }
    return sum;
}

int main()
{
}
```

## <a name="a15-the-number-of-threads-used"></a>. 15 使用されるスレッドの数

次の不適切な例について考えてみます ( [セクション 3.1.2](3-run-time-library-functions.md#312-omp_get_num_threads-function))。

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

この呼び出しでは、 `omp_get_num_threads()` コードのシリアルセクションで1が返されます。そのため、前の例では、 *np* は常に1になります。 並列領域にデプロイされるスレッドの数を決定するには、その呼び出しが並列領域内に存在する必要があります。

次の例は、スレッド数のクエリを含めずに、このプログラムを書き直す方法を示しています。

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>16個のロック

次の例 ( [セクション 3.2](3-run-time-library-functions.md#32-lock-functions)) では、ロック関数の引数は型である必要があり、 `omp_lock_t` フラッシュする必要はありません。  ロック関数を使用すると、最初の重要なセクションへのエントリを待機している間にスレッドがアイドル状態になりますが、2番目のエントリを待機している間は他の作業を行います。  `omp_set_lock`関数はブロックしますが、関数はを使用せず `omp_test_lock` 、の作業 `skip()` を実行できます。

```cpp
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```

## <a name="a17-nestable-locks"></a>. 17 個の A.17 ロック

次の例 ( [セクション 3.2](3-run-time-library-functions.md#32-lock-functions)) では、a.17 ロックを使用して、構造全体とそのメンバーのいずれかに更新を同期する方法を示しています。

```cpp
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```

## <a name="a18-nested-for-directives"></a>. 18 の入れ子になった for ディレクティブ

次のディレクティブの入れ子の例は、 `for` [](2-directives.md#29-directive-nesting)内部ディレクティブと外部 `for` ディレクティブが異なる並列領域にバインドされているために準拠しています。

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

前の例の次のバリエーションも準拠しています。

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>作業共有ディレクティブの不適切な入れ子を示す、19個の例

このセクションの例では、 [ディレクティブの入れ子](2-directives.md#29-directive-nesting) 規則について説明します。

次の例は、内部ディレクティブと外部 `for` ディレクティブが入れ子になっていて、同じディレクティブにバインドされているため、準拠していません `parallel` 。

```cpp
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

上記の例の動的に入れ子にされた次のバージョンも非準拠になります。

```cpp
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

次の例は、 `for` `single` ディレクティブとディレクティブが入れ子になっており、同じ並列領域にバインドされているため、非準拠です。

```cpp
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

次の例は `barrier` 、内のディレクティブに `for` よってデッドロックが発生する可能性があるため、準拠していません。

```cpp
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

次の例は、 `barrier` 一度に1つのスレッドのみがクリティカルセクションに入ることができるため、デッドロックが発生するため、準拠していません。

```cpp
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

次の例は、 `barrier` 1 つのスレッドのみがセクションを実行するという点でデッドロックが発生するため、準拠していません `single` 。

```cpp
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```

## <a name="a20-bind-barrier-directives"></a>. 20 バインドバリアディレクティブ

ディレクティブバインド規則は、ディレクティブを呼び出して、 `barrier` 最も近い外側のディレクティブにバインドし `parallel` ます。 ディレクティブバインドの詳細については、 [セクション 2.8](2-directives.md#28-directive-binding)を参照してください。

次の例では、 *main* から *sub2* への呼び出しが準拠しています。これは、 `barrier` ( *sub3* の) が *sub2* の並行領域にバインドされるためです。 *Main* から *sub1* への呼び出しは、が `barrier` サブルーチンの parallel 領域にバインドするため、準拠しています。 *sub2*  が並列領域にバインドされず、無視されるため、 *main* から *sub3* への呼び出しは準拠し `barrier` ています。 また、によって同期されるのは、 `barrier` *sub1* で作成されたすべてのスレッドではなく、外側の並列領域内のスレッドのチームだけです。

```cpp
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```

## <a name="a21-scope-variables-with-the-private-clause"></a>. 21 スコープ変数と private 句

次の例のとの値 `i` `j` は、並行領域からの終了時には定義されていません。

```cpp
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

句の詳細につい `private` ては、「 [2.7.2.1」セクション](2-directives.md#2721-private)を参照してください。

## <a name="a22-the-defaultnone-clause"></a>. 22 既定 (none) 句

次の例では、句によって影響を受ける変数を、では `default(none)` ない変数から区別します。

```cpp
// openmp_using_clausedefault.c
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int x, y, z[1000];
#pragma omp threadprivate(x)

void fun(int a) {
   const int c = 1;
   int i = 0;

   #pragma omp parallel default(none) private(a) shared(z)
   {
      int j = omp_get_num_thread();
             //O.K.  - j is declared within parallel region
      a = z[j];       // O.K.  - a is listed in private clause
                      //      - z is listed in shared clause
      x = c;          // O.K.  - x is threadprivate
                      //      - c has const-qualified type
      z[i] = y;       // C3052 error - cannot reference i or y here

      #pragma omp for firstprivate(y)
         for (i=0; i<10 ; i++) {
            z[i] = y;  // O.K. - i is the loop control variable
                       // - y is listed in firstprivate clause
          }
       z[i] = y;   // Error - cannot reference i or y here
   }
}
```

句の詳細につい `default` ては、「 [2.7.2.5」セクション](2-directives.md#2725-default)を参照してください。

## <a name="a23-examples-of-the-ordered-directive"></a>Ordered ディレクティブの23の例

句を使用して、指定されたを含む複数の順序付けされたセクションを持つことができ `for` `ordered` ます。 最初の例は、API で次の規則が指定されているため、準拠していません。

"コンストラクトを持つループの反復処理では、同じディレクティブを複数回実行することはできません `for` 。また、複数のディレクティブを実行することはできません `ordered` `ordered` 。" (「 [2.6.6 ordered」セクション](2-directives.md#266-ordered-construct)を参照してください)。

この非準拠の例では、すべてのイテレーションが2つの順序付けられたセクションを実行します。

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

次の準拠する例は、複数の `for` 順序付けされたセクションを持つを示しています。

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```

## <a name="a24-example-of-the-private-clause"></a>プライベート句の24の例

並列領域の [private](2-directives.md#2721-private) 句は、領域の構文の範囲に対してのみ有効です。これは、領域の動的な範囲ではありません。  したがって、次の例では、ルーチンのループ内で *a 変数 a* を使用すると、のプライベートコピーが参照されますが、 `for` ルーチン *g* の使用法ではグローバル *a* が参照されます。 

```cpp
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>Copyprivate data attribute 句の25の例

**例 1:**[Copyprivate](2-directives.md#2728-copyprivate)句を使用すると、1つのスレッドによって取得された値を、他のスレッドのプライベート変数のすべてのインスタンスに直接ブロードキャストできます。

```cpp
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

ルーチン *初期化* がシリアル領域から呼び出された場合、その動作はディレクティブの存在による影響を受けません。 *Get_values* ルーチンの呼び出しが1つのスレッドによって実行されると、すべてのスレッドの *a*、 *b*、 *x*、および *y* によって指定されたプライベートオブジェクトが、値が読み込まれて定義されるまで、スレッドは構築を終了します。

**例 2:** 前の例とは異なり、読み取りは、マスタースレッドなど、特定のスレッドによって実行される必要があるとします。 この場合、句を `copyprivate` 使用してブロードキャストを直接実行することはできませんが、一時共有オブジェクトへのアクセスを提供するために使用できます。

```cpp
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**例 3:** 並列領域内で必要とされるロックオブジェクトの数は、入力する前に簡単に判断できないとします。 句を使用して、 `copyprivate` その並列領域内に割り当てられている共有ロックオブジェクトへのアクセスを提供できます。

```cpp
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```

## <a name="a26-the-threadprivate-directive"></a>. 26 threadprivate ディレクティブ

次の例では、 [threadprivate](2-directives.md#271-threadprivate-directive) ディレクティブを使用して、各スレッドに個別のカウンターを指定する方法を示します。

### <a name="example-1"></a>例 1

```cpp
int counter = 0;
#pragma omp threadprivate(counter)

int sub()
{
    counter++;
    return(counter);
}
```

### <a name="example-2"></a>例 2

```cpp
int sub()
{
    static int counter = 0;
    #pragma omp threadprivate(counter)
    counter++;
    return(counter);
}
```

## <a name="a27-c99-variable-length-arrays"></a>. 27 C99 可変長配列

次の例では、 [firstprivate](2-directives.md#2722-firstprivate) ディレクティブで C99 可変長配列 (vlas) を使用する方法を示します。

> [!NOTE]
> 可変長配列は現在、Visual C++ ではサポートされていません。

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-num_threads-clause"></a>Num_threads 句の28です。

次の例は、 [num_threads](2-directives.md#23-parallel-construct) 句を示しています。 並列領域は、最大で10個のスレッドで実行されます。

```cpp
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>重要なコンストラクト内にある、29の作業共有コンストラクト

次の例では、コンストラクト内で作業共有コンストラクトを使用する方法を示し `critical` ます。 この例は、ワークシェアリングコンストラクトと `critical` コンストラクトが同じ並行領域にバインドされていないため、準拠しています。

```cpp
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```

## <a name="a30-reprivatization"></a>. 30 Reprivatization

次の例は、変数の reprivatization を示しています。 プライベート変数は `private` 、入れ子になったディレクティブで再びマークできます。 これらの変数は、外側の並列領域で共有する必要はありません。

```cpp
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```

## <a name="a31-thread-safe-lock-functions"></a>. 31 スレッドセーフロック関数

次の C++ の例は、 [omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions)を使用して、並列領域内のロックの配列を初期化する方法を示しています。

```cpp
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```
