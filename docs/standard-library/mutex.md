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
ms.openlocfilehash: 9cd4f968543ff777b9178c8f6fa6b3c1699ee465
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965657"
---
# <a name="ltmutexgt"></a>&lt;mutex&gt;

標準ヘッダー \<mutex> をインクルードすることにより、クラス `mutex`、`recursive_mutex`、`timed_mutex`、`recursive_timed_mutex`、テンプレート `lock_guard` および `unique_lock`、相互排他コード領域を定義するためサポートしている型と関数を定義します。

> [!WARNING]
> Visual Studio 2015 以降では、C++ 標準ライブラリ同期型は、は Windows 同期プリミティブに基づいており、(ターゲット プラットフォームが Windows XP の場合を除き、ConcRT を使用できなくします。 \<mutex> で定義されている型は、ConcRT 型または関数には使用しないでください。

## <a name="syntax"></a>構文

```cpp
#include <mutex>
```

## <a name="remarks"></a>Remarks

> [!NOTE]
> 使用してコンパイルされたコードで **/clr**、このヘッダーはブロックされます。

クラス `mutex` と`recursive_mutex` は *mutex 型*です。 mutex 型には、既定のコンストラクターとデストラクターがあり、例外をスローしません。 これらのオブジェクトには、同じオブジェクトをロックしようとしている複数のスレッドがある場合に相互排他するためのメソッドがあります。 具体的には、mutex 型にはメソッド `lock`、`try_lock`、および`unlock` が含まれます。

- `lock` メソッドは、スレッドがミューテックスの所有権を得るまでそのスレッドの呼び出しをブロックします。 その戻り値は無視されます。

- `try_lock` メソッドは、ミューテックスをブロックせずに所有権を取得しようとします。 戻り値の型に変換できる**bool**は**true**メソッドは、所有権を取得しますが、それ以外の場合は、場合**false**します。

- `unlock` メソッドは、呼び出し元のスレッドからミューテックスの所有権を解放します。

型の引数として mutex 型を使用すると、テンプレート `lock_guard` と `unique_lock` をインスタンス化できます。 これらの型のオブジェクトを `Lock` 引数として使用すると、テンプレート [condition_variable_any](../standard-library/condition-variable-any-class.md) でメンバー関数を待機できます。

*timed mutex type* は mutex 型の要件を満たします。 さらは、`try_lock_for`と`try_lock_until`メソッドを 1 つの引数を使用して呼び出し可能である必要がありますに変換できる型を返す必要があります**bool**します。 timed mutex 型では、追加の引数を使用してこれらの関数を定義できます (追加の引数すべてに既定値があることが条件)。

- `try_lock_for` メソッドは、型が [chrono::duration](../standard-library/duration-class.md) でインスタンス化されている 1 つの引数 `Rel_time` を使用して呼び出し可能である必要があります。 メソッドはミューテックスの所有権を取得しようとしますが、取得できたかどうかに関係なく、`Rel_time` で指定された時間内に値が返されます。 戻り値に変換**true**メソッドが所有権を取得した場合、それ以外の場合、戻り値に変換**false**します。

- `try_lock_until` メソッドは、型が [chrono::time_point](../standard-library/time-point-class.md) でインスタンス化されている引数 `Abs_time` を使用して呼び出し可能である必要があります。 メソッドはミューテックスの所有権を取得しようとしますが、取得できたかどうかに関係なく、`Abs_time` で指定された時間内に値が返されます。 戻り値に変換**true**メソッドが所有権を取得した場合、それ以外の場合、戻り値に変換**false**します。

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

|name|説明|
|----------|-----------------|
|[adopt_lock_t 構造体](../standard-library/adopt-lock-t-structure.md)|`adopt_lock` の定義に使用する型を表します。|
|[defer_lock_t 構造体](../standard-library/defer-lock-t-structure.md)|`unique_lock` のオーバーロード コンストラクターの 1 つを選択するために使用される、`defer_lock` オブジェクトを定義する型を表します。|
|[once_flag 構造体](../standard-library/once-flag-structure.md)|表す、**構造体**テンプレート関数で使用されている`call_once`ように初期化するコードは 1 回だけ呼び出す、複数の実行スレッドがある場合でもです。|
|[try_to_lock_t 構造体](../standard-library/try-to-lock-t-structure.md)|表す、**構造体**を定義する、`try_to_lock`オブジェクトし、のオーバー ロードされたコンス トラクターのいずれかを選択するために使用`unique_lock`します。|

### <a name="variables"></a>変数

|name|説明|
|----------|-----------------|
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|`lock_guard` と `unique_lock` のコンストラクターに渡されるオブジェクを表し、同じコンストラクターに渡されるミューテックス オブジェクトがロックされていることを示します。|
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|`unique_lock` のコンストラクターに渡すことのできるオブジェクトを表し、コンストラクターがそれに渡されるミューテックス オブジェクトをロックしないことを示しています。|
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|`unique_lock` のコンストラクターに渡すことのできるオブジェクトを表し、ブロックされずに渡される `mutex` をコンストラクターがロック解除しようとすることを示します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
