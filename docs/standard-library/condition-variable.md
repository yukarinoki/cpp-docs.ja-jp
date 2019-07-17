---
title: '&lt;condition_variable&gt;'
ms.date: 11/04/2016
f1_keywords:
- <condition_variable>
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
ms.openlocfilehash: ed98966f651df76078fa47b05f5a2d8ae1b71d05
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244574"
---
# <a name="ltconditionvariablegt"></a>&lt;condition_variable&gt;

条件が true になるまで待機するオブジェクトを作成するために使用される、[condition_variable](../standard-library/condition-variable-class.md) クラスと [condition_variable_any](../standard-library/condition-variable-any-class.md) クラスを定義します。

このヘッダーではコンカレンシー ランタイム (ConcRT) が使用されます。これにより、このヘッダーを他の ConcRT メカニズムと共に使用できます。 ConcRT の詳細については、「[コンカレンシー ランタイム](../parallel/concrt/concurrency-runtime.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<condition_variable >

**名前空間:** std

> [!NOTE]
> 使用してコンパイルされたコードで **/clr**、このヘッダーはブロックされます。

### <a name="remarks"></a>Remarks

条件変数を待機するコードでは `mutex` を使用する必要もあります。 呼び出しスレッドは、条件変数を待機する関数を呼び出す前に、`mutex` をロックする必要があります。 呼び出された関数が戻ると、`mutex` はロックされます。 条件が true になるまでスレッドが待機している間は、`mutex` はロックされません。 予測できない結果にならないように、条件変数を待機する各スレッドでは同じ `mutex` オブジェクトを使用する必要があります。

`condition_variable_any` 型のオブジェクトはどの型のミューテックスでも使用できます。 使用されるミューテックス型で `try_lock` メソッドを指定する必要はありません。 `condition_variable` 型のオブジェクトは `unique_lock<mutex>` 型のミューテックスでのみ使用できます。 この型のオブジェクトは `condition_variable_any<unique_lock<mutex>>` 型のオブジェクトより高速になる可能性があります。

イベントを待機するには、まず、ミューテックスをロックしてから、条件変数で `wait` メソッドのいずれかを呼び出します。 別のスレッドが条件変数を通知するまで、`wait` 呼び出しはブロックされます。

条件変数を待機しているスレッドが適切な通知なしでブロック解除された場合、*誤ったウェイクアップ*が発生します。 このような誤ったウェイクアップを認識するには、条件が true になるまで待機するコードで、wait 関数からコードが返されたときにその条件を明示的に確認する必要があります。 これは通常、ループを使用して行われます。`wait(unique_lock<mutex>& lock, Predicate pred)` を使用すれば、このループを自動的に実行することができます。

```cpp
while (condition is false)
    wait for condition variable;
```

`condition_variable_any` と `condition_variable` クラスにはそれぞれ、条件を待機する次の 3 つのメソッドがあります。

- `wait` は無制限に待機します。

- `wait_until` は指定された `time` まで待機します。

- `wait_for` は指定された `time interval` の間待機します。

これらのメソッドにはそれぞれ 2 つのオーバーロード バージョンがあります。 1 つは待機するだけで、誤ってウェークアップする可能性があります。 もう 1 つは、述語を定義する追加のテンプレート引数を受け取ります。 述語になるまでは、メソッドが返されません**true**します。

各クラスの状態にある条件変数を通知に使用される 2 つのメソッドもあります**true**します。

- `notify_one` は、条件変数を待機しているスレッドの 1 つをウェイクアップします。

- `notify_all` は、条件変数を待機しているすべてのスレッドをウェイクアップします。

## <a name="functions-and-enums"></a>関数と列挙型

```cpp
void notify_all_at_thread_exit(condition_variable& cond, unique_lock<mutex> lk);

enum class cv_status { no_timeout, timeout };
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[condition_variable クラス](../standard-library/condition-variable-class.md)<br/>
[condition_variable_any クラス](../standard-library/condition-variable-any-class.md)<br/>
