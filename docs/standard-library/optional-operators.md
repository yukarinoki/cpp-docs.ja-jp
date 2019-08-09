---
title: '&lt;省略可能な&gt;演算子'
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
ms.openlocfilehash: c5d0de435180054b186400384fc0583df5b03246
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268924"
---
# <a name="ltoptionalgt-operators"></a>&lt;省略可能な&gt;演算子

## <a name="op_eq_eq"></a> 演算子 = =

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトと等しいかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

*そうです*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

## <a name="op_neq"></a> operator!=

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトと等しくないかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

*そうです*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

### <a name="remarks"></a>Remarks

このテンプレート関数は `!(left == right)` を返します。

## <a name="op_lt"></a> 演算子&lt;

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトより小さいかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

*そうです*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

### <a name="return-value"></a>戻り値

演算子の左辺の list が演算子の右辺の list 未満である場合は **true**、それ以外の場合は **false**。

## <a name="op_lt_eq"></a>  演算子&lt;=

演算子の左側の `optional` オブジェクトが右側の  `optional` オブジェクト以下かどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

*そうです*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

### <a name="return-value"></a>戻り値

演算子の左辺の list が演算子の右辺の list 以下である場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

このテンプレート関数は `!(right < left)` を返します。

## <a name="op_gt"></a> 演算子&gt;

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトより大きいかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

*そうです*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

### <a name="return-value"></a>戻り値

演算子の左辺の list が演算子の右辺の list より大きい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

このテンプレート関数は `right < left` を返します。

## <a name="op_gt_eq"></a> 演算子&gt;=

演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクト以上であるかどうかを調べます。

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>パラメーター

*左*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

*そうです*\
型のオブジェクト`optional`、 `nullopt_t`、または`T`します。

### <a name="return-value"></a>戻り値

演算子の左辺の `optional` が演算子の右辺の `optional` 以上である場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

このテンプレート関数は `!(left < right)` を返します。
