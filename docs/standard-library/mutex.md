---
title: '&lt;mutex&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <mutex>
dev_langs:
- C++
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2c58f32847084407d19afea8f2946f8b3041efa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltmutexgt"></a>&lt;mutex&gt;

標準ヘッダー \<mutex> をインクルードすることにより、クラス `mutex`、`recursive_mutex`、`timed_mutex`、`recursive_timed_mutex`、テンプレート `lock_guard` および `unique_lock`、相互排他コード領域を定義するためサポートしている型と関数を定義します。

> [!WARNING]
> Visual Studio 2015 以降では、C++ 標準ライブラリの同期型は Windows 同期プリミティブに基づいており、不要になった (ターゲット プラットフォームが Windows XP の場合) を除く ConcRT を使用します。 \<mutex> で定義されている型は、ConcRT 型または関数には使用しないでください。

## <a name="syntax"></a>構文

```cpp
#include <mutex>
```

## <a name="remarks"></a>コメント

> [!NOTE]
> 使用してコンパイルされたコードで **/clr**、このヘッダーはブロックされます。

クラス `mutex` と`recursive_mutex` は *mutex 型*です。 mutex 型には、既定のコンストラクターとデストラクターがあり、例外をスローしません。 これらのオブジェクトには、同じオブジェクトをロックしようとしている複数のスレッドがある場合に相互排他するためのメソッドがあります。 具体的には、mutex 型にはメソッド `lock`、`try_lock`、および`unlock` が含まれます。

- `lock` メソッドは、スレッドがミューテックスの所有権を得るまでそのスレッドの呼び出しをブロックします。 その戻り値は無視されます。

- `try_lock` メソッドは、ミューテックスをブロックせずに所有権を取得しようとします。 その戻り値の型は、`bool` に変換でき、メソッドが所有権を得ると `true` になりますが、それ以外の場合は `false` です。

- `unlock` メソッドは、呼び出し元のスレッドからミューテックスの所有権を解放します。

型の引数として mutex 型を使用すると、テンプレート `lock_guard` と `unique_lock` をインスタンス化できます。 これらの型のオブジェクトを `Lock` 引数として使用すると、テンプレート [condition_variable_any](../standard-library/condition-variable-any-class.md) でメンバー関数を待機できます。

*timed mutex type* は mutex 型の要件を満たします。 また、呼び出しには 1 つの引数を使用し、`bool` に変換可能な型を返す `try_lock_for` メソッドと `try_lock_until` メソッドがあります。 timed mutex 型では、追加の引数を使用してこれらの関数を定義できます (追加の引数すべてに既定値があることが条件)。

- `try_lock_for` メソッドは、型が [chrono::duration](../standard-library/duration-class.md) でインスタンス化されている 1 つの引数 `Rel_time` を使用して呼び出し可能である必要があります。 メソッドはミューテックスの所有権を取得しようとしますが、取得できたかどうかに関係なく、`Rel_time` で指定された時間内に値が返されます。 メソッドが所有権を取得した場合は戻り値が `true` に変換されますが、取得していない場合は `false` に変換されます。

- `try_lock_until` メソッドは、型が [chrono::time_point](../standard-library/time-point-class.md) でインスタンス化されている引数 `Abs_time` を使用して呼び出し可能である必要があります。 メソッドはミューテックスの所有権を取得しようとしますが、取得できたかどうかに関係なく、`Abs_time` で指定された時間内に値が返されます。 メソッドが所有権を取得した場合は戻り値が `true` に変換されますが、取得していない場合は `false` に変換されます。

mutex 型は *lockable 型*とも呼ばれます。 メンバー関数 `try_lock` が提供されない場合は、*basic lockable 型*になります。 timed mutex 型は *timed lockable 型*とも呼ばれます。

### <a name="classes"></a>クラス

|名前|説明|
|----------|-----------------|
|[lock_guard クラス](../standard-library/lock-guard-class.md)|オブジェクトを作成し、そのデストラクタ―が `mutex` のロックを解除するためにインスタンス化できるテンプレートを表します。|
|[mutex クラス (C++ 標準ライブラリ)](../standard-library/mutex-class-stl.md)|mutex 型を表します。 この型のオブジェクトを使用して、プログラム内で相互排他を適用します。|
|[recursive_mutex クラス](../standard-library/recursive-mutex-class.md)|mutex 型を表します。 `mutex` クラスとは異なり、既にロックされているオブジェクトのロック メソッドを呼び出す動作は詳細に定義されています。|
|[recursive_timed_mutex クラス](../standard-library/recursive-timed-mutex-class.md)|timed mutex 型を表します。 この型のオブジェクトを使用して、プログラム内で時間制限ブロックのある相互排他を適用します。 `timed_mutex` 型のオブジェクトとは異なり、`recursive_timed_mutex` オブジェクトにロック メソッドを呼び出すことによる影響は詳細に定義されています。|
|[timed_mutex クラス](../standard-library/timed-mutex-class.md)|timed mutex 型を表します。 この型のオブジェクトを使用して、プログラム内で時間制限ブロックのある相互排他を適用します。|
|[unique_lock クラス](../standard-library/unique-lock-class.md)|`mutex` のロックとロック解除を管理するオブジェクトを作成するためにインスタンス化できるテンプレートを表します。|

### <a name="functions"></a>関数

|名前|説明|
|----------|-----------------|
|[call_once](../standard-library/mutex-functions.md#call_once)|指定された呼び出し可能オブジェクトが、実行中に 1 回だけ呼び出されるメカニズムを提供します。|
|[lock](../standard-library/mutex-functions.md#lock)|デッドロックなしですべての引数をロックしようとします。|

### <a name="structs"></a>構造体

|名前|説明|
|----------|-----------------|
|[adopt_lock_t 構造体](../standard-library/adopt-lock-t-structure.md)|`adopt_lock` の定義に使用する型を表します。|
|[defer_lock_t 構造体](../standard-library/defer-lock-t-structure.md)|`unique_lock` のオーバーロード コンストラクターの 1 つを選択するために使用される、`defer_lock` オブジェクトを定義する型を表します。|
|[once_flag 構造体](../standard-library/once-flag-structure.md)|テンプレート関数 `call_once` で使用する `struct` を表し、実行する複数スレッドがある場合でも、初期化コードが 1 回だけ呼び出されるようにします。|
|[try_to_lock_t 構造体](../standard-library/try-to-lock-t-structure.md)|`unique_lock` のオーバーロード コンストラクターの 1 つを選択するために使用される、`try_to_lock` オブジェクトを定義する `struct` を表し ます。|

### <a name="variables"></a>変数

|名前|説明|
|----------|-----------------|
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|`lock_guard` と `unique_lock` のコンストラクターに渡されるオブジェクを表し、同じコンストラクターに渡されるミューテックス オブジェクトがロックされていることを示します。|
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|`unique_lock` のコンストラクターに渡すことのできるオブジェクトを表し、コンストラクターがそれに渡されるミューテックス オブジェクトをロックしないことを示しています。|
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|`unique_lock` のコンストラクターに渡すことのできるオブジェクトを表し、ブロックされずに渡される `mutex` をコンストラクターがロック解除しようとすることを示します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
