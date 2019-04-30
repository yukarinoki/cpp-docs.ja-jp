---
title: OpenMP ディレクティブ
ms.date: 03/20/2019
f1_keywords:
- OpenMP directives
- atomic
- barrier
- critical
- flush
- for
- master
- ordered
- parallel
- section
- SECTIONS
- single
- threadprivate
helpviewer_keywords:
- OpenMP directives
- atomic OpenMP directive
- barrier OpenMP directive
- critical OpenMP directive
- flush OpenMP directive
- for OpenMP directive
- master OpenMP directive
- ordered OpenMP directive
- parallel OpenMP directive
- sections OpenMP directive
- single OpenMP directive
- threadprivate OpenMP directive
ms.assetid: 0562c263-344c-466d-843e-de830d918940
ms.openlocfilehash: d644b612c0c326692786c94046d799163dfbce8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362687"
---
# <a name="openmp-directives"></a>OpenMP ディレクティブ

OpenMP API で使用するディレクティブへのリンクを提供します。

VisualC++次 OpenMP ディレクティブをサポートしています。

並列作業の共有。

|ディレクティブ|説明|
|---------|-----------|
|[parallel](#parallel)|複数のスレッドを並列で実行されるコードは、並列領域を定義します。|
|[for](#for-openmp)|行われる動作、`for`スレッド間で除算する、並行領域内でループします。|
|[sections](#sections-openmp)|すべてのスレッド間で分配するコード セクションを識別します。|
|[single](#single)|コードのセクションは、シングル スレッドで実行する必要があります指定できます。|

マスターと同期します。

|ディレクティブ|説明|
|---------|-----------|
|[master](#master)|マスタ スレッドだけがプログラムのセクションを実行する必要がありますを指定します。|
|[critical](#critical)|コードが、一度に 1 つのスレッドでのみ実行されるかを指定します。|
|[barrier](#barrier)|チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまでのすべてのスレッドがバリアで一時停止します。|
|[atomic](#atomic)|指定するアトミックに更新されるメモリの場所。|
|[flush](#flush-openmp)|すべてのスレッドがすべての共有オブジェクトのメモリの同じビューを持つことを指定します。|
|[順序付け](#ordered-openmp-directives)|並行処理には、そのコードを指定します`for`シーケンシャル ループのようなループを実行する必要があります。|

データ環境。

|ディレクティブ|説明|
|---------|-----------|
|[threadprivate](#threadprivate)|変数は、スレッドに対してプライベートであることを指定します。|

## <a name="atomic"></a>アトミック

指定するアトミックに更新されるメモリの場所。

```
#pragma omp atomic
   expression
```

### <a name="parameters"></a>パラメーター

*式 (expression)*<br/>
ステートメントを持つ、*左辺値*、1 つ以上の書き込みに対して保護するメモリ位置。

### <a name="remarks"></a>Remarks

`atomic`ディレクティブに句がサポートされていません。

詳細については、次を参照してください。 [2.6.4 atomic 構築](../../../parallel/openmp/2-6-4-atomic-construct.md)します。

### <a name="example"></a>例

```cpp
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

## <a name="barrier"></a>バリア

チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまでのすべてのスレッドがバリアで一時停止します。

```
#pragma omp barrier
```

### <a name="remarks"></a>Remarks

`barrier`ディレクティブに句がサポートされていません。

詳細については、次を参照してください。 [2.6.3 barrier ディレクティブ](../../../parallel/openmp/2-6-3-barrier-directive.md)します。

### <a name="example"></a>例

使用する方法の例については`barrier`を参照してください[マスター](#master)します。

## <a name="critical"></a>重要です

コードは一度に 1 つのスレッドでのみ実行することを指定します。

```
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>パラメーター

*name*<br/>
(省略可能)Critical コードを識別する名前。 名前は、かっこで囲む必要があります。

### <a name="remarks"></a>Remarks

`critical`ディレクティブに句がサポートされていません。

詳細については、次を参照してください。 [2.6.2 の重要な構築](../../../parallel/openmp/2-6-2-critical-construct.md)します。

### <a name="example"></a>例

```cpp
// omp_critical.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10

int main()
{
    int i;
    int max;
    int a[SIZE];

    for (i = 0; i < SIZE; i++)
    {
        a[i] = rand();
        printf_s("%d\n", a[i]);
    }

    max = a[0];
    #pragma omp parallel for num_threads(4)
        for (i = 1; i < SIZE; i++)
        {
            if (a[i] > max)
            {
                #pragma omp critical
                {
                    // compare a[i] and max again because max
                    // could have been changed by another thread after
                    // the comparison outside the critical section
                    if (a[i] > max)
                        max = a[i];
                }
            }
        }

    printf_s("max = %d\n", max);
}
```

```Output
41
18467
6334
26500
19169
15724
11478
29358
26962
24464
max = 29358
```

## <a name="flush-openmp"></a>フラッシュ

すべてのスレッドがすべての共有オブジェクトのメモリの同じビューを持つことを指定します。

```
#pragma omp flush [(var)]
```

### <a name="parameters"></a>パラメーター

*var*<br/>
(省略可能)同期するオブジェクトを表す変数のコンマ区切りの一覧。 場合*var*が指定されていないすべてのメモリをフラッシュします。

### <a name="remarks"></a>Remarks

`flush`ディレクティブに句がサポートされていません。

詳細については、次を参照してください。 [2.6.5 flush ディレクティブ](../../../parallel/openmp/2-6-5-flush-directive.md)します。

### <a name="example"></a>例

```cpp
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

## <a name="for-openmp"></a>の

行われる動作、`for`スレッド間で除算する、並行領域内でループします。

```
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>パラメーター

*句*<br/>
(省略可能)0 個以上の句を参照してください、**解説**セクション。

*for_statement*<br/>
A`for`ループします。 ユーザー コードで未定義の動作が発生、`for`ループ インデックス変数を変更します。

### <a name="remarks"></a>Remarks

`for`ディレクティブは、次の句をサポートしています。

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [順序付け](openmp-clauses.md#ordered-openmp-clauses)
- [schedule](openmp-clauses.md#schedule)
- [nowait](openmp-clauses.md#nowait)

場合`parallel`が指定されても、`clauses`句受け入れ可能で、`parallel`または`for`ディレクティブを除く`nowait`。

詳細については、次を参照してください。 [2.4.1 for のコンストラクト](../../../parallel/openmp/2-4-1-for-construct.md)します。

### <a name="example"></a>例

```cpp
// omp_for.cpp
// compile with: /openmp
#include <stdio.h>
#include <math.h>
#include <omp.h>

#define NUM_THREADS 4
#define NUM_START 1
#define NUM_END 10

int main() {
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;
   int nThreads = 0, nTmp = nStart + nEnd;
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *
                               unsigned(abs(nTmp))) / 2;
   int nSumCalc = uTmp;

   if (nTmp < 0)
      nSumCalc = -nSumCalc;

   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)
   {
      #pragma omp master
      nThreads = omp_get_num_threads();

      #pragma omp for
      for (i=nStart; i<=nEnd; ++i) {
            #pragma omp atomic
            nSum += i;
      }
   }

   if  (nThreads == NUM_THREADS) {
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);
      nRet = 0;
   }
   else {
      printf_s("Expected %d OpenMP threads, but %d were used.\n",
               NUM_THREADS, nThreads);
      nRet = 1;
   }

   if (nSum != nSumCalc) {
      printf_s("The sum of %d through %d should be %d, "
               "but %d was reported!\n",
               NUM_START, NUM_END, nSumCalc, nSum);
      nRet = 1;
   }
   else
      printf_s("The sum of %d through %d is %d\n",
               NUM_START, NUM_END, nSum);
}
```

```Output
4 OpenMP threads were used.
The sum of 1 through 10 is 55
```

## <a name="master"></a>マスター

マスタ スレッドだけがプログラムのセクションを実行する必要がありますを指定します。

```
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Remarks

`master`ディレクティブに句がサポートされていません。

[単一](#single)ディレクティブを使用して、シングル スレッドでコードのセクションを実行するように指定できます。

詳細については、次を参照してください。 [2.6.1 master コンストラクト](../../../parallel/openmp/2-6-1-master-construct.md)します。

### <a name="example"></a>例

```cpp
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="ordered-openmp-directives"></a>順序付け

並行処理には、そのコードを指定します`for`シーケンシャル ループのようなループを実行する必要があります。

```
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Remarks

`ordered`ディレクティブはの動的範囲内である必要があります、[の](#for-openmp)または`parallel for`で構築、`ordered`句。

`ordered`ディレクティブに句がサポートされていません。

詳細については、次を参照してください。 [2.6.6 ordered コンストラクト](../../../parallel/openmp/2-6-6-ordered-construct.md)します。

### <a name="example"></a>例

```cpp
// omp_ordered.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

static float a[1000], b[1000], c[1000];

void test(int first, int last)
{
    #pragma omp for schedule(static) ordered
    for (int i = first; i <= last; ++i) {
        // Do something here.
        if (i % 2)
        {
            #pragma omp ordered
            printf_s("test() iteration %d\n", i);
        }
    }
}

void test2(int iter)
{
    #pragma omp ordered
    printf_s("test2() iteration %d\n", iter);
}

int main( )
{
    int i;
    #pragma omp parallel
    {
        test(1, 8);
        #pragma omp for ordered
        for (i = 0 ; i < 5 ; i++)
            test2(i);
    }
}
```

```Output
test() iteration 1
test() iteration 3
test() iteration 5
test() iteration 7
test2() iteration 0
test2() iteration 1
test2() iteration 2
test2() iteration 3
test2() iteration 4
```

## <a name="parallel"></a>並列

複数のスレッドを並列で実行されるコードは、並列領域を定義します。

```
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>パラメーター

*句*<br/>
(省略可能)0 個以上の句を参照してください、**解説**セクション。

### <a name="remarks"></a>Remarks

`parallel`ディレクティブは、次の句をサポートしています。

- [if](openmp-clauses.md#if-openmp)
- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [shared](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel` 使用することができますも、[の](#for-openmp)と[セクション](#sections-openmp)ディレクティブ。

詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)します。

### <a name="example"></a>例

次の例では、スレッドの数を設定し、並列領域を定義する方法を示します。 スレッドの数は既定では、マシン上の論理プロセッサの数です。 たとえば、ハイパースレッディングが有効になっている 1 つの物理プロセッサを搭載したコンピューターがある場合は、2 つの論理プロセッサと 2 つのスレッドがあります。 出力の順序は、マシンによって異なります。

```cpp
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="sections-openmp"></a>セクション

すべてのスレッド間で分配するコード セクションを識別します。

```
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   }
}
```

### <a name="parameters"></a>パラメーター

*句*<br/>
(省略可能)0 個以上の句を参照してください、**解説**セクション。

### <a name="remarks"></a>Remarks

`sections`ディレクティブは、0 個以上含めることができます`section`ディレクティブ。

`sections`ディレクティブは、次の句をサポートしています。

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [nowait](openmp-clauses.md#nowait)

場合`parallel`が指定されても、`clauses`句受け入れ可能で、`parallel`または`sections`ディレクティブを除く`nowait`。

詳細については、次を参照してください。 [2.4.2 sections のコンストラクト](../../../parallel/openmp/2-4-2-sections-construct.md)します。

### <a name="example"></a>例

```cpp
// omp_sections.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
    #pragma omp parallel sections num_threads(4)
    {
        printf_s("Hello from thread %d\n", omp_get_thread_num());
        #pragma omp section
        printf_s("Hello from thread %d\n", omp_get_thread_num());
    }
}
```

```Output
Hello from thread 0
Hello from thread 0
```

## <a name="single"></a>1 つ

コードのセクションは、シングル スレッドで実行する必要があります指定できます。

```
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>パラメーター

*句*<br/>
(省略可能)0 個以上の句を参照してください、**解説**セクション。

### <a name="remarks"></a>Remarks

`single`ディレクティブは、次の句をサポートしています。

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [nowait](openmp-clauses.md#nowait)

[マスター](#master)ディレクティブを使用して、コードのセクションをマスター スレッドでのみ実行するように指定できます。

詳細については、次を参照してください。 [2.4.3 の 1 つ構築](../../../parallel/openmp/2-4-3-single-construct.md)します。

### <a name="example"></a>例

```cpp
// omp_single.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(2)
   {
      #pragma omp single
      // Only a single thread can read the input.
      printf_s("read input\n");

      // Multiple threads in the team compute the results.
      printf_s("compute results\n");

      #pragma omp single
      // Only a single thread can write the output.
      printf_s("write output\n");
    }
}
```

```Output
read input
compute results
compute results
write output
```

## <a name="threadprivate"></a>threadprivate

変数は、スレッドに対してプライベートであることを指定します。

```
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>パラメーター

*var*<br/>
スレッドに非公開にする変数のコンマ区切りの一覧。 *var*グローバルまたは名前空間スコープの変数または静的ローカル変数のいずれかにする必要があります。

### <a name="remarks"></a>Remarks

`threadprivate`ディレクティブに句がサポートされていません。

`threadprivate`ディレクティブがに基づいて、[スレッド](../../../cpp/thread.md)属性を使用して、 [_ _declspec](../../../cpp/declspec.md)キーワード; に対する制限`__declspec(thread)`に適用`threadprivate`します。 たとえば、`threadprivate`変数は、任意のスレッドが並列領域により生成されたスレッド チームの一部であるスレッドだけでなく、プロセスの開始に存在します。 この実装の詳細に注意してください。コンス トラクター、`threadprivate`ユーザー定義型は予想以上と呼ばれます。

使用することができます`threadprivate`でプロセスの起動時に静的に読み込まれる DLL、ただしは使用できません`threadprivate`経由で読み込まれる DLL で[LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya)で読み込まれる Dll など[/DELAYLOAD (遅延読み込みのインポート)](../../../build/reference/delayload-delay-load-import.md)、使用することも`LoadLibrary`します。

A`threadprivate`の変数を*破棄可能な*と呼ばれる、デストラクターがある型は保証されません。 例:

```
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

ユーザーは、並列領域を構成するスレッドが終了すると、コントロールを持つありません。 プロセスが終了するし、スレッドのプロセスの終了に関する通知が送られませんのデストラクターは呼び出されません、それらのスレッドが存在しない場合`threaded_var`に存在する 1 つを除く任意のスレッドで (ここでは、プライマリ スレッド)。 コードは適切な破棄のため`threadprivate`変数。

詳細については、次を参照してください。 [2.7.1 threadprivate ディレクティブ](../../../parallel/openmp/2-7-1-threadprivate-directive.md)します。

### <a name="example"></a>例

使用するサンプルの`threadprivate`を参照してください[プライベート](openmp-clauses.md#private-openmp)します。
