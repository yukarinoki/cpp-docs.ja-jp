---
description: '詳細情報: &lt; スレッド &gt; 演算子'
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
ms.openlocfilehash: 3992dccf051622bcf854c1843f1bdeb15d227731
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207424"
---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt; 演算子

[operator! =](#op_neq)\
[operator&gt;](#op_gt)\
[operator&gt;=](#op_gt_eq)\
[operator&lt;](#op_lt)\
[operator&lt;&lt;](#op_lt_lt)\
[operator&lt;=](#op_lt_eq)\
[operator = =](#op_eq_eq)

## <a name="operatorgt"></a><a name="op_gt_eq"></a> operator&gt;=

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以上かどうかを判断します。

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`!(Left < Right)`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より大きいかどうかを判断します。

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`Right < Left`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorlt"></a><a name="op_lt_eq"></a> operator&lt;=

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以下かどうかを判断します。

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`!(Right < Left)`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より小さいかどうかを判断します。

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 左 *の順序で**左* にある場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この演算子は、すべての `thread::id` オブジェクトでの全体の順序付けを定義します。 これらのオブジェクトは、連想コンテナー内のキーとして使用できます。

この関数では、例外がスローされません。

## <a name="operator"></a><a name="op_neq"></a> operator! =

2 つの `thread::id` オブジェクトが等しくないかどうかを比較します。

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

`!(Left == Right)`

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

2 つの `thread::id` オブジェクトが等しいかどうかを比較します。

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>パラメーター

*左側*\
左側の `thread::id` オブジェクト。

*そうです*\
右側の `thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 2つのオブジェクトが同じ実行スレッドを表している場合、またはいずれのオブジェクトも実行スレッドを表している場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この関数では、例外がスローされません。

## <a name="operatorltlt"></a><a name="op_lt_lt"></a> operator&lt;&lt;

`thread::id` オブジェクトのテキスト表現をストリームに挿入します。

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>パラメーター

*Ostr*\
[basic_ostream](../standard-library/basic-ostream-class.md) オブジェクト。

*番号*\
`thread::id` オブジェクト。

### <a name="return-value"></a>戻り値

*Ostr*。

### <a name="remarks"></a>解説

この関数は、 *Ostr* に *Id* を挿入します。

2 つの `thread::id` オブジェクトが等しい場合、これらのオブジェクトの挿入されたテキスト表現は同じです。

## <a name="see-also"></a>関連項目

[\<thread>](../standard-library/thread.md)
