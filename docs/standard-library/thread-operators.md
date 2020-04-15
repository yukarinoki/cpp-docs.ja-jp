---
title: '&lt;thread&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.openlocfilehash: 6312d14dc681736ee396d5c7af6c50ba8d72cd3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375831"
---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt; 演算子

||||
|-|-|-|
|[演算子!=](#op_neq)|[演算子&gt;](#op_gt)|[演算子&gt;=](#op_gt_eq)|
|[演算子&lt;](#op_lt)|[演算子&lt;&lt;](#op_lt_lt)|[演算子&lt;=](#op_lt_eq)|
|[演算子==](#op_eq_eq)|

## <a name="operatorgt"></a><a name="op_gt_eq"></a>演算子&gt;=

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以上かどうかを判断します。

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`!(Left < Right)`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorgt"></a><a name="op_gt"></a>演算子&gt;

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より大きいかどうかを判断します。

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`Right < Left`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorlt"></a><a name="op_lt_eq"></a>演算子&lt;=

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以下かどうかを判断します。

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`!(Right < Left)`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorlt"></a><a name="op_lt"></a>演算子&lt;

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より小さいかどうかを判断します。

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

*左*が合計順序の*右*の前にあたる場合**は true、** その他の値は true です。それ以外の場合**は false。**

### <a name="remarks"></a>解説

この演算子は、すべての `thread::id` オブジェクトでの全体の順序付けを定義します。 これらのオブジェクトは、連想コンテナー内のキーとして使用できます。

この関数では、例外がスローされません。

## <a name="operator"></a><a name="op_neq"></a>演算子!=

2 つの `thread::id` オブジェクトが等しくないかどうかを比較します。

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`!(Left == Right)`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operator"></a><a name="op_eq_eq"></a>演算子==

2 つの `thread::id` オブジェクトが等しいかどうかを比較します。

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

2 つのオブジェクトが同じ実行スレッドを表す場合、またはどちらのオブジェクトも実行スレッドを表していない場合は**true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>演算子&lt;&lt;

`thread::id` オブジェクトのテキスト表現をストリームに挿入します。

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>パラメーター

*Ostr*\
[basic_ostream](../standard-library/basic-ostream-class.md) オブジェクト。

*Id*\
`thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

*オストル*.

### <a name="remarks"></a>解説

この関数は *、Ostr*に*Id*を挿入します。

2 つの `thread::id` オブジェクトが等しい場合、これらのオブジェクトの挿入されたテキスト表現は同じです。

## <a name="see-also"></a>関連項目

[\<スレッド>](../standard-library/thread.md)
