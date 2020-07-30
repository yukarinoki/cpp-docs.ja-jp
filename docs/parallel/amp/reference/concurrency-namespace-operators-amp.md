---
title: コンカレンシー名前空間演算子 (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: 03079f8899f3b13c8509e1affd10a82191b1817c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228480"
---
# <a name="concurrency-namespace-operators-amp"></a>コンカレンシー名前空間演算子 (AMP)

||||
|-|-|-|
|[operator! =](#operator_neq)|[operator](#operator_mod)|[operator](#operator_star)|
|[演算子 +](#operator_add)|[operator](#operator-)|[operator](#operator_div)|
|[operator = =](#operator_eq_eq)|

## <a name="operator"></a><a name="operator_eq_eq"></a>operator = =

指定した引数が等しいかどうかを判断します。

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
タプルの引数のランク。

*_Lhs*<br/>
比較するタプルの 1 つ。

*_Rhs*<br/>
比較するタプルの 1 つ。

### <a name="return-value"></a>戻り値

**`true`** 組が等しい場合は。それ以外の場合は **`false`** 。

## <a name="operator"></a><a name="operator_neq"></a>operator! =

指定した引数が等しくないかどうかを判断します。

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
タプルの引数のランク。

*_Lhs*<br/>
比較するタプルの 1 つ。

*_Rhs*<br/>
比較するタプルの 1 つ。

### <a name="return-value"></a>戻り値

**`true`** 組が等しくない場合は。それ以外の場合は **`false`** 。

## <a name="operator"></a><a name="operator_add"></a>演算子 +

指定された引数の要素ごとの合計を計算します。

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
タプルの引数のランク。

*_Lhs*<br/>
追加する引数の 1 つ。

*_Rhs*<br/>
追加する引数の 1 つ。

### <a name="return-value"></a>戻り値

指定された引数の要素ごとの合計。

## <a name="operator-"></a><a name="operator-"></a>operator

指定された引数の要素ごとの差を計算します。

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
タプルの引数のランク。

*_Lhs*<br/>
減算元の引数。

*_Rhs*<br/>
減算する引数。

### <a name="return-value"></a>戻り値

指定された引数の要素ごとの差。

## <a name="operator"></a><a name="operator_star"></a>operator

指定された引数の要素ごとの積を計算します。

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
タプルの引数のランク。

*_Lhs*<br/>
乗算するタプルのいずれか。

*_Rhs*<br/>
乗算するタプルのいずれか。

### <a name="return-value"></a>戻り値

指定された引数の要素ごとの積。

## <a name="operator"></a><a name="operator_div"></a>operator

指定された引数のコンポーネントごとの商を計算します。

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
タプルの引数のランク。

*_Lhs*<br/>
除算されるタプル。

*_Rhs*<br/>
除算するタプル。

### <a name="return-value"></a>戻り値

指定された引数のコンポーネントごとの商。

## <a name="operator"></a><a name="operator_mod"></a>operator

2 番目の指定された引数による 1 番目の指定された引数の剰余を計算します。

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター

*_Rank*<br/>
タプルの引数のランク。

*_Lhs*<br/>
剰余が計算される元のタプル。

*_Rhs*<br/>
それによって剰余が計算されるタプル。

### <a name="return-value"></a>戻り値

2 番目の指定された引数による 1 番目の指定された引数の剰余という結果。

## <a name="see-also"></a>関連項目

[Concurrency 名前空間](concurrency-namespace-cpp-amp.md)
