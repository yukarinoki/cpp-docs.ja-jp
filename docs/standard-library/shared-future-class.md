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
ms.openlocfilehash: 2280c17c4ce58fe06365c107ad26d646c7ae2d72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412606"
---
# <a name="sharedfuture-class"></a>shared_future クラス

*非同期のリターン オブジェクト*を記述します。 [future](../standard-library/future-class.md) オブジェクトとは異なり、*非同期プロバイダー*を任意の数の `shared_future` オブジェクトに関連付けることができます。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>Remarks

`valid`、`operator=` のメソッド、および*空の* `shared_future` オブジェクト上のデストラクター以外は呼び出しません。

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
|[valid](#valid)|オブジェクトが空でないかどうかを指定します。|
|[wait](#wait)|関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。|
|[wait_for](#wait_for)|関連付けられた非同期状態が準備できるまで、または指定した時間が経過するまでブロックします。|
|[wait_until](#wait_until)|関連付けられた非同期状態が準備できるまで、または指定した時点までブロックします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[shared_future::operator=](#op_eq)|新しい関連付けられた非同期状態を割り当てます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<将来 >

**名前空間:** std

## <a name="get"></a>  shared_future::get

*関連付けられた非同期状態*に格納されている結果を取得します。

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>Remarks

結果が例外の場合は、そのメソッドが再スローします。 それ以外の場合、結果が返されます。

結果を取得する前に、このメソッドは、関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。

部分的特殊化 `shared_future<Ty&>` では、格納されている値は、実質的には*非同期プロバイダー*に戻り値として渡されたオブジェクトへの参照です。

特殊化に格納されている値が存在しないので`shared_future<void>`、メソッドを返します**void**します。

## <a name="op_eq"></a>  shared_future::operator=

指定したオブジェクトから、*関連付けられた非同期状態*を転送します。

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>パラメーター

*右*<br/>
`shared_future` オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>Remarks

最初の演算子*右*不要になった操作の完了後、関連付けられた非同期状態を持ちます。

2 番目のメソッドでは、*右*関連付けられた非同期状態を維持します。

## <a name="shared_future"></a>  shared_future::shared_future コンストラクター

`shared_future` オブジェクトを構築します。

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>パラメーター

*右*<br/>
[future](../standard-library/future-class.md) または `shared_future` オブジェクト。

### <a name="remarks"></a>Remarks

1 つ目のコンストラクターは、*関連付けられた非同期状態*がない `shared_future` オブジェクトを構築します。

2 番目と 3 番目のコンス トラクターを構築、`shared_future`オブジェクトし、関連付けられた非同期状態からの転送*右*します。 *右*関連付けられた非同期状態にはなくなりました。

4 番目のコンス トラクターの構成要素を`shared_future`として非同期状態が同じであるオブジェクトに関連付けられている*右*します。

## <a name="valid"></a>  shared_future::valid

オブジェクトが*関連付けられた非同期状態*であるかどうかを指定します。

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>戻り値

**true**場合は、オブジェクトに関連付けられた非同期状態です。 それ以外の場合、 **false**します。

## <a name="wait"></a>  shared_future::wait

*関連付けられた非同期状態*が *ready* になるまで、現在のスレッドをブロックします。

```cpp
void wait() const;
```

### <a name="remarks"></a>Remarks

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ、準備完了になります。

## <a name="wait_for"></a>  shared_future::wait_for

関連付けられた非同期状態が *ready* になるまで、または指定した時間が経過するまで、現在のスレッドをブロックします。

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>パラメーター

*Rel_time*<br/>
スレッドがブロックする最大の時間間隔を指定する [chrono::duration](../standard-library/duration-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>Remarks

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ *ready* になります。

## <a name="wait_until"></a>  shared_future::wait_until

関連付けられた非同期状態が *ready* になるまで、または指定した時点後まで現在のスレッドをブロックします。

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>パラメーター

*Abs_time*<br/>
スレッドがブロックを解除できる時間を指定する [chrono::time_point](../standard-library/time-point-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>Remarks

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ、準備完了になります。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
