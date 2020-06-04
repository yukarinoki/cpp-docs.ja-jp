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
- parallel
- section
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
ms.openlocfilehash: 569419b3422b155afc6e9692efaecd4e5a06f188
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366441"
---
# <a name="openmp-directives"></a>OpenMP ディレクティブ

OpenMP API で使用されるディレクティブへのリンクを提供します。

Visual C++ では、次の OpenMP ディレクティブがサポートされています。

並行ワークシェアリングの場合:

|ディレクティブ|説明|
|---------|-----------|
|[parallel](#parallel)|並列領域を定義します。|
|[for](#for-openmp)|並列領域内の`for`ループで実行された処理をスレッド間で分割します。|
|[セクション](#sections-openmp)|すべてのスレッドに分割するコード セクションを指定します。|
|[single](#single)|コードのセクションを、必ずしもマスター スレッドではなく、単一のスレッドで実行することを指定できます。|

マスタと同期の場合:

|ディレクティブ|説明|
|---------|-----------|
|[master](#master)|マスター スレッドだけがプログラムのセクションを実行することを指定します。|
|[critical](#critical)|コードが一度に 1 つのスレッドでのみ実行されることを指定します。|
|[障壁](#barrier)|チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまで、すべてのスレッドがバリアで一時停止します。|
|[アトミック (atomic)](#atomic)|アトミックに更新されるメモリ位置を指定します。|
|[フラッシュ](#flush-openmp)|すべてのスレッドが、すべての共有オブジェクトに対して同じメモリ ビューを持つことを指定します。|
|[注文](#ordered-openmp-directives)|並列`for`化されたループの下のコードをシーケンシャル ループのように実行することを指定します。|

データ環境の場合:

|ディレクティブ|説明|
|---------|-----------|
|[threadprivate](#threadprivate)|変数がスレッドに対してプライベートであることを指定します。|

## <a name="atomic"></a><a name="atomic"></a>原子

アトミックに更新されるメモリ位置を指定します。

```cpp
#pragma omp atomic
   expression
```

### <a name="parameters"></a>パラメーター

*式*<br/>
複数の書き込みから保護するメモリ位置を持つ*lvalue*を持つステートメント。

### <a name="remarks"></a>解説

ディレクティブ`atomic`は句をサポートしません。

詳細については、 [2.6.4 アトミックコンストラクト](../../../parallel/openmp/2-6-4-atomic-construct.md)を参照してください。

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

## <a name="barrier"></a><a name="barrier"></a>障壁

チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまで、すべてのスレッドがバリアで一時停止します。

```cpp
#pragma omp barrier
```

### <a name="remarks"></a>解説

ディレクティブ`barrier`は句をサポートしません。

詳細については[、2.6.3 バリア ディレクティブ](../../../parallel/openmp/2-6-3-barrier-directive.md)を参照してください。

### <a name="example"></a>例

の使用方法`barrier`の例については、「 [master](#master)」を参照してください。

## <a name="critical"></a><a name="critical"></a>重要

コードが一度に 1 つのスレッドでのみ実行されるように指定します。

```cpp
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>パラメーター

*name*<br/>
(オプション)重要なコードを識別する名前。 名前は括弧で囲む必要があります。

### <a name="remarks"></a>解説

ディレクティブ`critical`は句をサポートしません。

詳細については、 [2.6.2 クリティカルコンストラクト](../../../parallel/openmp/2-6-2-critical-construct.md)を参照してください。

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

## <a name="flush"></a><a name="flush-openmp"></a>フラッシュ

すべてのスレッドが、すべての共有オブジェクトに対して同じメモリ ビューを持つことを指定します。

```cpp
#pragma omp flush [(var)]
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
(オプション)同期するオブジェクトを表す変数のコンマ区切りのリスト。 *var*が指定されていない場合、すべてのメモリがフラッシュされます。

### <a name="remarks"></a>解説

ディレクティブ`flush`は句をサポートしません。

詳細については、 [2.6.5 フラッシュ ディレクティブ](../../../parallel/openmp/2-6-5-flush-directive.md)を参照してください。

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

## <a name="for"></a>次の場合は <a name="for-openmp"></a>: 

並列領域内の`for`ループで実行された処理をスレッド間で分割します。

```cpp
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>パラメーター

*句*<br/>
(オプション)0 個以上の句については、「**解説」** を参照してください。

*for_statement*<br/>
`for`ループ。 ループ内のユーザー コードがインデックス変数を`for`変更すると、未定義の動作が発生します。

### <a name="remarks"></a>解説

ディレクティブ`for`は、次の句をサポートしています。

- [プライベート](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [注文](openmp-clauses.md#ordered-openmp-clauses)
- [スケジュール](openmp-clauses.md#schedule)
- [Nowait](openmp-clauses.md#nowait)

また`parallel`、指定されている場合`clauses`は、`parallel`または`for`ディレクティブで受け入れられる句`nowait`を指定できます 。

詳細については、 [2.4.1 の構築を参照](../../../parallel/openmp/2-4-1-for-construct.md)してください。

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

## <a name="master"></a><a name="master"></a>マスター

マスター スレッドだけがプログラムのセクションを実行することを指定します。

```cpp
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>解説

ディレクティブ`master`は句をサポートしません。

[単一](#single)のディレクティブを使用すると、コードのセクションを、必ずしもマスター スレッドではなく、単一のスレッドで実行することを指定できます。

詳細については、 [2.6.1 マスターコンストラクト](../../../parallel/openmp/2-6-1-master-construct.md)を参照してください。

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

## <a name="ordered"></a><a name="ordered-openmp-directives"></a>注文

並列`for`化されたループの下のコードをシーケンシャル ループのように実行することを指定します。

```cpp
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>解説

ディレクティブ`ordered`は、句を含む[for](#for-openmp)または`parallel for`construct の`ordered`動的範囲内になければなりません。

ディレクティブ`ordered`は句をサポートしません。

詳細については、 [2.6.6 順序付きコンストラクト](../../../parallel/openmp/2-6-6-ordered-construct.md)を参照してください。

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

## <a name="parallel"></a><a name="parallel"></a>並列

並列領域を定義します。

```cpp
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>パラメーター

*句*<br/>
(オプション)0 個以上の句については、「**解説」** を参照してください。

### <a name="remarks"></a>解説

ディレクティブ`parallel`は、次の句をサポートしています。

- [if](openmp-clauses.md#if-openmp)
- [プライベート](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [共有](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [reduction](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel`for[および](#for-openmp)[sections](#sections-openmp)ディレクティブと共に使用することもできます。

詳細については、 [2.3 並列構造](../../../parallel/openmp/2-3-parallel-construct.md)を参照してください。

### <a name="example"></a>例

次の例は、スレッド数を設定し、並列領域を定義する方法を示しています。 スレッドの数は、デフォルトではマシン上の論理プロセッサの数と同じです。 たとえば、ハイパースレッディングが有効になっている物理プロセッサが 1 つあるマシンがある場合、2 つの論理プロセッサと 2 つのスレッドが存在します。 出力の順序は、マシンによって異なる場合があります。

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

## <a name="sections"></a><a name="sections-openmp"></a>セクション

すべてのスレッドに分割するコード セクションを指定します。

```cpp
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
(オプション)0 個以上の句については、「**解説」** を参照してください。

### <a name="remarks"></a>解説

ディレクティブ`sections`には、0 個以上`section`のディレクティブを含めることができます。

ディレクティブ`sections`は、次の句をサポートしています。

- [プライベート](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [reduction](openmp-clauses.md#reduction)
- [Nowait](openmp-clauses.md#nowait)

また`parallel`、指定されている場合`clauses`は、`parallel`または`sections`ディレクティブで受け入れられる句`nowait`を指定できます 。

詳細については、 [2.4.2 セクションの構成を](../../../parallel/openmp/2-4-2-sections-construct.md)参照してください。

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

## <a name="single"></a><a name="single"></a>単一

コードのセクションを、必ずしもマスター スレッドではなく、単一のスレッドで実行することを指定できます。

```cpp
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>パラメーター

*句*<br/>
(オプション)0 個以上の句については、「**解説」** を参照してください。

### <a name="remarks"></a>解説

ディレクティブ`single`は、次の句をサポートしています。

- [プライベート](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [Nowait](openmp-clauses.md#nowait)

[master](#master)ディレクティブを使用すると、コードのセクションをマスター スレッドでのみ実行することを指定できます。

詳細については、 [2.4.3 単一のコンストラクト](../../../parallel/openmp/2-4-3-single-construct.md)を参照してください。

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

## <a name="threadprivate"></a><a name="threadprivate"></a>Threadprivate

変数がスレッドに対してプライベートであることを指定します。

```cpp
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>パラメーター

*Var*<br/>
スレッドをプライベートにする変数のコンマ区切りのリスト。 *var*は、グローバル変数または名前空間スコープ変数、またはローカル静的変数でなければなりません。

### <a name="remarks"></a>解説

ディレクティブ`threadprivate`は句をサポートしません。

ディレクティブ`threadprivate`は[、__declspec](../../../cpp/declspec.md)キーワードを使用して[スレッド](../../../cpp/thread.md)属性に基づいています。の制限`__declspec(thread)`が`threadprivate`に適用されます。 たとえば、並列領域`threadprivate`によって生成されたスレッド チームの一部であるスレッドだけでなく、プロセスで開始されるスレッドに変数が存在します。 この実装の詳細に注意してください。ユーザー定義型のコンストラクタが、より`threadprivate`頻繁に呼び出され、期待されることがわかります。

プロセスの起動時`threadprivate`に静的に読み込まれる DLL で使用できますが[、/DELAYLOAD (読み込み遅延インポート)](../../../build/reference/delayload-delay-load-import.md)を使用する DLL など[、LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)を介して読み込まれる DLL`LoadLibrary`では使用`threadprivate`できません。

デス`threadprivate`トラクターが呼び出される保証されていない *、デストラクター*型の変数です。 次に例を示します。

```cpp
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

ユーザーは、並列領域を構成するスレッドがいつ終了するかを制御できません。 プロセスの終了時にこれらのスレッドが存在する場合、プロセスの終了に関する通知は行われず、終了するスレッド (ここではプライマリ スレッド`threaded_var`) 以外のスレッドではデストラクターが呼び出されません。 したがって、コードは変数の適切な破棄を`threadprivate`当てにすべきではありません。

詳細については、 [2.7.1 スレッドプライベート ディレクティブ](../../../parallel/openmp/2-7-1-threadprivate-directive.md)を参照してください。

### <a name="example"></a>例

の使用`threadprivate`の例については、 [private](openmp-clauses.md#private-openmp)を参照してください。
