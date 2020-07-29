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
ms.openlocfilehash: 3b8baca48b7b7a32b88079a1668aecdd1c9aca88
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224696"
---
# <a name="optional-class"></a>省略可能なクラス

クラステンプレートは、格納されている `optional<T>` 値と呼ばれる型の値を格納できる場合と、含まれない場合があるオブジェクトを表し `T` ます。 *contained value*

のインスタンスに `optional<T>` 値が含まれている場合、格納されている値は、オブジェクトのストレージ内で `optional` 、型に対して適切に配置された領域内に割り当てられ `T` ます。 `optional<T>`がに変換されると **`bool`** 、 **`true`** オブジェクトに値が含まれている場合は結果がになります。それ以外の場合はが返され **`false`** ます。

含まれているオブジェクトの種類を `T` [in_place_t](in-place-t-struct.md)または[nullopt_t](nullopt-t-structure.md)することはできません。 `T`*破棄可能な*である必要があります。つまり、デストラクターは所有されているすべてのリソースを解放する必要があり、例外をスローしないことがあります。

`optional`クラスは c++ 17 で新しく追加されたものです。

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
|[~ 省略可能](#optional-destructor) | 型のオブジェクトを破棄 `optional` します。 |
| **割り当て** | |
| [operator =](#op_eq) | を `optional` 別ののコピーで置き換え `optional` ます。 |
| [emplace](#op_eq) | 引数を指定して、格納されている値を初期化します。 |
| **フォト** | |
| [スワップ](#swap) | 格納されている値または空の状態を別のに交換 `optional` します。 |
| **オブザーバー** | |
| [has_value](#has_value) | `optional`オブジェクトに値が含まれているかどうかを返します。 |
| [value](#value) | 格納されている値を返します。 |
| [value_or](#value_or) | 含まれている値を返します。値が存在しない場合は、代替のを返します。 |
| [演算子->](#op_as) | オブジェクトの格納されている値を参照 `optional` します。 |
| [operator](#op_mem) | オブジェクトの格納されている値を参照 `optional` します。 |
| [bool 演算子](#op_bool) | `optional`オブジェクトに値が含まれているかどうかを返します。 |
| **修飾子** | |
| [reset](#reset) | 格納さ `optional` れている値をすべて破棄することによって、をリセットします。 |

## <a name="has_value"></a><a name="has_value"></a>has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional-constructor"></a><a name="optional"></a>省略可能なコンストラクター

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
格納され `optional` ている値をコピーまたは移動する。

*i_list*\
格納されている値を構築する初期化子リスト。

*value*\
格納されている値を構築する引数リスト。

### <a name="remarks"></a>解説

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;`これらのコンストラクターは、 `optional` 値を含まないを構築します。

`constexpr optional(const optional& rhs);`コピーコンストラクターは、引数の格納されている値から、格納されている値を初期化します。 が true の場合を除き、**削除済み**として定義されて `is_copy_constructible_v<T>` おり、が true の場合は簡単です `is_trivially_copy_constructible_v<T>` 。

`constexpr optional(optional&& rhs) noexcept;`移動コンストラクターは、引数の格納されている値から移動して、格納されている値を初期化します。 が true である場合を除いて、オーバーロードの解決には関与しません `is_move_constructible_v<T>` 。が true の場合、簡単 `is_trivially_move_constructible_v<T>` です。

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);`引数を使用する場合と同様に、格納されている値を直接初期化し `std::forward<Args>(args)` ます。 このコンストラクターは **`constexpr`** 、使用するコンストラクターがである場合にです `T` **`constexpr`** 。 が true でない限り、オーバーロードの解決には関与しません `is_constructible_v<T, Args...>` 。

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);`引数を使用する場合と同様に、格納されている値を直接初期化し `i_list, std::forward<Args>(args)` ます。 このコンストラクターは **`constexpr`** 、使用するコンストラクターがである場合にです `T` **`constexpr`** 。 が true でない限り、オーバーロードの解決には関与しません `is_constructible_v<T, initializer_list<U>&, Args&&...>` 。

`template <class U = T> explicit constexpr optional(U&& rhs);`直接を使用する場合と同様に、格納されている値を初期化し `std::forward<U>(v)` ます。 このコンストラクターは **`constexpr`** 、使用するコンストラクターがである場合にです `T` **`constexpr`** 。 `is_constructible_v<T, U&&>`が true で、 `is_same_v<remove_cvref_t<U>, in_place_t>` and が false でない限り、オーバーロードの解決には関与しません `is_same_v<remove_cvref_t<U>, optional>` 。

`template <class U> explicit optional(const optional<U>& rhs);`*Rhs*に値が含まれている場合は、引数の格納されている値から、格納されている値を直接初期化します。 が true ではなく、、、、、、、 `is_constructible_v<T, const U&>` `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>` 、および `is_convertible_v<const optional<U>&&, T>` がすべて false である場合を除き、オーバーロードの解決には関与しません。

`template <class U> explicit optional(optional<U>&& rhs);`*Rhs*に値が含まれている場合は、を使用しているかのように、格納されている値を直接初期化し `std::move(*rhs)` ます が true ではなく、、、、、、、 `is_constructible_v<T, U&&>` `is_constructible_v<T, optional<U>&>` `is_constructible_v<T, optional<U>&&>` `is_constructible_v<T, const optional<U>&>` `is_constructible_v<T, const optional<U>&&>` `is_convertible_v<optional<U>&, T>` `is_convertible_v<optional<U>&&, T>` `is_convertible_v<const optional<U>&, T>` 、および `is_convertible_v<const optional<U>&&, T>` がすべて false である場合を除き、オーバーロードの解決には関与しません。

## <a name="optional-destructor"></a><a name="optional-destructor"></a>~ 省略可能なデストラクター

非普通の破棄可能なに含まれている値が存在する場合は、そのデストラクターを呼び出して破棄します。

```cpp
~optional();
```

### <a name="remarks"></a>解説

`T`が普通で破棄可能なの場合、 `optional<T>` も普通の破棄可能なです。

## <a name="operator"></a><a name="op_eq"></a>operator =

の格納されている値を、 `optional` 格納されている別の値からコピーまたは移動して置換し `optional` ます。

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

## <a name="operator-"></a><a name="op_as"></a>演算子->

オブジェクトの格納されている値を逆参照し `optional` ます。

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="operator"></a><a name="op_mem"></a>operator

オブジェクトの格納されている値を逆参照し `optional` ます。

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="operator-bool"></a><a name="op_bool"></a>bool 演算子

オブジェクトに格納されている値があるかどうか `optional` を報告します。

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a><a name="reset"></a>解除

実質的に、は、含まれているオブジェクトのデストラクターを呼び出し、初期化されていない状態に設定します。

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a>フォト

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a><a name="value"></a> の値

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a><a name="value_or"></a>value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>関連項目

[\<optional>](optional.md)
