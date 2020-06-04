---
title: time_point クラス
ms.date: 03/27/2019
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
helpviewer_keywords:
- std::chrono [C++], time_point
ms.openlocfilehash: e1de674d4a13ba465100923bffe6cba76e61ab4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368028"
---
# <a name="time_point-class"></a>time_point クラス

`time_point` では、時点を表す型について記述します。 これは、テンプレート引数 `Clock` によって表される新しいエポック以降の経過時間を格納する [duration](../standard-library/duration-class.md) 型のオブジェクトを保持します。

## <a name="syntax"></a>構文

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`time_point::clock`|テンプレート パラメーター `Clock` のシノニム。|
|`time_point::duration`|テンプレート パラメーター `Duration` のシノニム。|
|`time_point::period`|入れ子にされた型の名前 `duration::period` のシノニム。|
|`time_point::rep`|入れ子にされた型の名前 `duration::rep` のシノニム。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[time_point](#time_point)|`time_point` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[max](#max)|`time_point::ref` の上限を指定します。|
|[min](#min)|`time_point::ref` の下限を指定します。|
|[time_since_epoch](#time_since_epoch)|格納された `duration` の値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[time_point::演算子+=](#op_add_eq)|指定した値を格納された期間に加算します。|
|[time_point::operator-=](#operator-_eq)|指定した値を格納された期間から減算します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<クロノ>

**名前空間:** std::chrono

## <a name="time_pointmax"></a><a name="max"></a>time_point::最大

`time_point::ref` 型の値の上限の境界を返す静的メソッドです。

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>戻り値

実際には、`time_point(duration::max())` を返します。

## <a name="time_pointmin"></a><a name="min"></a>time_point::分

`time_point::ref` 型の値の下限の境界を返す静的メソッドです。

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>戻り値

実際には、`time_point(duration::min())` を返します。

## <a name="time_pointoperator"></a><a name="op_add_eq"></a>time_point::演算子+=

指定した値を格納された [duration](../standard-library/duration-class.md) 値に加算します。

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>パラメーター

*長調*\
`duration` オブジェクト。

### <a name="return-value"></a>戻り値

加算が実行された後の `time_point` オブジェクト。

## <a name="time_pointoperator-"></a><a name="operator-_eq"></a>time_point::演算子-=

指定された値を格納された [duration](../standard-library/duration-class.md) 値から減算します。

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>パラメーター

*長調*\
`duration` オブジェクト。

### <a name="return-value"></a>戻り値

減算が実行された後の `time_point` オブジェクト。

## <a name="time_pointtime_point-constructor"></a><a name="time_point"></a>time_point::time_pointコンストラクタ

`time_point` オブジェクトを構築します。

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>パラメーター

*長調*\
[duration](../standard-library/duration-class.md) オブジェクト。

*Tp*\
`time_point` オブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは、格納されている `duration` 値が [duration::zero](../standard-library/duration-class.md#zero) と等しいオブジェクトを構築します。

2 番目のコンストラクターは、保存された duration 値が*Dur*に等しいオブジェクトを構築します。 true`is_convertible<Duration2, duration>`を持たない限り、2 番目のコンストラクターはオーバーロードの解決に参加しません。 詳しくは、「[<type_traits>](../standard-library/type-traits.md)」をご覧ください。

3 番目のコンストラクターは、`duration` を使用してその `Tp.time_since_epoch()` 値を初期化します。

## <a name="time_pointtime_since_epoch"></a><a name="time_since_epoch"></a>time_point::time_since_epoch

格納されている [duration](../standard-library/duration-class.md) 値を取得します。

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<クロノ>](../standard-library/chrono.md)
