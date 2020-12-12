---
description: '詳細: バリアントクラス'
title: variant クラス
ms.date: 04/04/2019
f1_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
helpviewer_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
ms.openlocfilehash: 0fc2887def147b458e63bc316f211e62a5eba879
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305105"
---
# <a name="variant-class"></a>variant クラス

任意の時点における variant のインスタンスはいずれも、その代わりの型のいずれかの値を保持するか、値を保持しません。

## <a name="syntax"></a>構文

```cpp
template <class... Types>
    class variant
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|-|-|
|[variant](#variant)|`variant` 型のオブジェクトを構築します。|

### <a name="functions"></a>関数

|名前|説明|
|-|-|
|[emplace](#emplace)|格納されている新しい値を作成します。|
|[インデックス](#index)|格納されている値のインデックスを返します。|
|[スワップ](#swap)||
|[valueless_by_exception](#emplace)|**`false`** バリアントが値を保持している場合はを返します。|

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[operator =](#op_eq)|バリアントを別のバリアントのコピーで置き換えます。|

## <a name="emplace"></a><a name="emplace"></a> emplace

格納されている新しい値を作成します。

```cpp
template <class T, class... Args>
    T& emplace(Args&&...);
template <class T, class U, class... Args>
    T& emplace(initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(Args&&...);
template <size_t I, class U, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(initializer_list<U>, Args&&...);
```

## <a name="index"></a><a name="index"></a> 化

格納されている値のインデックスを返します。

```cpp
constexpr size_t index() const noexcept;
```

## <a name="variant"></a><a name="variant"></a> 型

`variant` 型のオブジェクトを構築します。 には、デストラクターも含まれています。

```cpp
constexpr variant() noexcept(see below);
variant(const variant&);
variant(variant&&) noexcept(see below);
template <class T>
    constexpr variant(T&&) noexcept(see below);
template <class T, class... Args>
    constexpr explicit variant(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    constexpr explicit variant(in_place_type_t<T>, initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    constexpr explicit variant(in_place_index_t<I>, Args&&...);
template <size_t I, class U, class... Args>
    constexpr explicit variant(in_place_index_t<I>, initializer_list<U>, Args&&...);

template <class Alloc>
    variant(allocator_arg_t, const Al&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, const variant&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, variant&&);
template <class Alloc, class T>
    variant(allocator_arg_t, const Al&, T&&);
template <class Alloc, class T, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, Args&&...);
template <class Alloc, class T, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, initializer_list<U>, Args&&...);
template <class Alloc, size_t I, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, Args&&...);
template <class Alloc, size_t I, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, initializer_list<U>, Args&&...);

~variant();
```

### <a name="parameters"></a>パラメーター

*ウムアルクラ*\
このオブジェクトに対して使用するアロケーター クラス。

## <a name="operator"></a><a name="op_eq"></a> operator =

バリアントを別のバリアントのコピーで置き換えます。

```cpp
variant& operator=(const variant&);
variant& operator=(variant&&) noexcept(see below);
template <class T>
    variant& operator=(T&&) noexcept(see below);
```

## <a name="swap"></a><a name="swap"></a> フォト

```cpp
void swap(variant&) noexcept(see below);
```

## <a name="valueless_by_exception"></a><a name="valueless"></a> valueless_by_exception

**`false`** バリアントが値を保持している場合はを返します。

```cpp
constexpr bool valueless_by_exception() const noexcept;
```
