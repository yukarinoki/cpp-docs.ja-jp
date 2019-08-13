---
title: 省略可能なクラス
ms.date: 11/04/2016
f1_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
helpviewer_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
ms.openlocfilehash: f664df6493a7ee20361d49531a930aeb810d3d2a
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957156"
---
# <a name="optional-class"></a>省略可能なクラス

このテンプレートクラス`optional<T>`は、格納されている*値*と呼ばれる型`T`の値を格納または格納できないオブジェクトを表します。

の`optional<T>`インスタンスに値が含まれている場合、格納されている値は`optional` 、オブジェクトのストレージ内で、型`T`に対して適切に配置された領域内に割り当てられます。 がに変換される`bool`と、オブジェクトに`true`値が`false`含まれている場合は結果がになります。それ以外の場合はが返されます。 `optional<T>`

含まれている`T`オブジェクト型を[in_place_t](in-place-t-struct.md)または[nullopt_t](nullopt-t-structure.md)にすることはできません。 `T`*破棄可能な*である必要があります。つまり、デストラクターは所有されているすべてのリソースを解放する必要があり、例外をスローしないことがあります。

クラス`optional`は c++ 17 で新しく追加されたものです。

## <a name="syntax"></a>構文

```cpp
template <class T>
class optional
{
    using value_type = T;
};

template<class T> optional(T) -> optional<T>;
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|||
|-|-|
| **コンストラクターとデストラクター** | |
|[optional](#optional) | `optional` 型のオブジェクトを構築します。 |
|[~ 省略可能](#optional-destructor) | 型`optional`のオブジェクトを破棄します。 |
| **代入** | |
| [operator=](#op_eq) | を`optional` 別`optional`ののコピーで置き換えます。 |
| [emplace](#op_eq) | 引数を指定して、格納されている値を初期化します。 |
| **Swap** | |
| [swap](#swap) | 格納されている値または空の`optional`状態を別のに交換します。 |
| **オブザーバー** | |
| [has_value](#has_value) | オブジェクトに`optional`値が含まれているかどうかを返します。 |
| [value](#value) | 格納されている値を返します。 |
| [value_or](#value_or) | 含まれている値を返します。値が存在しない場合は、代替のを返します。 |
| [operator->](#op_as) | `optional`オブジェクトの格納されている値を参照します。 |
| [operator*](#op_mem) | `optional`オブジェクトの格納されている値を参照します。 |
| [operator bool](#op_bool) | オブジェクトに`optional`値が含まれているかどうかを返します。 |
| **修飾子** | |
| [reset](#reset) | 格納さ`optional`れている値をすべて破棄することによって、をリセットします。 |

## <a name="has_value"></a>has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional"></a>省略可能なコンストラクター

`optional` 型のオブジェクトを構築します。

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t nullopt) noexcept;
constexpr optional(const optional& rhs);
constexpr optional(optional&& rhs) noexcept;

template <class... Args>
constexpr explicit optional(in_place_t, Args&&... args);

template <class U, class... Args>
constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);

template <class U = T>
explicit constexpr optional(U&& rhs);

template <class U>
explicit optional(const optional<U>& rhs);

template <class U>
explicit optional(optional<U>&& rhs);
```

### <a name="parameters"></a>パラメーター

*rhs*\
格納されている値をコピーまたは移動する。`optional`

*i_list*\
格納されている値を構築する初期化子リスト。

*value*\
格納されている値を構築する引数リスト。

### <a name="remarks"></a>Remarks

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;`これらのコンストラクターは`optional` 、値を含まないを構築します。

`constexpr optional(const optional& rhs);`コピーコンストラクターは、引数の格納されている値から、格納されている値を初期化します。 が true の場合を除き`is_copy_constructible_v<T>` 、**削除済み**として定義さ`is_trivially_copy_constructible_v<T>`れており、が true の場合は簡単です。

`constexpr optional(optional&& rhs) noexcept;`移動コンストラクターは、引数の格納されている値から移動して、格納されている値を初期化します。 が true である場合を除い`is_move_constructible_v<T>`て、オーバーロードの解決には関与`is_trivially_move_constructible_v<T>`しません。が true の場合、簡単です。

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);`引数`std::forward<Args>(args)`を使用する場合と同様に、格納されている値を直接初期化します。 このコンストラクターは`constexpr` 、 `T`使用する`constexpr`コンストラクターがである場合にです。 が true でない限り`is_constructible_v<T, Args...>` 、オーバーロードの解決には関与しません。

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);`引数`i_list, std::forward<Args>(args)`を使用する場合と同様に、格納されている値を直接初期化します。 このコンストラクターは`constexpr` 、 `T`使用する`constexpr`コンストラクターがである場合にです。 が true でない限り`is_constructible_v<T, initializer_list<U>&, Args&&...>` 、オーバーロードの解決には関与しません。

`template <class U = T> explicit constexpr optional(U&& rhs);`直接を使用する`std::forward<U>(v)`場合と同様に、格納されている値を初期化します。 このコンストラクターは`constexpr` 、 `T`使用する`constexpr`コンストラクターがである場合にです。 が true `is_constructible_v<T, U&&>` `is_same_v<remove_cvref_t<U>, optional>`で、 `is_same_v<remove_cvref_t<U>, in_place_t>` and が false でない限り、オーバーロードの解決には関与しません。

`template <class U> explicit optional(const optional<U>& rhs);`*Rhs*に値が含まれている場合は、引数の格納されている値から、格納されている値を直接初期化します。 `is_constructible_v<T, const U&>`が trueで`is_convertible_v<optional<U>&&, T>`はなく`is_convertible_v<const optional<U>&&, T>` 、、、、、、、 、およびがすべてfalseである場合を除き、オーバーロードの解決には関与しません。`is_convertible_v<const optional<U>&, T>` `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>`

`template <class U> explicit optional(optional<U>&& rhs);`*Rhs*に値が含まれている場合は、を使用`std::move(*rhs)`しているかのように、格納されている値を直接初期化します `is_constructible_v<T, U&&>`が trueで`is_convertible_v<optional<U>&&, T>`はなく`is_convertible_v<const optional<U>&&, T>` 、、、、、、、 、およびがすべてfalseである場合を除き、オーバーロードの解決には関与しません。`is_convertible_v<const optional<U>&, T>` `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>`

## <a name="optional-destructor"></a>~ 省略可能なデストラクター

非普通の破棄可能なに含まれている値が存在する場合は、そのデストラクターを呼び出して破棄します。

```cpp
~optional();
```

### <a name="remarks"></a>Remarks

が`T` 普通`optional<T>`で破棄可能なの場合、も普通の破棄可能なです。

## <a name="op_eq"></a>operator =

の`optional`格納されている値を、格納されて`optional`いる別の値からコピーまたは移動して置換します。

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional& rhs);
optional& operator=(optional&&) noexcept( /* see below */ );

template <class U = T>
    optional& operator=(U&&);

template <class U>
optional& operator=(const optional<U>&);

template <class U>
    optional& operator=(optional<U>&&);

template <class... Args>
T& emplace(Args&&...);

template <class U, class... Args>
T& emplace(initializer_list<U>, Args&&...);
```

## <a name="op_as"></a>演算子->

`optional`オブジェクトの格納されている値を逆参照します。

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="op_mem"></a>operator

`optional`オブジェクトの格納されている値を逆参照します。

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="op_bool"></a>bool 演算子

オブジェクトに格納`optional`されている値があるかどうかを報告します。

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a>解除

実質的に、は、含まれているオブジェクトのデストラクターを呼び出し、初期化されていない状態に設定します。

```cpp
void reset() noexcept;
```

## <a name="swap"></a>フォト

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a>数値

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a>value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>関連項目

[\<オプション >](optional.md)
