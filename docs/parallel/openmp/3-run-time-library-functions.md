---
title: 3. ランタイム ライブラリの関数
ms.date: 05/13/2019
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: 767c006b0a2d81af4d1f8f2e23f84d7847326f31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370283"
---
# <a name="3-run-time-library-functions"></a>3. ランタイムライブラリ関数

このセクションでは、OpenMP C および C++ ランタイム ライブラリ関数について説明します。 ヘッダー ** \<omp.h>** は、並列実行環境の制御と照会に使用できるいくつかの関数、およびデータへのアクセスを同期するために使用できるロック関数の 2 つの型を宣言します。

型`omp_lock_t`は、ロックが使用可能であることを表すオブジェクト型、またはスレッドがロックを所有していることを表すオブジェクト型です。 これらのロックは、*単純なロック*と呼ばれます。

型`omp_nest_lock_t`は、ロックが使用可能であるか、またはロックを所有するスレッドの ID と*入れ子のカウント*(後述) の両方を表すことができるオブジェクト型です。 これらのロックは *、ネスト可能ロック*と呼ばれます。

ライブラリ関数は"C"リンケージを持つ外部関数です。

この章の説明は、次のトピックに分かれています。

- [実行環境関数](#31-execution-environment-functions)
- [ロック機能](#32-lock-functions)
- [タイミング ルーチン](#33-timing-routines)

## <a name="31-execution-environment-functions"></a>3.1 実行環境関数

このセクションで説明する機能は、スレッド、プロセッサー、および並列環境に影響を与え、モニターします。

- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_get_max_threads](#313-omp_get_max_threads-function)
- [omp_get_thread_num](#314-omp_get_thread_num-function)
- [omp_get_num_procs](#315-omp_get_num_procs-function)
- [omp_in_parallel](#316-omp_in_parallel-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [omp_get_dynamic](#318-omp_get_dynamic-function)
- [omp_set_nested](#319-omp_set_nested-function)
- [omp_get_nested](#3110-omp_get_nested-function)

### <a name="311-omp_set_num_threads-function"></a><a name="311-omp_set_num_threads-function"></a>3.1.1 omp_set_num_threads機能

この`omp_set_num_threads`関数は、句を指定しない後の並列領域で使用するスレッドの既定の数を`num_threads`設定します。 その形式は次のとおりです。

```cpp
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

パラメーター *num_threads*の値は正の整数である必要があります。 その効果は、スレッド数の動的調整が有効かどうかによって異なります。 関数とスレッドの動的調整の相互作用に関する包括的なルールについては、[セクション 2.3](2-directives.md#23-parallel-construct)を参照してください。 `omp_set_num_threads`

この関数は、関数がゼロを返すプログラムの一部から呼び`omp_in_parallel`出された場合に、上記の効果を持ちます。 `omp_in_parallel`関数が 0 以外の値を返すプログラムの一部から呼び出された場合、この関数の動作は未定義です。

この呼び出しは環境変数`OMP_NUM_THREADS`よりも優先されます。 スレッド数の既定値は、呼び出`omp_set_num_threads`しまたは`OMP_NUM_THREADS`環境変数の設定によって確立される場合があり、`parallel``num_threads`句を指定することで、単一のディレクティブで明示的にオーバーライドできます。

詳細については、「 [omp_set_dynamic](#317-omp_set_dynamic-function)」 を参照してください。

#### <a name="cross-references"></a>クロスリファレンス

- [omp_set_dynamic](#317-omp_set_dynamic-function)機能
- [omp_get_dynamic](#318-omp_get_dynamic-function)機能
- [環境変数OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)条項

### <a name="312-omp_get_num_threads-function"></a><a name="312-omp_get_num_threads-function"></a>3.1.2 omp_get_num_threads機能

この`omp_get_num_threads`関数は、チーム内で現在、呼び出された並列領域を実行しているスレッドの数を返します。 その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_get_num_threads(void);
```

句`num_threads`、`omp_set_num_threads`関数、および`OMP_NUM_THREADS`環境変数は、チーム内のスレッドの数を制御します。

スレッドの数がユーザーによって明示的に設定されていない場合、既定の実装定義です。 この関数は、最も近い囲`parallel`みディレクティブにバインドします。 プログラムのシリアル部分またはシリアル化された入れ子になった並列領域から呼び出された場合、この関数は 1 を返します。

詳細については、「 [omp_set_dynamic](#317-omp_set_dynamic-function)」 を参照してください。

#### <a name="cross-references"></a>クロスリファレンス

- [OMP_NUM_THREADS](4-environment-variables.md#42-omp_num_threads)
- [num_threads](2-directives.md#23-parallel-construct)
- [parallel](2-directives.md#23-parallel-construct)

### <a name="313-omp_get_max_threads-function"></a><a name="313-omp_get_max_threads-function"></a>3.1.3 omp_get_max_threads機能

この`omp_get_max_threads`関数は、コードのその時点で`num_threads`句のない並列領域が見られる場合にチームを形成するために使用されるスレッドの数と少なくとも同じ大きさであることが保証された整数を返します。 その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_get_max_threads(void);
```

次の例は、 の値に対する`omp_get_max_threads`下限を表します。

> *スレッド -次のチームに使用される* <= `omp_get_max_threads`

別の並列領域が特定のスレッド`num_threads`数を要求するためにこの句を使用する場合、結果の下限での`omp_get_max_threads`保証が保持されなくなることに注意してください。

関数`omp_get_max_threads`の戻り値を使用すると、次の並列領域で形成されたチーム内のすべてのスレッドに対して、十分なストレージを動的に割り当てることができます。

#### <a name="cross-references"></a>クロスリファレンス

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [omp_set_num_threads](#311-omp_set_num_threads-function)
- [omp_set_dynamic](#317-omp_set_dynamic-function)
- [num_threads](2-directives.md#23-parallel-construct)

### <a name="314-omp_get_thread_num-function"></a><a name="314-omp_get_thread_num-function"></a>3.1.4 omp_get_thread_num機能

この`omp_get_thread_num`関数は、関数を実行しているスレッドのチーム内のスレッド番号を返します。 スレッド番号は 0 から`omp_get_num_threads()`-1 の間にあります。 チームのマスタースレッドはスレッド 0 です。

その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_get_thread_num(void);
```

シリアル領域から呼び出された`omp_get_thread_num`場合は 0 を返します。 シリアル化された入れ子になった並列領域内から呼び出された場合、この関数は 0 を返します。

#### <a name="cross-references"></a>クロスリファレンス

- [omp_get_num_threads](#312-omp_get_num_threads-function)機能

### <a name="315-omp_get_num_procs-function"></a><a name="315-omp_get_num_procs-function"></a>3.1.5 omp_get_num_procs機能

この`omp_get_num_procs`関数は、関数が呼び出された時点でプログラムが使用できるプロセッサの数を返します。 その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_get_num_procs(void);
```

### <a name="316-omp_in_parallel-function"></a><a name="316-omp_in_parallel-function"></a>3.1.6 omp_in_parallel機能

並列`omp_in_parallel`実行される並列領域の動的範囲内で呼び出された場合、この関数は 0 以外の値を返します。それ以外の場合は 0 を返します。 その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_in_parallel(void);
```

この関数は、並列で実行される領域 (シリアル化された入れ子になった領域を含む) 内から呼び出された場合に、0 以外の値を返します。

### <a name="317-omp_set_dynamic-function"></a><a name="317-omp_set_dynamic-function"></a>3.1.7 omp_set_dynamic機能

この`omp_set_dynamic`関数は、並列領域の実行に使用できるスレッド数の動的調整を有効または無効にします。 その形式は次のとおりです。

```cpp
#include <omp.h>
void omp_set_dynamic(int dynamic_threads);
```

*dynamic_threads*が 0 以外の値に評価される場合、システム リソースを最適に使用するために、実行時環境で、今後の並列領域の実行に使用されるスレッドの数が自動的に調整される可能性があります。 その結果、ユーザーが指定したスレッド数が最大スレッド数になります。 並列領域を実行しているチーム内のスレッドの数は、その並列領域の期間は固定されたままであり、`omp_get_num_threads`関数によって報告されます。

*dynamic_threads*が 0 と評価される場合、動的調整は無効になります。

この関数は、関数がゼロを返すプログラムの一部から呼び`omp_in_parallel`出された場合に、上記の効果を持ちます。 `omp_in_parallel`関数が 0 以外の値を返すプログラムの一部から呼び出された場合、この関数の動作は未定義です。

呼`omp_set_dynamic`び出しは環境変数よりも`OMP_DYNAMIC`優先されます。

スレッドの動的調整のデフォルトは、実装定義です。 その結果、正しい実行のために特定の数のスレッドに依存するユーザー コードは、動的スレッドを明示的に無効にする必要があります。 実装はスレッド数を動的に調整する機能を提供する必要はありませんが、すべてのプラットフォームで移植性をサポートするインターフェイスを提供する必要があります。

#### <a name="microsoft-specific"></a>Microsoft 固有の仕様

現在の`omp_get_dynamic`サポートと`omp_set_dynamic`のサポートは次のとおりです。

入力`omp_set_dynamic`パラメータはスレッド処理ポリシーに影響を与えないので、スレッドの数は変わりません。 `omp_get_num_threads`ユーザー定義番号が設定されている場合は常に、または既定のスレッド番号を返します。 現在の Microsoft の`omp_set_dynamic(0)`実装では、動的スレッドをオフにして、既存のスレッドセットを次の並列領域で再利用できるようにします。 `omp_set_dynamic(1)`既存のスレッドセットを破棄し、今後の並列領域用の新しいセットを作成することにより、動的スレッド処理をオンにします。 新しいセットのスレッド数は、古いセットと同じで、戻り値に基づいています`omp_get_num_threads`。 したがって、最高のパフォーマンスを得`omp_set_dynamic(0)`るために、既存のスレッドを再利用するために使用します。

#### <a name="cross-references"></a>クロスリファレンス

- [omp_get_num_threads](#312-omp_get_num_threads-function)
- [OMP_DYNAMIC](4-environment-variables.md#43-omp_dynamic)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="318-omp_get_dynamic-function"></a><a name="318-omp_get_dynamic-function"></a>3.1.8 omp_get_dynamic機能

この`omp_get_dynamic`関数は、スレッドの動的調整が有効になっている場合は 0 以外の値を返し、それ以外の場合は 0 を返します。 その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_get_dynamic(void);
```

実装がスレッド数の動的調整を実装しない場合、この関数は常に 0 を返します。 詳細については、「 [omp_set_dynamic](#317-omp_set_dynamic-function)」 を参照してください。

#### <a name="cross-references"></a>クロスリファレンス

- 動的スレッド調整の詳細については[、「omp_set_dynamic」](#317-omp_set_dynamic-function)を参照してください。

### <a name="319-omp_set_nested-function"></a><a name="319-omp_set_nested-function"></a>3.1.9 omp_set_nested機能

この`omp_set_nested`関数は、入れ子になった並列処理を有効または無効にします。 その形式は次のとおりです。

```cpp
#include <omp.h>
void omp_set_nested(int nested);
```

*入れ子の*評価が 0 の場合、入れ子になった並列処理は無効になります (既定の状態) 、入れ子になった並列領域は現在のスレッドによってシリアル化され、実行されます。 それ以外の場合は、入れ子になった並列処理が有効になり、入れ子になった並列領域は、入れ子になったチームを形成するために追加のスレッドを配置できます。

この関数は、関数がゼロを返すプログラムの一部から呼び`omp_in_parallel`出された場合に、上記の効果を持ちます。 `omp_in_parallel`関数が 0 以外の値を返すプログラムの一部から呼び出された場合、この関数の動作は未定義です。

この呼び出しは環境変数`OMP_NESTED`よりも優先されます。

入れ子になった並列処理が有効な場合、入れ子になった並列領域の実行に使用されるスレッドの数は、実装によって定義されます。 結果として、OpenMP 準拠の実装は、入れ子になった並列処理が有効な場合でも、入れ子になった並列領域をシリアル化できます。

#### <a name="cross-references"></a>クロスリファレンス

- [OMP_NESTED](4-environment-variables.md#44-omp_nested)
- [omp_in_parallel](#316-omp_in_parallel-function)

### <a name="3110-omp_get_nested-function"></a><a name="3110-omp_get_nested-function"></a>3.1.10 omp_get_nested機能

この`omp_get_nested`関数は、ネストされた並列処理が有効な場合は 0 以外の値を返し、無効になっている場合は 0 を返します。 ネストされた並列処理の詳細については[、「omp_set_nested」](#319-omp_set_nested-function)を参照してください。 その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_get_nested(void);
```

実装が入れ子になった並列処理を実装しない場合、この関数は常に 0 を返します。

## <a name="32-lock-functions"></a>3.2 ロック機能

このセクションで説明する関数は、同期に使用されるロックを操作します。

次の関数の場合、lock 変数は`omp_lock_t`type を持つ必要があります。 この変数は、これらの関数を通じてのみアクセスする必要があります。 すべてのロック関数には、型へのポインターを持つ`omp_lock_t`引数が必要です。

- [omp_init_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions)関数は、単純なロックを初期化します。
- [omp_destroy_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions)関数は、単純なロックを削除します。
- [omp_set_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions)関数は、単純なロックが使用可能になるまで待機します。
- [omp_unset_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions)関数は、単純なロックを解放します。
- [omp_test_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions)関数は、単純なロックをテストします。

次の関数の場合、lock 変数は`omp_nest_lock_t`type を持つ必要があります。  この変数は、これらの関数を通じてのみアクセスする必要があります。 入れ子にできるロック関数はすべて、型へのポインターを`omp_nest_lock_t`持つ引数を必要とします。

- [omp_init_nest_lock](#321-omp_init_lock-and-omp_init_nest_lock-functions)関数は、入れ子にできるロックを初期化します。
- [omp_destroy_nest_lock](#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions)関数は、入れ子にできるロックを削除します。
- [omp_set_nest_lock](#323-omp_set_lock-and-omp_set_nest_lock-functions)関数は、入れ子にできるロックが使用可能になるまで待機します。
- [omp_unset_nest_lock](#324-omp_unset_lock-and-omp_unset_nest_lock-functions)関数は、入れ子にできるロックを解放します。
- [omp_test_nest_lock](#325-omp_test_lock-and-omp_test_nest_lock-functions)関数は、入れ子にできるロックをテストします。

OpenMP ロック関数は、ロック変数の最新の値を常に読み取って更新する方法で、ロック変数にアクセスします。 したがって、OpenMP プログラムに明示的な`flush`ディレクティブを含めて、ロック変数の値が異なるスレッド間で一貫していることを確認する必要はありません。 (他の変数の`flush`値を一致させるディレクティブが必要な場合があります)。

### <a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a><a name="321-omp_init_lock-and-omp_init_nest_lock-functions"></a>3.2.1 omp_init_lockとomp_init_nest_lock関数

これらの関数は、ロックを初期化する唯一の手段を提供します。 各関数は、今後の呼び出しで使用するために、パラメーター ロックに関連付けられた*ロック*を初期化します。 その形式は次のとおりです。

```cpp
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

初期状態はロック解除されます (つまり、ロックを所有するスレッドはありません)。 入れ子にできるロックの場合、初期ネストカウントはゼロです。 既に初期化されているロック変数を使用してこれらのルーチンのいずれかを呼び出すのは非準拠です。

### <a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a><a name="322-omp_destroy_lock-and-omp_destroy_nest_lock-functions"></a>3.2.2 omp_destroy_lock関数とomp_destroy_nest_lock機能

これらの関数は、ロック変数*ロック*を指し示すロックが初期化されていないかどうかを確認します。 その形式は次のとおりです。

```cpp
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

これらのルーチンのいずれかを、初期化されていないロック変数またはロック解除されたロック変数で呼び出すのは非準拠です。

### <a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a><a name="323-omp_set_lock-and-omp_set_nest_lock-functions"></a>3.2.3 omp_set_lock関数とomp_set_nest_lock関数

これらの各関数は、指定されたロックが使用可能になるまで、関数を実行するスレッドをブロックし、ロックを設定します。 ロックが解除されている場合は、シンプルなロックが使用できます。 入れ子にできるロックは、ロックが解除されている場合、または関数を実行しているスレッドによって既に所有されている場合に使用できます。 その形式は次のとおりです。

```cpp
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

単純なロックの場合、関数の引数`omp_set_lock`は初期化されたロック変数を指している必要があります。 ロックの所有権は、関数を実行しているスレッドに付与されます。

入れ子にできるロックの場合、関数`omp_set_nest_lock`の引数は初期化されたロック変数を指している必要があります。 入れ子のカウントがインクリメントされ、スレッドにロックの所有権が付与されるか保持されます。

### <a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a><a name="324-omp_unset_lock-and-omp_unset_nest_lock-functions"></a>3.2.4 omp_unset_lock関数とomp_unset_nest_lock関数

これらの関数は、ロックの所有権を解放する手段を提供します。 その形式は次のとおりです。

```cpp
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

これらの関数の引数は、関数を実行するスレッドが所有する初期化済みロック変数を指している必要があります。 スレッドがそのロックを所有していない場合、動作は未定義です。

単純なロックの場合、`omp_unset_lock`関数は、関数を実行しているスレッドをロックの所有権から解放します。

入れ子可能ロックの場合`omp_unset_nest_lock`、関数はネストカウントを減算し、結果のカウントがゼロの場合は、その関数を実行しているスレッドをロックの所有権から解放します。

### <a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a><a name="325-omp_test_lock-and-omp_test_nest_lock-functions"></a>3.2.5 omp_test_lock関数とomp_test_nest_lock関数

これらの関数は、ロックを設定しようとしますが、スレッドの実行をブロックしません。 その形式は次のとおりです。

```cpp
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

引数は、初期化されたロック変数を指している必要があります。 これらの関数は、`omp_set_lock`と`omp_set_nest_lock`同じ方法でロックを設定しようとしますが、スレッドの実行をブロックしません。

単純なロックの場合、`omp_test_lock`ロックが正常に設定された場合は、関数は 0 以外の値を返します。それ以外の場合は、ゼロを返します。

入れ子にできるロックの`omp_test_nest_lock`場合、この関数は、ロックが正常に設定された場合に、新しい入れ子カウントを返します。それ以外の場合は、ゼロを返します。

## <a name="33-timing-routines"></a>3.3 タイミングルーチン

このセクションで説明する関数は、ポータブルの壁時計タイマーをサポートします。

- [omp_get_wtime](#331-omp_get_wtime-function)関数は、経過した壁時計時間を返します。
- [omp_get_wtick](#332-omp_get_wtick-function)関数は、連続するクロック刻みから秒を返します。

### <a name="331-omp_get_wtime-function"></a><a name="331-omp_get_wtime-function"></a>3.3.1 omp_get_wtime機能

この`omp_get_wtime`関数は、"過去の時間" 以降の経過した壁時計の時間と等しい倍精度浮動小数点値を秒数で返します。  実際の 「過去の時刻」は任意ですが、アプリケーション プログラムの実行中に変更されないことが保証されています。 その形式は次のとおりです。

```cpp
#include <omp.h>
double omp_get_wtime(void);
```

この関数は、次の例に示すように、経過時間を測定するために使用されることを想定しています。

```cpp
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

返される時間はスレッド単位の時間であり、アプリケーションに参加するすべてのスレッドでグローバルに一貫性を持つ必要はありません。

### <a name="332-omp_get_wtick-function"></a><a name="332-omp_get_wtick-function"></a>3.3.2 omp_get_wtick機能

この`omp_get_wtick`関数は、連続するクロック・ティック間の秒数と等しい倍精度浮動小数点値を戻します。 その形式は次のとおりです。

```cpp
#include <omp.h>
double omp_get_wtick(void);
```
