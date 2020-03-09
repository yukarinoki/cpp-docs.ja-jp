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
ms.openlocfilehash: 5435c3b9e10f151fc77c72b58c93510b6a867ce1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865176"
---
# <a name="ltfuturegt-functions"></a>&lt;future&gt; 関数

||||
|-|-|-|
|[async](#async)|[future_category](#future_category)|[make_error_code](#make_error_code)|
|[make_error_condition](#make_error_condition)|[swap](#swap)|

## <a name="async"></a>  async

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

### <a name="remarks"></a>コメント

省略形の定義:

|||
|-|-|
|*dfn*|`decay_copy(forward<Fn>(fn))` の呼び出しの結果。|
|*dargs*|`decay_copy(forward<ArgsTypes>(args...))` の呼び出しの結果。|
|*Ty*|型 `result_of<Fn(ArgTypes...)>::type`。|

1 番目のテンプレート関数は、`async(launch::any, fn, args...)` を返します。

2 番目の関数は `future<Ty>` オブジェクトを返し、その*関連付けられた非同期状態*は、結果、*dfn* および *dargs* の値、実行の個別のスレッドを管理するためのスレッド オブジェクトを保持します。

`decay<Fn>::type` が launch 以外の型でない限り、2 番目の関数はオーバーロードの解決に関与しません。

標準C++では、ポリシーが launch:: async の場合、関数は新しいスレッドを作成します。 ただし、Microsoft の実装は現在、準拠していません。 Windows ThreadPool からスレッドを取得します。この場合、新しいスレッドではなくリサイクルスレッドが提供されることがあります。 つまり、`launch::async` ポリシーは実際には `launch::async|launch::deferred`として実装されます。  ThreadPool ベースの実装のもう1つの意味は、スレッドが完了したときにスレッドローカル変数が破棄される保証がないことです。 スレッドがリサイクルされ、`async`への新しい呼び出しに渡された場合、古い変数は引き続き存在します。 このため、`async`でスレッドローカル変数を使用しないことをお勧めします。

*ポリシー*が `launch::deferred`場合、関数は、関連付けられた非同期状態を*遅延関数*の保持としてマークし、を返します。 関連付けられた非同期状態が実際に準備完了になるまで待機する、時間指定のない関数への初めての呼び出しでは、`INVOKE(dfn, dargs..., Ty)` を評価することによって遅延関数が呼び出されます。

いずれの場合も、`future` オブジェクトの関連付けられた非同期状態は、 *の評価が完了するまでは、例外がスローされても正常に制御が戻っても、* ready`INVOKE(dfn, dargs..., Ty)` には設定されません。 関連付けられた非同期状態の結果は、例外がスローされた場合の例外か、評価から返された値です。

> [!NOTE]
> `future` で開始されたタスクにアタッチされた [ (または最後の ](../standard-library/shared-future-class.md)shared_future`std::async`) の場合、タスクが完了していないと、デストラクターがブロックします。つまり、スレッドがまだ `.get()` または `.wait()` を呼び出しておらず、タスクがまだ実行中の場合、デストラクターによってブロックされます。 `future` から取得された `std::async` がローカル スコープ外に移動される場合、それを使う他のコードでは、共有状態が準備完了になることをデストラクターがブロックする場合があることに注意する必要があります。

擬似関数 `INVOKE` は [\<functional>](../standard-library/functional.md) で定義されています。

## <a name="future_category"></a>  future_category

[ オブジェクトに関連するエラーの特性を設定する ](../standard-library/error-category-class.md)error_category`future` オブジェクトへの参照を返します。

```cpp
const error_category& future_category() noexcept;
```

## <a name="make_error_code"></a>  make_error_code

[future](../standard-library/error-code-class.md) エラーを特徴付ける [error_category](../standard-library/error-category-class.md) オブジェクトと共に、[error_code](../standard-library/future-class.md) を作成します。

```cpp
inline error_code make_error_code(future_errc Errno) noexcept;
```

### <a name="parameters"></a>パラメーター

*Errno*\
報告されたエラーを識別する [future_errc](../standard-library/future-enums.md#future_errc) の値。

### <a name="return-value"></a>戻り値

`error_code(static_cast<int>(Errno), future_category());`

## <a name="make_error_condition"></a>  make_error_condition

[future](../standard-library/error-condition-class.md) エラーを特徴付ける [error_category](../standard-library/error-category-class.md) オブジェクトと共に、[error_condition](../standard-library/future-class.md) を作成します。

```cpp
inline error_condition make_error_condition(future_errc Errno) noexcept;
```

### <a name="parameters"></a>パラメーター

*Errno*\
報告されたエラーを識別する [future_errc](../standard-library/future-enums.md#future_errc) の値。

### <a name="return-value"></a>戻り値

`error_condition(static_cast<int>(Errno), future_category());`

## <a name="swap"></a>  swap

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

*右*\
右側の `promise` オブジェクト。

## <a name="see-also"></a>参照

[\<future>](../standard-library/future.md)
