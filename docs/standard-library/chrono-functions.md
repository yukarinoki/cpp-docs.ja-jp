---
title: '&lt;chrono&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 5aadf776cc25e22a40ed75f854481dff63cce4bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597497"
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 関数

||||
|-|-|-|
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|

## <a name="duration_cast"></a>  duration_cast

`duration` オブジェクトを指定した型にキャストします。

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```

### <a name="return-value"></a>戻り値

対象の型に収まる必要のある場合、省略された期間 `duration` を表す `To` 型の `Dur` オブジェクト。

### <a name="remarks"></a>Remarks

`To` が `duration` のインスタンス化の場合、この関数はオーバーロードの解決に関与しません。

## <a name="time_point_cast"></a>  time_point_cast

[time_point](../standard-library/time-point-class.md) オブジェクトを指定した型にキャストします。

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```

### <a name="return-value"></a>戻り値

`time_point` 型の継続時間を含む `To` オブジェクト。

### <a name="remarks"></a>Remarks

`To` が [duration](../standard-library/duration-class.md) のインスタンス化ではない限り、この関数はオーバーロードの解決に関与しません。

## <a name="see-also"></a>関連項目

[\<chrono>](../standard-library/chrono.md)<br/>
