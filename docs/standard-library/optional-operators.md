---
title: '&lt;オプションの &gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- optional/std::operator!=
- optional/std::operator==
- optional/std::operatoroperator&gt;
- optional/std::operatoroperator&gt=;
- optional/std::operatoroperator&lt;
- optional/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (optional)
- std::operator== (optional)
- std::operatoroperator&gt; (optional)
- std::operatoroperator&gt=; (optional)
- std::operatoroperator&lt; (optional)
- std::operatoroperator&lt;= (optional)
ms.openlocfilehash: c7eca76f71f12e7f7fe0e60c0a4cfe456d54c374
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224683"
---
# <a name="ltoptionalgt-operators"></a>&lt;オプションの &gt; 演算子

## <a name="operator"></a><a name="op_eq_eq"></a>operator = =

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトと等しいかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左側*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

*そうです*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

## <a name="operator"></a><a name="op_neq"></a>operator! =

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトと等しくないかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左側*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

*そうです*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

### <a name="remarks"></a>解説

このテンプレート関数は `!(left == right)` を返します。

## <a name="operatorlt"></a><a name="op_lt"></a>operator&lt;

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトより小さいかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左側*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

*そうです*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のリストが演算子の右辺のリストより小さい場合は、それ以外の場合は。それ以外の場合は **`false`** 。

## <a name="operatorlt"></a><a name="op_lt_eq"></a>operator&lt;=

演算子の左側の `optional` オブジェクトが右側の  `optional` オブジェクト以下かどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左側*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

*そうです*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のリストが演算子の右辺の list 以下である場合は、を返します。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このテンプレート関数は `!(right < left)` を返します。

## <a name="operatorgt"></a><a name="op_gt"></a>operator&gt;

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトより大きいかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左側*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

*そうです*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のリストが演算子の右辺の list より大きい場合は、です。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このテンプレート関数は `right < left` を返します。

## <a name="operatorgt"></a><a name="op_gt_eq"></a>operator&gt;=

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクト以上であるかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左側*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

*そうです*\
`optional`、 `nullopt_t` 、または型のオブジェクト `T` 。

### <a name="return-value"></a>戻り値

**`true`**`optional`演算子の左辺のが演算子の右辺のより大きいか等しい場合は `optional` 。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このテンプレート関数は `!(left < right)` を返します。
