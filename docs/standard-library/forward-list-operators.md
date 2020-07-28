---
title: '&lt;forward_list&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: beb02a8353c6c5187dd0fa0171518c753eee7868
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193342"
---
# <a name="ltforward_listgt-operators"></a>&lt;forward_list&gt; 演算子

## <a name="operator"></a><a name="op_eq_eq"></a>operator = =

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`forward_list` 型オブジェクト。

*そうです*\
`forward_list` 型オブジェクト。

### <a name="remarks"></a>解説

このテンプレート関数は `operator==` 、クラステンプレートの2つのオブジェクトを比較するためにをオーバーロードし `forward_list` ます。 `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())` が返されます。

## <a name="operator"></a><a name="op_neq"></a>operator! =

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`forward_list` 型オブジェクト。

*そうです*\
`forward_list` 型オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** リストが等しくない場合は。**`false`** リストが等しい場合は。

### <a name="remarks"></a>解説

このテンプレート関数は `!(left == right)` を返します。

## <a name="operatorlt"></a><a name="op_lt"></a>operator&lt;

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより小さいかどうかを調べます。

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`forward_list` 型オブジェクト。

*そうです*\
`forward_list` 型オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のリストが演算子の右辺のリストより小さい場合は、それ以外の場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このテンプレート関数は `operator<` 、クラステンプレートの2つのオブジェクトを比較するためにをオーバーロードし `forward_list` ます。 `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())` が返されます。

## <a name="operatorlt"></a><a name="op_lt_eq"></a>operator&lt;=

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以下であるかどうかを調べます。

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`forward_list` 型オブジェクト。

*そうです*\
`forward_list` 型オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のリストが演算子の右辺の list 以下である場合は、を返します。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このテンプレート関数は `!(right < left)` を返します。

## <a name="operatorgt"></a><a name="op_gt"></a>operator&gt;

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより大きいかどうかを調べます。

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`forward_list` 型オブジェクト。

*そうです*\
`forward_list` 型オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺のリストが演算子の右辺の list より大きい場合は、です。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このテンプレート関数は `right < left` を返します。

## <a name="operatorgt"></a><a name="op_gt_eq"></a>operator&gt;=

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以上であるかどうかを調べます。

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`forward_list` 型オブジェクト。

*そうです*\
`forward_list` 型オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の前方リストが演算子の右辺の前方リスト以上である場合は、を返します。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

このテンプレート関数は `!(left < right)` を返します。
