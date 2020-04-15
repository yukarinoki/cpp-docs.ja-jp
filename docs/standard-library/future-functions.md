---
title: '&lt;future&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- future/std::async
- future/std::future_category
- future/std::make_error_code
- future/std::make_error_condition
- future/std::swap
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
helpviewer_keywords:
- std::async [C++]
- std::future_category [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::swap [C++]
ms.openlocfilehash: 16c26212cac13602e981f42d8333518da90615fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370672"
---
# <a name="ltfuturegt-functions"></a>&lt;future&gt; 関数

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[スワップ](#swap)|

## <a name="async"></a><a name="async"></a>非同期

*非同期プロバイダー*を表します。

```cpp
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```

### <a name="parameters"></a>パラメーター

*ポリシー*\
[launch](../standard-library/future-enums.md#launch) の値。

### <a name="remarks"></a>解説

省略形の定義:

|||
|-|-|
|*Dfn*|`decay_copy(forward<Fn>(fn))` の呼び出しの結果。|
|*dargs*|`decay_copy(forward<ArgsTypes>(args...))` の呼び出しの結果。|
|*Ty*|型 `result_of<Fn(ArgTypes...)>::type`。|

1 番目のテンプレート関数は、`async(launch::any, fn, args...)` を返します。

2 番目の関数は `future<Ty>` オブジェクトを返し、その*関連付けられた非同期状態*は、結果、*dfn* および *dargs* の値、実行の個別のスレッドを管理するためのスレッド オブジェクトを保持します。

`decay<Fn>::type` が launch 以外の型でない限り、2 番目の関数はオーバーロードの解決に関与しません。

C++ 標準では、ポリシーが起動されると::async、関数は新しいスレッドを作成すると述べています。 ただし、マイクロソフトの実装は現在準拠していません。 Windows スレッド プールからスレッドを取得しますが、場合によっては、新しいスレッドではなくリサイクルされたスレッドを提供する場合があります。 これは、`launch::async`ポリシーが実際に`launch::async|launch::deferred`として実装されていることを意味します。  ThreadPool ベースの実装のもう 1 つの意味は、スレッドが完了したときにスレッド ローカル変数が破棄される保証が存在しないということです。 スレッドがリサイクルされ、 への新しい呼び出し`async`に提供された場合、古い変数は存在します。 したがって、スレッド ローカル変数は 使用`async`しないことをお勧めします。

*policy*が`launch::deferred`の場合、関数は、関連付けられた非同期状態を*保留としてマークし、遅延関数*を返します。 関連付けられた非同期状態が実際に準備完了になるまで待機する、時間指定のない関数への初めての呼び出しでは、`INVOKE(dfn, dargs..., Ty)` を評価することによって遅延関数が呼び出されます。

いずれの場合も、`future` オブジェクトの関連付けられた非同期状態は、`INVOKE(dfn, dargs..., Ty)` の評価が完了するまでは、例外がスローされても正常に制御が戻っても、*ready* には設定されません。 関連付けられた非同期状態の結果は、例外がスローされた場合の例外か、評価から返された値です。

> [!NOTE]
> `std::async` で開始されたタスクにアタッチされた `future` (または最後の [shared_future](../standard-library/shared-future-class.md)) の場合、タスクが完了していないと、デストラクターがブロックします。つまり、スレッドがまだ `.get()` または `.wait()` を呼び出しておらず、タスクがまだ実行中の場合、デストラクターによってブロックされます。 `future` から取得された `std::async` がローカル スコープ外に移動される場合、それを使う他のコードでは、共有状態が準備完了になることをデストラクターがブロックする場合があることに注意する必要があります。

擬似関数`INVOKE`は[\<、 機能>](../standard-library/functional.md)で定義されます。

## <a name="future_category"></a><a name="future_category"></a>future_category

`future` オブジェクトに関連するエラーの特性を設定する [error_category](../standard-library/error-category-class.md) オブジェクトへの参照を返します。

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a><a name="make_error_code"></a>make_error_code

[future](../standard-library/future-class.md) エラーを特徴付ける [error_category](../standard-library/error-category-class.md) オブジェクトと共に、[error_code](../standard-library/error-code-class.md) を作成します。

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>パラメーター

*Errno*\
報告されたエラーを識別する [future_errc](../standard-library/future-enums.md#future_errc) の値。

### <a name="return-value"></a>戻り値

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a><a name="make_error_condition"></a>make_error_condition

[future](../standard-library/future-class.md) エラーを特徴付ける [error_category](../standard-library/error-category-class.md) オブジェクトと共に、[error_condition](../standard-library/error-condition-class.md) を作成します。

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>パラメーター

*Errno*\
報告されたエラーを識別する [future_errc](../standard-library/future-enums.md#future_errc) の値。

### <a name="return-value"></a>戻り値

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a><a name="swap"></a>スワップ

*関連付けられた非同期状態*を、`promise` オブジェクト間で交換します。

```cpp
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```

### <a name="parameters"></a>パラメーター

*左*\
左側の `promise` オブジェクト。

*そうです*\
右側の `promise` オブジェクト。

## <a name="see-also"></a>関連項目

[\<将来の>](../standard-library/future.md)
