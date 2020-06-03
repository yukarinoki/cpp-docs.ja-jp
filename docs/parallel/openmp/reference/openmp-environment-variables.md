---
title: OpenMP の環境変数
ms.date: 03/20/2019
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
ms.openlocfilehash: bee9b0fbdf147ee962ff92d0b3b9ff57d4209f84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363885"
---
# <a name="openmp-environment-variables"></a>OpenMP の環境変数

OpenMP API で使用される環境変数へのリンクを提供します。

OpenMP 標準の Visual C++ 実装には、次の環境変数が含まれています。 これらの環境変数はプログラムの起動時に読み込まれ、その値に対する変更は実行時に無視されます (たとえば[、_putenvを使用して、_wputenv)。](../../../c-runtime-library/reference/putenv-wputenv.md)

|環境変数|説明|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|または`parallel for`ディレクティブで指定されている場合`schedule(runtime)`に[、スケジュール](openmp-clauses.md#schedule)句の動作`for`を変更します。|
|[OMP_NUM_THREADS](#omp-num-threads)|[omp_set_num_threads](openmp-functions.md#omp-set-num-threads)または[num_threads](openmp-clauses.md#num-threads)でオーバーライドされない限り、並列領域内のスレッドの最大数を設定します。|
|[OMP_DYNAMIC](#omp-dynamic)|OpenMP ランタイムが並列領域のスレッド数を調整できるかどうかを指定します。|
|[OMP_NESTED](#omp-nested)|で入れ子の並列処理が有効または無効にされていない限り、入れ子`omp_set_nested`の並列処理を有効にするかどうかを指定します。|

## <a name="omp_dynamic"></a><a name="omp-dynamic"></a>OMP_DYNAMIC

OpenMP ランタイムが並列領域のスレッド数を調整できるかどうかを指定します。

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>解説

環境変数`OMP_DYNAMIC`は[、omp_set_dynamic](openmp-functions.md#omp-set-dynamic)関数によってオーバーライドできます。

OpenMP 標準の Visual C++ 実装の既定値は`OMP_DYNAMIC=FALSE`です。

詳細については[、「4.3 OMP_DYNAMIC」](../../../parallel/openmp/4-3-omp-dynamic.md)を参照してください。

### <a name="example"></a>例

次のコマンドは、`OMP_DYNAMIC`環境変数を TRUE に設定します。

```cmd
set OMP_DYNAMIC=TRUE
```

次のコマンドは、環境変数の現在の`OMP_DYNAMIC`設定を表示します。

```cmd
set OMP_DYNAMIC
```

## <a name="omp_nested"></a><a name="omp-nested"></a>OMP_NESTED

で入れ子の並列処理が有効または無効にされていない限り、入れ子`omp_set_nested`の並列処理を有効にするかどうかを指定します。

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>解説

環境変数`OMP_NESTED`は[、omp_set_nested](openmp-functions.md#omp-set-nested)関数によってオーバーライドできます。

OpenMP 標準の Visual C++ 実装の既定値は`OMP_DYNAMIC=FALSE`です。

詳細については[、「4.4 OMP_NESTED」](../../../parallel/openmp/4-4-omp-nested.md)を参照してください。

### <a name="example"></a>例

次のコマンドは、`OMP_NESTED`環境変数を TRUE に設定します。

```cmd
set OMP_NESTED=TRUE
```

次のコマンドは、環境変数の現在の`OMP_NESTED`設定を表示します。

```cmd
set OMP_NESTED
```

## <a name="omp_num_threads"></a><a name="omp-num-threads"></a>Omp_num_threads

[omp_set_num_threads](openmp-functions.md#omp-set-num-threads)または[num_threads](openmp-clauses.md#num-threads)でオーバーライドされない限り、並列領域内のスレッドの最大数を設定します。

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>パラメーター

*num*<br/>
並列領域に必要なスレッドの最大数 (Visual C++ 実装では最大 64 個)。

### <a name="remarks"></a>解説

環境変数`OMP_NUM_THREADS`は[、omp_set_num_threads](openmp-functions.md#omp-set-num-threads)関数または[num_threads](openmp-clauses.md#num-threads)によってオーバーライドできます。

OpenMP 標準`num`の Visual C++ 実装の既定値は、ハイパースレッディング CPU を含む仮想プロセッサの数です。

詳細については、「 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)」 を参照してください。

### <a name="example"></a>例

次のコマンドは、`OMP_NUM_THREADS`環境変数を`16`に設定します。

```cmd
set OMP_NUM_THREADS=16
```

次のコマンドは、環境変数の現在の`OMP_NUM_THREADS`設定を表示します。

```cmd
set OMP_NUM_THREADS
```

## <a name="omp_schedule"></a><a name="omp-schedule"></a>OMP_SCHEDULE

または`parallel for`ディレクティブで指定されている場合`schedule(runtime)`に[、スケジュール](openmp-clauses.md#schedule)句の動作`for`を変更します。

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
(オプション)反復のサイズを指定します。 *size*は正の整数でなければなりません。 既定は、`1`*型*が静的である場合を除き、 です。 *型*が の場合`runtime`は無効です。

*type*<br/>
スケジュールの種類 ( `dynamic`、 `guided` `runtime`、 `static`、 、 、 、 のいずれか ) 。

### <a name="remarks"></a>解説

OpenMP 標準の Visual C++ 実装の既定値は`OMP_SCHEDULE=static,0`です。

詳細については[、「4.1 OMP_SCHEDULE」](../../../parallel/openmp/4-1-omp-schedule.md)を参照してください。

### <a name="example"></a>例

次のコマンドは、`OMP_SCHEDULE`環境変数を設定します。

```cmd
set OMP_SCHEDULE="guided,2"
```

次のコマンドは、環境変数の現在の`OMP_SCHEDULE`設定を表示します。

```cmd
set OMP_SCHEDULE
```
