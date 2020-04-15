---
title: future クラス
ms.date: 11/04/2016
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
helpviewer_keywords:
- std::future [C++]
- std::future [C++], future
- std::future [C++], get
- std::future [C++], share
- std::future [C++], valid
- std::future [C++], wait
- std::future [C++], wait_for
- std::future [C++], wait_until
ms.openlocfilehash: e71c750ddeb198faa3ae9c5960b2668c376241ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370703"
---
# <a name="future-class"></a>future クラス

*非同期のリターン オブジェクト*を記述します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
class future;
```

## <a name="remarks"></a>解説

各標準*非同期プロバイダー*は、このテンプレートのインスタンス化の型を持つオブジェクトを返します。 `future` オブジェクトは、関連付けられている非同期プロバイダーへのアクセスのみを提供します。 同じ非同期プロバイダーに関連付けられている複数の非同期リターン オブジェクトが必要な場合は、`future` オブジェクトを [shared_future](../standard-library/shared-future-class.md) オブジェクトにコピーします。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[将来](#future)|`future` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get](#get)|関連付けられた非同期状態に格納されている結果を取得します。|
|[共有](#share)|オブジェクトを `shared_future` に変換します。|
|[有効](#valid)|オブジェクトが空でないかどうかを指定します。|
|[待つ](#wait)|関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。|
|[wait_for](#wait_for)|関連付けられた非同期状態が準備できるまで、または指定した時間が経過するまでブロックします。|
|[wait_until](#wait_until)|関連付けられた非同期状態が準備できるまで、または指定した時点までブロックします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[future::operator=](#op_eq)|指定したオブジェクトから関連付けられた非同期状態を転送します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<将来の>

**名前空間:** std

## <a name="futurefuture-constructor"></a><a name="future"></a>未来::未来のコンストラクタ

`future` オブジェクトを構築します。

```cpp
future() noexcept;
future(future&& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

*他*\
`future` オブジェクト。

### <a name="remarks"></a>解説

1 つ目のコンストラクターは、関連付けられた非同期状態がない `future` オブジェクトを構築します。

2 番目のコンストラクターは`future`、オブジェクトを構築し、関連する非同期状態を*Other*から転送します。 *他の*ユーザーは、非同期状態に関連付けなくなりました。

## <a name="futureget"></a><a name="get"></a>未来::取得

関連付けられた非同期状態に格納されている結果を取得します。

```cpp
Ty get();
```

### <a name="return-value"></a>戻り値

結果が例外の場合は、そのメソッドが再スローします。 それ以外の場合、結果が返されます。

### <a name="remarks"></a>解説

結果を取得する前に、このメソッドは、関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。

部分的特殊化 `future<Ty&>` では、格納されている値は、実質的には非同期プロバイダーに戻り値として渡されたオブジェクトへの参照です。

特殊化`future<void>`に格納されている値が存在しないため、メソッドは**void**を返します。

その他の特殊化では、メソッドは、格納されている値からその戻り値を移動します。 そのため、このメソッドを 1 回だけ呼び出します。

## <a name="futureoperator"></a><a name="op_eq"></a>将来::演算子=

関連付けられた非同期状態から、指定したオブジェクトを転送します。

```cpp
future& operator=(future&& Right) noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
`future` オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>解説

転送後 *、Right*には非同期状態が関連付けなくなります。

## <a name="futureshare"></a><a name="share"></a>将来::共有

オブジェクトを [shared_future](../standard-library/shared-future-class.md) オブジェクトに変換します。

```cpp
shared_future<Ty> share();
```

### <a name="return-value"></a>戻り値

`shared_future(move(*this))`

## <a name="futurevalid"></a><a name="valid"></a>未来::有効

オブジェクトが関連付けられた非同期状態であるかどうかを指定します。

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>戻り値

オブジェクトに非同期状態が関連付けられている場合は**true、** その他の値は true です。それ以外の場合**は false。**

## <a name="futurewait"></a><a name="wait"></a>未来::待って

関連付けられた非同期状態が *ready* になるまで、現在のスレッドをブロックします。

```cpp
void wait() const;
```

### <a name="remarks"></a>解説

関連付けられた非同期状態は、その非同期プロバイダーが戻り値を格納している場合、または例外を格納している場合にのみ*準備が可能*です。

## <a name="futurewait_for"></a><a name="wait_for"></a>未来::wait_for

関連付けられた非同期状態が *ready* になるまで、または指定した時間が経過するまでブロックします。

```cpp
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>パラメーター

*Rel_time*\
スレッドがブロックする最大の時間間隔を指定する [chrono::duration](../standard-library/duration-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>解説

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ準備完了になります。

## <a name="futurewait_until"></a><a name="wait_until"></a>未来::wait_until

関連付けられた非同期状態が *ready* になるまで、または指定した時点後まで現在のスレッドをブロックします。

```cpp
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>パラメーター

*Abs_time*\
スレッドがブロックを解除できる時間を指定する [chrono::time_point](../standard-library/time-point-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>解説

関連付けられた非同期状態は、その非同期プロバイダーが戻り値を格納している場合、または例外を格納している場合にのみ*準備が可能*です。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<将来の>](../standard-library/future.md)
