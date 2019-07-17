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
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
ms.openlocfilehash: 414b3e608e915ec06dbdf90726151a1c33ea4c60
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269204"
---
# <a name="optional-class"></a>省略可能なクラス

値を含めることはできませんが、オブジェクトについて説明します。

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
|[optional](#optional)|`optional` 型のオブジェクトを構築します。|

### <a name="functions"></a>関数

|||
|-|-|
|[has_value](#has_value)|返します**true**場合`optional`値が含まれています。|
|[reset](#reset)|リセット、`optional`します。|
|[value](#value)|評価、`optional`値。|
|[value_or](#value_or)|評価、`optional`値。|

### <a name="operators"></a>演算子

|||
|-|-|
|[operator=](#op_eq)|置換、`optional`別のコピーで`optional`します。|
|[operator->](#op_as)|値を代入`optional`します。|
|[operator*](#op_mem)|メモリ参照`optional`します。|
|[operator bool](#op_bool)|ブール値を返す`optional`値。|

### <a name="has_value"></a> has_value

```cpp
constexpr bool has_value() const noexcept;
```

### <a name="optional"></a> 省略可能

`optional` 型のオブジェクトを構築します。 また、デストラクターが含まれます。

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t) noexcept;
constexpr optional(const optional&);
constexpr optional(optional&&) noexcept(see below);

template <class... Args>
    constexpr explicit optional(in_place_t, Args&&...);
template <class U, class... Args>
    constexpr explicit optional(in_place_t, initializer_list<U>, Args&&...);
template <class U = T>
    explicit constexpr optional(U&&);
template <class U>
    explicit optional(const optional<U>&);
template <class U>
    explicit optional(optional<U>&&);

~optional();
```

### <a name="op_eq"></a> 演算子 =

置換、`optional`別のコピーで`optional`します。

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional&);
optional& operator=(optional&&) noexcept(see below);

template <class U = T>
    optional& operator=(U&&); template <class U> optional& operator=(const optional<U>&);
template <class U>
    optional& operator=(optional<U>&&); template <class... Args> T& emplace(Args&&...);
template <class U, class... Args>
    T& emplace(initializer_list<U>, Args&&...);
```

### <a name="op_as"></a> -> 演算子

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

### <a name="op_mem"></a> 演算子 *

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

### <a name="op_bool"></a> operator bool

```cpp
constexpr explicit operator bool() const noexcept;
```

### <a name="reset"></a> リセット

```cpp
void reset() noexcept;
```

### <a name="value"></a> 値

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

### <a name="value_or"></a> value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```
