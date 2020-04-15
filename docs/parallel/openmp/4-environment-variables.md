---
title: 4. 環境変数
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: e93c59654c17ed6dbfb7483ac2dce716ce24b52a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370268"
---
# <a name="4-environment-variables"></a>4. 環境変数

この章では、並列コードの実行を制御する OpenMP C および C++ API 環境変数 (またはプラットフォーム固有の同様のメカニズム) について説明します。  環境変数の名前は大文字にする必要があります。 割り当てられた値は大文字と小文字を区別せず、先頭と末尾の空白を持つ可能性があります。  プログラムの開始後の値の変更は無視されます。

環境変数は次のとおりです。

- [OMP_SCHEDULE](#41-omp_schedule)ランタイム スケジュールの種類とチャンク サイズを設定します。
- [OMP_NUM_THREADS、](#42-omp_num_threads)実行中に使用するスレッドの数を設定します。
- [OMP_DYNAMIC](#43-omp_dynamic)は、スレッド数の動的調整を有効または無効にします。
- [OMP_NESTED](#44-omp_nested)は、入れ子の並列処理を有効または無効にします。

この章の例では、Unix C シェル (csh) 環境でこれらの変数がどのように設定されるかについて説明します。 Korn シェル環境と DOS 環境では、アクションは次のようになります。

Csh：  
`setenv OMP_SCHEDULE "dynamic"`

Ksh：  
`export OMP_SCHEDULE="dynamic"`

Dos：  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a><a name="41-omp_schedule"></a>4.1 OMP_SCHEDULE

`OMP_SCHEDULE`は、`for`スケジュール`parallel for`の種類`runtime`を持つ ディレクティブおよび ディレクティブにのみ適用されます。 このようなループのスケジュールタイプとチャンクサイズは、実行時に設定できます。 この環境変数を任意の認識されたスケジュール・タイプに設定し、オプションの*chunk_size*に設定します。

と`for``parallel for`以外のスケジュールの種類`runtime`を持つディレクティブ`OMP_SCHEDULE`は無視されます。 この環境変数のデフォルト値は、実装定義です。 オプションの*chunk_size*が設定されている場合、値は正でなければなりません。 *chunk_size*が設定されていない場合、スケジュールが の場合を除き、値 1`static`が使用されます。 スケジュールの`static`場合、既定のチャンク サイズはループの反復領域をループに適用されるスレッド数で割って設定されます。

例:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>クロスリファレンス

- ディレクティブ[用](2-directives.md#241-for-construct)
- ディレクティブ[の並列](2-directives.md#251-parallel-for-construct)

## <a name="42-omp_num_threads"></a><a name="42-omp_num_threads"></a>4.2 OMP_NUM_THREADS

環境変数`OMP_NUM_THREADS`は、実行時に使用するスレッドのデフォルト数を設定します。 `OMP_NUM_THREADS`は、その番号がライブラリー・ルーチンを呼び出して`omp_set_num_threads`明示的に変更された場合は無視されます。 `parallel`ディレクティブに明示的`num_threads`な句がある場合も無視されます。

環境変数の`OMP_NUM_THREADS`値は正の整数でなければなりません。 その効果は、スレッド数の動的調整が有効かどうかによって異なります。 環境変数とスレッドの動的調整の相互作用に関する包括的な規則については、[セクション 2.3](2-directives.md#23-parallel-construct)を参照してください。 `OMP_NUM_THREADS`

使用するスレッドの数は、次の場合に実装で定義されます。

- 環境変数`OMP_NUM_THREADS`が指定されていません。
- 指定された値は正の整数ではありません。
- この値は、システムがサポートできるスレッドの最大数を超えています。

例:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>クロスリファレンス

- [num_threads](2-directives.md#23-parallel-construct)条項
- [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function)機能
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)機能

## <a name="43-omp_dynamic"></a><a name="43-omp_dynamic"></a>4.3 OMP_DYNAMIC

環境変数`OMP_DYNAMIC`は、並列領域の実行に使用できるスレッド数の動的調整を有効または無効にします。 `OMP_DYNAMIC`動的調整が明示的に有効または無効にされている場合、ライブラリ ルーチン`omp_set_dynamic`を呼び出すことによって無視されます。 その値は、 `TRUE` `FALSE`または でなければなりません。

に`OMP_DYNAMIC`設定`TRUE`されている場合、並列領域の実行に使用されるスレッドの数は、システム リソースを最大限に利用するようにランタイム環境によって調整できます。  に`OMP_DYNAMIC`設定`FALSE`されている場合、動的調整は無効になります。 デフォルトの条件は実装定義です。

例:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>クロスリファレンス

- [パラレル領域](2-directives.md#23-parallel-construct)
- [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)機能

## <a name="44-omp_nested"></a><a name="44-omp_nested"></a>4.4 OMP_NESTED

環境変数`OMP_NESTED`は、ライブラリ ルーチンを呼び出すことによって、入れ子になった並列処理を有効または無効にしない`omp_set_nested`限り、入れ子になった並列処理を有効または無効にします。 に`OMP_NESTED`設定`TRUE`されている場合、ネストされた並列処理は有効になります。 に`OMP_NESTED`設定`FALSE`されている場合、ネストされた並列処理は無効になります。 既定値は `FALSE` です。

例:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>クロスリファレンス

- [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function)機能
