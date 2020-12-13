---
description: 詳細については、次を参照してください。 4. 環境変数
title: 4. 環境変数
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: 47c0d557497a387f89c13c88c414aae9eb9377ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342531"
---
# <a name="4-environment-variables"></a>4. 環境変数

この章では、並列コードの実行を制御する OpenMP C および C++ API 環境変数 (または同様のプラットフォーム固有の機構) について説明します。  環境変数の名前は大文字にする必要があります。 割り当てられた値は大文字と小文字が区別されず、先頭と末尾に空白が含まれる場合があります。  プログラムの開始後に値を変更しても、その変更は無視されます。

環境変数は次のとおりです。

- [OMP_SCHEDULE](#41-omp_schedule) は、実行時のスケジュールの種類とチャンクサイズを設定します。
- 実行中に使用するスレッドの数を[OMP_NUM_THREADS](#42-omp_num_threads)設定します。
- [OMP_DYNAMIC](#43-omp_dynamic) スレッド数の動的な調整を有効または無効にします。
- 入れ子になった並列処理を有効または無効に[OMP_NESTED](#44-omp_nested)ます。

この章の例では、これらの変数が Unix C シェル (csh) 環境でどのように設定されるかを示しています。 Korn シェルと DOS 環境では、次のようなアクションが実行されます。

csh  
`setenv OMP_SCHEDULE "dynamic"`

ksh  
`export OMP_SCHEDULE="dynamic"`

同名  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a><a name="41-omp_schedule"></a> 4.1 OMP_SCHEDULE

`OMP_SCHEDULE` は `for` 、および `parallel for` スケジュールの種類を持つディレクティブにのみ適用さ `runtime` れます。 このようなすべてのループのスケジュールの種類とチャンクサイズは、実行時に設定できます。 この環境変数を、認識されているスケジュールの種類とオプションの *chunk_size* に設定します。

`for`および `parallel for` 以外のスケジュールの種類を持つディレクティブの場合 `runtime` 、 `OMP_SCHEDULE` は無視されます。 この環境変数の既定値は、実装によって定義されています。 オプションの *chunk_size* が設定されている場合、値は正の値である必要があります。 *Chunk_size* が設定されていない場合は、スケジュールがの場合を除き、値1が想定され `static` ます。 スケジュールの場合 `static` 、既定のチャンクサイズは、ループに適用されるスレッドの数で割ったループの反復領域に設定されます。

例:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>相互参照

- ディレクティブ[の場合](2-directives.md#241-for-construct)
- [parallel for](2-directives.md#251-parallel-for-construct) ディレクティブ

## <a name="42-omp_num_threads"></a><a name="42-omp_num_threads"></a> 4.2 OMP_NUM_THREADS

`OMP_NUM_THREADS`環境変数は、実行時に使用する既定のスレッド数を設定します。 `OMP_NUM_THREADS` ライブラリルーチンを呼び出すことによってその数値が明示的に変更された場合、は無視され `omp_set_num_threads` ます。 ディレクティブに明示的な句がある場合にも無視さ `num_threads` `parallel` れます。

環境変数の値は正の整数である `OMP_NUM_THREADS` 必要があります。 その効果は、スレッド数の動的調整が有効になっているかどうかによって異なります。 環境変数とスレッドの動的調整の間の相互作用に関するルールの包括的なセットについ `OMP_NUM_THREADS` ては、 [セクション 2.3](2-directives.md#23-parallel-construct)を参照してください。

使用するスレッドの数は、次の場合に実装で定義されます。

- `OMP_NUM_THREADS`環境変数が指定されていません。
- 指定された値が正の整数ではありません。
- 値が、システムがサポートできるスレッドの最大数を超えています。

例:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>相互参照

- [num_threads](2-directives.md#23-parallel-construct) 句
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function) 関数
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) 関数

## <a name="43-omp_dynamic"></a><a name="43-omp_dynamic"></a> 4.3 OMP_DYNAMIC

`OMP_DYNAMIC`環境変数は、並列領域の実行に使用できるスレッド数の動的な調整を有効または無効にします。 `OMP_DYNAMIC` ライブラリルーチンを呼び出すことによって動的調整が明示的に有効または無効にされている場合、は無視され `omp_set_dynamic` ます。 値はまたはである必要があり `TRUE` `FALSE` ます。

`OMP_DYNAMIC`がに設定されている場合 `TRUE` 、並列領域の実行に使用されるスレッドの数は、システムリソースを最適に使用できるように、ランタイム環境によって調整されることがあります。  `OMP_DYNAMIC`がに設定されている場合 `FALSE` 、動的調整は無効になります。 既定の条件は、実装によって定義されます。

例:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>相互参照

- [並列領域](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) 関数

## <a name="44-omp_nested"></a><a name="44-omp_nested"></a> 4.4 OMP_NESTED

`OMP_NESTED`環境変数は、ライブラリルーチンを呼び出して入れ子になった並列処理を有効または無効にしない限り、入れ子になった並列処理を有効または無効にし `omp_set_nested` ます。 `OMP_NESTED`がに設定されている場合、入れ子になった `TRUE` 並列処理が有効になります。 がに設定されている場合、入れ子になった `OMP_NESTED` `FALSE` 並列処理は無効になります。 既定値は `FALSE` です。

例:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>相互参照

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) 関数
