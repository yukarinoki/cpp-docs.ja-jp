---
title: OpenMP 環境変数
ms.date: 10/23/2018
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: 99868fec581d93f451d321af365f6c4546319077
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449687"
---
# <a name="openmp-environment-variables"></a>OpenMP 環境変数

OpenMP API で使用される環境変数へのリンクを提供します。

OpenMP の標準の Visual C の実装には、次の環境変数が含まれています。 これらの環境変数がプログラムの起動時に読み取られ、実行時にその値に対する変更は無視されます (たとえばを使用して[_putenv、_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md))。

|環境変数|説明|
|--------------------|-----------|
|[OMP_DYNAMIC](#omp-dynamic)|OpenMP の実行時に、並行領域内のスレッドの数を調整できるかどうかを指定します。|
|[OMP_NESTED](#omp-nested)|入れ子になった並列処理が有効になってこと、入れ子になった並列処理を有効になっているかを無効になっている場合を除き、かどうかを指定します。`omp_set_nested`します。|
|[OMP_NUM_THREADS](#omp-num-threads)|によってオーバーライドされない限り、並列の領域でスレッドの最大数を設定[omp_set_num_threads](openmp-functions.md#omp-set-num-threads)または[num_threads](openmp-clauses.md#num-threads)します。|
|[OMP_SCHEDULE](#omp-schedule)|動作を変更、[スケジュール](openmp-clauses.md#schedule)句と`schedule(runtime)`で指定された、`for`または`parallel for`ディレクティブ。|

## <a name="omp-dynamic"></a>OMP_DYNAMIC

OpenMP の実行時に、並行領域内のスレッドの数を調整できるかどうかを指定します。

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Remarks

`OMP_DYNAMIC`で環境変数をオーバーライドできます、 [omp_set_dynamic](openmp-functions.md#omp-set-dynamic)関数。

OpenMP の標準の Visual C の実装の既定値は`OMP_DYNAMIC=FALSE`します。

詳細については、[4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)を参照してください。

### <a name="example"></a>例

次のコマンド セット、`OMP_DYNAMIC`環境変数を TRUE にします。

```
set OMP_DYNAMIC=TRUE
```

次のコマンドの現在の設定の表示、`OMP_DYNAMIC`環境変数。

```
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

入れ子になった並列処理が有効になってこと、入れ子になった並列処理を有効になっているかを無効になっている場合を除き、かどうかを指定します。`omp_set_nested`します。

```
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Remarks

`OMP_NESTED`で環境変数をオーバーライドできます、 [omp_set_nested](openmp-functions.md#omp-set-nested)関数。

OpenMP の標準の Visual C の実装の既定値は`OMP_DYNAMIC=FALSE`します。

詳細については、[4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md)を参照してください。

### <a name="example"></a>例

次のコマンド セット、`OMP_NESTED`環境変数を TRUE にします。

```
set OMP_NESTED=TRUE
```

次のコマンドの現在の設定の表示、`OMP_NESTED`環境変数。

```
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

によってオーバーライドされない限り、並列の領域でスレッドの最大数を設定[omp_set_num_threads](openmp-functions.md#omp-set-num-threads)または[num_threads](openmp-clauses.md#num-threads)します。

```
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>パラメーター

*num*<br/>
Visual C の実装では 64 まで、並列領域で必要なスレッドの最大数。

### <a name="remarks"></a>Remarks

`OMP_NUM_THREADS`で環境変数をオーバーライドできます、 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads)関数または[num_threads](openmp-clauses.md#num-threads)します。

既定値`num`Visual C の OpenMP 標準の実装は、ハイパー スレッド Cpu などの仮想プロセッサの数。

詳細については、[4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)を参照してください。

### <a name="example"></a>例

次のコマンド セット、`OMP_NUM_THREADS`環境変数を 16。

```
set OMP_NUM_THREADS=16
```

次のコマンドの現在の設定の表示、`OMP_NUM_THREADS`環境変数。

```
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

動作を変更、[スケジュール](openmp-clauses.md#schedule)句と`schedule(runtime)`で指定された、`for`または`parallel for`ディレクティブ。

```
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>パラメーター

*size*<br/>
(省略可能)イテレーションのサイズを指定します。 `size` 正の整数である必要があります。 既定値は 1 の場合を除き、`type`は静的です。 有効でない場合に`type`は`runtime`します。

*type*<br/>
スケジュールの種類。

- `dynamic`
- `guided`
- `runtime`
- `static`

### <a name="remarks"></a>Remarks

OpenMP の標準の Visual C の実装の既定値は`OMP_SCHEDULE=static,0`します。

詳細については、[4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md)を参照してください。

### <a name="example"></a>例

次のコマンド セット、`OMP_SCHEDULE`環境変数。

```
set OMP_SCHEDULE="guided,2"
```

次のコマンドの現在の設定の表示、`OMP_SCHEDULE`環境変数。

```
set OMP_SCHEDULE
```
