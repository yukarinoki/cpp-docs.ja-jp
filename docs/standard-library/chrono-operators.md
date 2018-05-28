---
title: '&lt;chrono&gt; 演算時 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 1ac1051ddaa67dc1970119586ecb9e937583c58a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt; 演算子

||||
|-|-|-|
|[modulo 演算子](#op_modulo)|[operator!=](#op_neq)|[operator&gt;](#op_gt)|
|[operator&gt;=](#op_gt_eq)|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|
|[operator*](#op_star)|[operator+](#op_add)|[operator-](#operator-)|
|[operator/](#op_div)|[operator==](#op_eq_eq)|

## <a name="operator-"></a>  operator-

[duration](../standard-library/duration-class.md) および [time_point](../standard-library/time-point-class.md) オブジェクトの減算または否定の演算子。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator-(
       const duration<Rep1, Period1>& Left,
       cconst duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type
   operator-(
       const time_point<Clock, Duration1>& Time,
       const duration<Rep2, Period2>& Dur);


template <class Clock, class Duration1, class Duration2>
constexpr typename common_type<Duration1, Duration2>::type
   operator-(
       const time_point<Clock, Duration1>& Left,
       const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

`Time` A`time_point`オブジェクト。

`Dur` A`duration`オブジェクト。

### <a name="return-value"></a>戻り値

最初の関数は、間隔の長さが 2 つの引数の期間の違いである `duration` オブジェクトを返します。

2 番目の関数は、`time_point` で指定された時点から `Dur` によって表される期間の拒否によって転置される時点を表す `Time` オブジェクトを返します。

3 番目の関数は、`duration` と `Left` 間の時間間隔を表す `Right` オブジェクトを返します。

## <a name="op_neq"></a>  operator!=

[duration](../standard-library/duration-class.md) または [time_point](../standard-library/time-point-class.md) オブジェクトの非等値演算子。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `!(Left == Right)` です。

## <a name="op_star"></a>  operator*

[duration](../standard-library/chrono-operators.md#op_star) オブジェクトの乗算演算子。

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator*(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Mult);


template <class Rep1, class Rep2, class Period2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2>
   operator*(
       const Rep1& Mult,
       const duration<Rep2,
       Period2>& Dur);
```

### <a name="parameters"></a>パラメーター

`Dur` A`duration`オブジェクト。

`Mult` 整数値。

### <a name="return-value"></a>戻り値

各関数は、間隔が `duration` の長さを乗算した `Mult` である `Dur` オブジェクトを返します。

`is_convertible<Rep2, common_type<Rep1, Rep2>>` が *true* にならない限り、最初の関数はオーバーロードの解決に関与しません。 詳細については、「[<type_traits>](../standard-library/type-traits.md)」を参照してください。

`is_convertible<Rep1, common_type<Rep1, Rep2>>` が *true* にならない限り、2 番目の関数はオーバーロードの解決に関与しません。 詳細については、「[<type_traits>](../standard-library/type-traits.md)」を参照してください。

## <a name="op_div"></a>  operator/

[duration](../standard-library/chrono-operators.md#op_star) オブジェクトの除算演算子。

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator/(
     const duration<Rep1, Period1>& Dur,
     const Rep2& Div);


template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<Rep1, Rep2>::type
   operator/(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>パラメーター

`Dur` A`duration`オブジェクト。

`Div` 整数値。

`Left` 左側の`duration`オブジェクト。

`Right` 右側の`duration`オブジェクト。

### <a name="return-value"></a>戻り値

最初の演算子は、間隔の長さが `Dur` の値で除算した `Div` の長さである duration オブジェクトを返します。

2 番目の演算子は、`Left` と `Right` の間隔の長さの比率を返します。

`is_convertible<Rep2, common_type<Rep1, Rep2>>` が *true を保持*せず、かつ `Rep2` が `duration` のインスタンス化ではない限り、最初の演算子はオーバーロードの解決に関与しません。 詳細については、「[<type_traits>](../standard-library/type-traits.md)」を参照してください。

## <a name="op_add"></a>  operator+

[duration](../standard-library/duration-class.md) および [time_point](../standard-library/time-point-class.md) オブジェクトを追加します。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator+(
      const duration<Rep1, Period1>& Left,
      const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,
      const duration<Rep2, Period2>& Dur);


template <class Rep1, class Period1, class Clock, class Duration2>
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,
      const time_point<Clock, Duration2>& Time);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

`Time` A`time_point`オブジェクト。

`Dur` A`duration`オブジェクト。

### <a name="return-value"></a>戻り値

最初の関数は `duration` と `Left` の間隔の合計と同じ時間間隔がある `Right` オブジェクトを返します。

2 番目と 3 番目の関数は、`time_point`時点からの間隔 `Dur` によって、転置される時点を表す `Time` オブジェクトを返します。

## <a name="op_lt"></a>  operator&lt;

一方の [duration](../standard-library/duration-class.md) または [time_point](../standard-library/time-point-class.md) オブジェクトが、もう一方の `duration` または `time_point` オブジェクト未満かどうかを判断します。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

### <a name="return-value"></a>戻り値

`true` の間隔の長さが `Left` の間隔の長さ未満である場合、最初の関数は `Right` を返します。 それ以外の場合、関数は `false` を返します。

`true` が `Left` に先行する場合、2 番目の関数は `Right` を返します。 それ以外の場合、関数は `false` を返します。

## <a name="op_lt_eq"></a>  演算子&lt;=

一方の [duration](../standard-library/duration-class.md) または [time_point](../standard-library/time-point-class.md) オブジェクトの値がもう一方の `duration` または `time_point` オブジェクトの値未満かどうかを判断します。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `!(Right < Left)` です。

## <a name="op_eq_eq"></a>  operator==

2 つの `duration` オブジェクトが同じ長さの時間間隔を表しているかどうか、または 2 つの `time_point` オブジェクトが同じ時点を表しているかどうかを判断します。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

### <a name="return-value"></a>戻り値

最初の関数は、`true` と `Left` が同じ長さの時間間隔を表す場合に `Right` を返します。 それ以外の場合、関数は `false` を返します。

2 番目の関数は、`true` と `Left` が同じ時点を表す場合に `Right` を返します。 それ以外の場合、関数は `false` を返します。

## <a name="op_gt"></a>  operator&gt;

1 つの [duration](../standard-library/duration-class.md) オブジェクトまたは [time_point](../standard-library/time-point-class.md) オブジェクトが、別の `duration` オブジェクトまたは `time_point` オブジェクトより大きいかどうかを判断します。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `Right < Left` です。

## <a name="op_gt_eq"></a>  演算子&gt;=

一方の [duration](../standard-library/duration-class.md) または [time_point](../standard-library/time-point-class.md) オブジェクトの値がもう一方の `duration` または `time_point` オブジェクトの値以上かどうかを判断します。

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>パラメーター

`Left` 左側の`duration`または`time_point`オブジェクト。

`Right` 右側の`duration`または`time_point`オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `!(Left < Right)` です。

## <a name="op_modulo"></a>  modulo 演算子

[duration](../standard-library/duration-class.md) オブジェクトに対する剰余演算の演算子。

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<Rep1, Period1, Rep2>::type
   operator%(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>パラメーター

`Dur` A`duration`オブジェクト。

`Div` 整数値。

`Left` 左側の`duration`オブジェクト。

`Right` 右側の`duration`オブジェクト。

### <a name="return-value"></a>戻り値

最初の関数は、間隔の長さが `Dur` を `Div` で除算した剰余となっている `duration` オブジェクトを返します。

2 番目の関数は、`Left` を `Right` で除算した剰余を表す値を返します。

## <a name="see-also"></a>関連項目

[\<chrono>](../standard-library/chrono.md)<br/>
