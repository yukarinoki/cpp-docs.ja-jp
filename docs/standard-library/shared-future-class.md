---
title: shared_future クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
dev_langs:
- C++
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 2ac125b068de5111a2b98800956c12a0c979737f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859665"
---
# <a name="sharedfuture-class"></a>shared_future クラス

*非同期のリターン オブジェクト*を記述します。 [future](../standard-library/future-class.md) オブジェクトとは異なり、*非同期プロバイダー*を任意の数の `shared_future` オブジェクトに関連付けることができます。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>コメント

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

## <a name="requirements"></a>要件

**ヘッダー:** \<将来 >

**名前空間:** std

## <a name="get"></a>  shared_future::get

*関連付けられた非同期状態*に格納されている結果を取得します。

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>コメント

結果が例外の場合は、そのメソッドが再スローします。 それ以外の場合、結果が返されます。

結果を取得する前に、このメソッドは、関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。

部分的特殊化 `shared_future<Ty&>` では、格納されている値は、実質的には*非同期プロバイダー*に戻り値として渡されたオブジェクトへの参照です。

特殊化 `shared_future<void>` には格納されている値が存在しないため、このメソッドは `void` を返します。

## <a name="op_eq"></a>  shared_future::operator=

指定したオブジェクトから、*関連付けられた非同期状態*を転送します。

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>パラメーター

`Right` A`shared_future`オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>コメント

最初の演算子では、操作の後、`Right` に関連付けられた非同期状態は既にありません。

2 番目のメソッドでは、`Right` は関連付けられた非同期状態を維持します。

## <a name="shared_future"></a>  shared_future::shared_future コンストラクター

`shared_future` オブジェクトを構築します。

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>パラメーター

`Right` A[将来](../standard-library/future-class.md)または`shared_future`オブジェクト。

### <a name="remarks"></a>コメント

1 つ目のコンストラクターは、*関連付けられた非同期状態*がない `shared_future` オブジェクトを構築します。

2 つ目および 3 つ目のコンストラクターは、`shared_future` オブジェクトを構築し、`Right` から関連付けられた非同期状態を転送します。 `Right` に関連付けられた非同期状態は既にありません。

4 つ目のコンストラクターは、`Right` と同じ関連付けられた非同期状態を持つ `shared_future` オブジェクトを構築します。

## <a name="valid"></a>  shared_future::valid

オブジェクトが*関連付けられた非同期状態*であるかどうかを指定します。

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>戻り値

オブジェクトが関連付けられた非同期状態である場合は `true` を返します。それ以外の場合は `false` を返します。

## <a name="wait"></a>  shared_future::wait

*関連付けられた非同期状態*が *ready* になるまで、現在のスレッドをブロックします。

```cpp
void wait() const;
```

### <a name="remarks"></a>コメント

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ、準備完了になります。

## <a name="wait_for"></a>  shared_future::wait_for

関連付けられた非同期状態が *ready* になるまで、または指定した時間が経過するまで、現在のスレッドをブロックします。

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>パラメーター

`Rel_time` A [:duration](../standard-library/duration-class.md)最大時間間隔を指定するオブジェクトをそのスレッドはブロックされます。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>コメント

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ *ready* になります。

## <a name="wait_until"></a>  shared_future::wait_until

関連付けられた非同期状態が *ready* になるまで、または指定した時点後まで現在のスレッドをブロックします。

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>パラメーター

`Abs_time` A [chrono::time_point](../standard-library/time-point-class.md)するまで、スレッド ブロックを解除できます時間を指定するオブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>コメント

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ、準備完了になります。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
