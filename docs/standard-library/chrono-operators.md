---
title: '&lt;chrono&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 398e2429c38cffb454c7b510aa5ab44fbe4cfef6
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865202"
---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt; 演算子

## <a name="operator-"></a>operator

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

*時刻*\
`time_point` オブジェクトです。

*期間*\
`duration` オブジェクトです。

### <a name="return-value"></a>戻り値

最初の関数は、間隔の長さが 2 つの引数の期間の違いである `duration` オブジェクトを返します。

2番目の関数は、*時間*によって指定された時点から、*期間*によって表される時間間隔の否定によって変位される特定の時点を表す `time_point` オブジェクトを返します。

3番目の関数は、 *Left*と*Right*の間の時間間隔を表す `duration` オブジェクトを返します。

## <a name="op_neq"></a>operator! =

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `!(Left == Right)` です。

## <a name="op_star"></a>operator

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

*期間*\
`duration` オブジェクトです。

*Mult*\
整数値。

### <a name="return-value"></a>戻り値

各関数は、 *Mult*の長さが*期間*の長さで乗算された `duration` オブジェクトを返します。

`is_convertible<Rep2, common_type<Rep1, Rep2>>` が *true* にならない限り、最初の関数はオーバーロードの解決に関与しません。 詳細については、「[<type_traits>](../standard-library/type-traits.md)」を参照してください。

`is_convertible<Rep1, common_type<Rep1, Rep2>>` が *true* にならない限り、2 番目の関数はオーバーロードの解決に関与しません。 詳細については、「[<type_traits>](../standard-library/type-traits.md)」を参照してください。

## <a name="op_div"></a>operator

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

*期間*\
`duration` オブジェクトです。

*Div*\
整数値。

*左*\
左側の `duration` オブジェクト。

*右*\
右側の `duration` オブジェクト。

### <a name="return-value"></a>戻り値

最初の演算子は、間隔の長さが値の*Div*で除算された*期間*の長さである duration オブジェクトを返します。

2番目の演算子は、*左*と*右*の間隔の長さの比率を返します。

`is_convertible<Rep2, common_type<Rep1, Rep2>>` が *true を保持*せず、かつ `Rep2` が `duration` のインスタンス化ではない限り、最初の演算子はオーバーロードの解決に関与しません。 詳細については、「[<type_traits>](../standard-library/type-traits.md)」を参照してください。

## <a name="op_add"></a>演算子 +

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

*時刻*\
`time_point` オブジェクトです。

*期間*\
`duration` オブジェクトです。

### <a name="return-value"></a>戻り値

最初の関数は、*左右*の間隔の*合計と同じ*時間間隔を持つ `duration` オブジェクトを返します。

2番目と3番目の関数は `time_point` を返します。このオブジェクトは、特定*の時点の* *期間*間隔で、その時点を表します。

## <a name="op_lt"></a> 演算子&lt;

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

### <a name="return-value"></a>戻り値

最初の関数は、 *Left*の interval の長さが*Right*の interval の長さよりも小さい場合に**true**を返します。 それ以外の場合、関数は**false**を返します。

2番目の関数は、 *Left*が*Right*の前にある場合に**true**を返します。 それ以外の場合、関数は**false**を返します。

## <a name="op_lt_eq"></a>演算子&lt;=

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `!(Right < Left)` です。

## <a name="op_eq_eq"></a>operator = =

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

### <a name="return-value"></a>戻り値

最初の関数は、 *Left*と*Right*が同じ長さの時間間隔を表している場合に**true**を返します。 それ以外の場合、関数は**false**を返します。

2番目の関数は、 *Left*と*Right*が同じ時点を表している場合に**true**を返します。 それ以外の場合、関数は**false**を返します。

## <a name="op_gt"></a> 演算子&gt;

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `Right < Left` です。

## <a name="op_gt_eq"></a>演算子&gt;=

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

*左*\
左側の `duration` オブジェクトまたは `time_point` オブジェクト。

*右*\
右側の `duration` オブジェクトまたは `time_point` オブジェクト。

### <a name="return-value"></a>戻り値

各関数から返される値は `!(Left < Right)` です。

## <a name="op_modulo"></a>剰余演算子

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

*期間*\
`duration` オブジェクトです。

*Div*\
整数値。

*左*\
左側の `duration` オブジェクト。

*右*\
右側の `duration` オブジェクト。

### <a name="return-value"></a>戻り値

最初の関数は、間隔の長さが*期間*モジュロ*Div*である `duration` オブジェクトを返します。

2番目の関数は、*左*剰余*右*を表す値を返します。
