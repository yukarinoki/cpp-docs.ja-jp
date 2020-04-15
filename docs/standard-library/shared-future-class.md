---
title: shared_future クラス
ms.date: 11/04/2016
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.openlocfilehash: 65ea01a9ced1ca69cd1b1526e7594c4b54387553
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336783"
---
# <a name="shared_future-class"></a>shared_future クラス

*非同期のリターン オブジェクト*を記述します。 [future](../standard-library/future-class.md) オブジェクトとは異なり、*非同期プロバイダー*を任意の数の `shared_future` オブジェクトに関連付けることができます。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>解説

`valid`、`operator=` のメソッド、および*空の*`shared_future` オブジェクト上のデストラクター以外は呼び出しません。

`shared_future` オブジェクトは同期されません。 同じオブジェクト上で複数のスレッドからメソッドを呼び出すことは、結果が予測不可能なデータ競合をもたらします。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[shared_future](#shared_future)|`shared_future` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get](#get)|*関連付けられた非同期状態*に格納されている結果を取得します。|
|[有効](#valid)|オブジェクトが空でないかどうかを指定します。|
|[待つ](#wait)|関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。|
|[wait_for](#wait_for)|関連付けられた非同期状態が準備できるまで、または指定した時間が経過するまでブロックします。|
|[wait_until](#wait_until)|関連付けられた非同期状態が準備できるまで、または指定した時点までブロックします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[shared_future::演算子=](#op_eq)|新しい関連付けられた非同期状態を割り当てます。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<将来の>

**名前空間:** std

## <a name="shared_futureget"></a><a name="get"></a>shared_future::取得

*関連付けられた非同期状態*に格納されている結果を取得します。

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>解説

結果が例外の場合は、そのメソッドが再スローします。 それ以外の場合、結果が返されます。

結果を取得する前に、このメソッドは、関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。

部分的特殊化`shared_future<Ty&>`の場合、格納された値は、事実上、戻り値として*非同期プロバイダー*に渡されたオブジェクトへの参照です。

特殊化`shared_future<void>`に格納されている値が存在しないため、メソッドは**void**を返します。

## <a name="shared_futureoperator"></a><a name="op_eq"></a>shared_future::演算子=

指定したオブジェクトから*関連付けられた非同期状態*を転送します。

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`shared_future` オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>解説

最初の演算子の場合、操作後に*Right*に関連付けられた非同期状態がなくなりました。

2 番目のメソッドの*Right は*、関連付けられた非同期状態を維持します。

## <a name="shared_futureshared_future-constructor"></a><a name="shared_future"></a>shared_future::shared_futureコンストラクタ

`shared_future` オブジェクトを構築します。

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
[future](../standard-library/future-class.md) または `shared_future` オブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは、`shared_future`*関連付けられた非同期状態*を持たないオブジェクトを構築します。

2 番目と 3 番目`shared_future`のコンストラクターはオブジェクトを構築し、関連する非同期状態を*Right*から転送します。 *Right*には、非同期状態が関連付けなくなりました。

4 番目のコンストラクターは`shared_future`、 *Right*と同じ関連付けられた非同期状態を持つオブジェクトを構築します。

## <a name="shared_futurevalid"></a><a name="valid"></a>shared_future::有効

オブジェクトに*関連付けられた非同期状態*を持つかどうかを指定します。

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>戻り値

オブジェクトに非同期状態が関連付けられている場合は**true、** その他の値は true です。それ以外の場合**は false。**

## <a name="shared_futurewait"></a><a name="wait"></a>shared_future::待つ

*関連付けられた非同期状態*が*準備完了*になるまで、現在のスレッドをブロックします。

```cpp
void wait() const;
```

### <a name="remarks"></a>解説

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ準備完了になります。

## <a name="shared_futurewait_for"></a><a name="wait_for"></a>shared_future::wait_for

関連付けられた非同期状態が *ready* になるまで、または指定した時間が経過するまで、現在のスレッドをブロックします。

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>パラメーター

*Rel_time*\
スレッドがブロックする最大の時間間隔を指定する [chrono::duration](../standard-library/duration-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>解説

関連付けられた非同期状態は、その非同期プロバイダーが戻り値を格納している場合、または例外を格納している場合にのみ*準備が可能*です。

## <a name="shared_futurewait_until"></a><a name="wait_until"></a>shared_future::wait_until

関連付けられた非同期状態が *ready* になるまで、または指定した時点後まで現在のスレッドをブロックします。

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>パラメーター

*Abs_time*\
スレッドがブロックを解除できる時間を指定する [chrono::time_point](../standard-library/time-point-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>解説

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ準備完了になります。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<将来の>](../standard-library/future.md)
