---
description: '詳細情報: &lt; chrono &gt; functions'
title: '&lt;chrono&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 161edeccace243c10a6382d931f5f9387f35790d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234203"
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 関数

## <a name="duration_cast"></a><a name="duration_cast"></a> duration_cast

`duration` オブジェクトを指定した型にキャストします。

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);

template <class ToDuration, class Rep, class Period>
constexpr ToDuration floor(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration ceil(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration round(const duration<Rep, Period>& d);
```

### <a name="return-value"></a>戻り値

対象の型に収まる必要のある場合、省略された期間 `duration` を表す `To` 型の `Dur` オブジェクト。

### <a name="remarks"></a>解説

`To` が `duration` のインスタンス化の場合、この関数はオーバーロードの解決に関与しません。

## <a name="time_point_cast"></a><a name="time_point_cast"></a> time_point_cast

[time_point](../standard-library/time-point-class.md) オブジェクトを指定した型にキャストします。

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);

template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
floor(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
ceil(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
round(const time_point<Clock, Duration>& tp);
```

### <a name="return-value"></a>戻り値

`time_point` 型の継続時間を含む `To` オブジェクト。

### <a name="remarks"></a>解説

`To` が [duration](../standard-library/duration-class.md) のインスタンス化ではない限り、この関数はオーバーロードの解決に関与しません。
