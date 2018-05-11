---
title: promise クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::promise
- future/std::promise::promise
- future/std::promise::get_future
- future/std::promise::set_exception
- future/std::promise::set_exception_at_thread_exit
- future/std::promise::set_value
- future/std::promise::set_value_at_thread_exit
- future/std::promise::swap
dev_langs:
- C++
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::promise [C++]
- std::promise [C++], promise
- std::promise [C++], get_future
- std::promise [C++], set_exception
- std::promise [C++], set_exception_at_thread_exit
- std::promise [C++], set_value
- std::promise [C++], set_value_at_thread_exit
- std::promise [C++], swap
ms.workload:
- cplusplus
ms.openlocfilehash: ac8508cab7afc7e6614c29b64d78849383f5bc2d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="promise-class"></a>promise クラス

*非同期プロバイダー*を記述します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[promise](#promise)|`promise` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_future](#get_future)|この約束に関連付けられている [future](../standard-library/future-class.md) を返します。|
|[set_exception](#set_exception)|この約束の結果をアトミックに設定して、例外を示します。|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|この約束の結果をアトミックに設定して例外を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します (通常はスレッド終了時)。|
|[set_value](#set_value)|この約束の結果をアトミックに設定して、値を示します。|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|この約束の結果をアトミックに設定して値を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します (通常はスレッド終了時)。|
|[swap](#swap)|この promise の*関連付けられた非同期状態*を、指定した promise オブジェクトの状態と交換します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[promise::operator=](#op_eq)|この約束オブジェクトの共有状態の割り当て。|

## <a name="inheritance-hierarchy"></a>継承階層

`promise`

## <a name="requirements"></a>要件

**ヘッダー:** \<将来 >

**名前空間:** std

## <a name="get_future"></a>  promise::get_future

この promise と同じ*関連付けられた非同期状態*の [future](../standard-library/future-class.md) オブジェクトを返します。

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>コメント

promise オブジェクトが空の場合、このメソッドは `no_state` の [error_code](../standard-library/error-code-class.md) を持つ [future_error](../standard-library/future-error-class.md) をスローします。

このメソッドが同じ関連付けられた非同期状態を持つ約束オブジェクトに対して既に呼び出されている場合、メソッドは `future_error` の `error_code` を持つ `future_already_retrieved` をスローします。

## <a name="op_eq"></a>  promise::operator=

指定した `promise` オブジェクトから*関連付けられた非同期状態*を転送します。

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

`Other` A`promise`オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>コメント

この演算子は `Other` から関連付けられた非同期状態を転送します。 転送後、`Other` は*空*になります。

## <a name="promise"></a>  promise::promise コンストラクター

`promise` オブジェクトを構築します。

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

`Al` メモリ割り当て。 詳細については、「[\<allocators>](../standard-library/allocators-header.md)」をご覧ください。

`Other` A`promise`オブジェクト。

### <a name="remarks"></a>コメント

1 つ目のコンストラクターは、*空の*`promise` オブジェクトを構築します。

2 つ目のコンストラクターは、空の `promise` オブジェクトを構築して、`Al` をメモリの割り当てに使用します。

3 つ目のコンストラクターは、`promise` オブジェクトを構築し、関連付けられた非同期状態を `Other` から転送し、`Other` を空のままにします。

## <a name="set_exception"></a>  promise::set_exception

アトミックに例外をこの `promise` オブジェクトの結果として格納し、*関連付けられた非同期状態*を*準備完了*に設定します。

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>パラメーター

`Exc` [Exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)このメソッドにより例外結果として格納されています。

### <a name="remarks"></a>コメント

`promise` オブジェクトに関連付けられた非同期状態がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。

`set_exception`、[set_exception_at_thread_exit](#set_exception_at_thread_exit)、[set_value](#set_value)、または [set_value_at_thread_exit](#set_value_at_thread_exit) が同じ関連付けられた非同期状態を持つ `promise` オブジェクトに対して呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。

このメソッドの結果として、関連付けられた非同期状態に対してブロックされているすべてのスレッドのブロックが解除されます。

## <a name="set_exception_at_thread_exit"></a>  promise::set_exception_at_thread_exit

この `promise` の結果をアトミックに設定して例外を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します (通常はスレッド終了時)。

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>パラメーター

`Exc` [Exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)このメソッドにより例外結果として格納されています。

### <a name="remarks"></a>コメント

promise オブジェクトに*関連付けられた非同期状態*がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。

[set_exception](#set_exception)、`set_exception_at_thread_exit`、[set_value](#set_value)、または [set_value_at_thread_exit](#set_value_at_thread_exit) が同じ関連付けられた非同期状態を持つ `promise` オブジェクトに対して既に呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。

[set_exception](#set_exception) とは対照的に、このメソッドでは、関連付けられた非同期状態は、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄されるまでは準備完了に設定されません。 通常、関連付けられた非同期状態に対してブロックされたスレッドは、現在のスレッドが終了するまでブロック解除されません。

## <a name="set_value"></a>  promise::set_value

アトミックに値をこの `promise` オブジェクトの結果として格納し、*関連付けられた非同期状態* を*準備完了*に設定します。

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>パラメーター

`Val` 結果として格納される値です。

### <a name="remarks"></a>コメント

`promise` オブジェクトに関連付けられた非同期状態がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。

[set_exception](#set_exception)、[set_exception_at_thread_exit](#set_exception_at_thread_exit)、`set_value`、または [set_value_at_thread_exit](#set_value_at_thread_exit) が同じ関連付けられた非同期状態の `promise` オブジェクトに対して呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。

このメソッドの結果として、関連付けられた非同期状態に対してブロックされているすべてのスレッドのブロックが解除されます。

最初のメソッドは、`Val` が関連付けられた非同期状態にコピーされたときにスローされるすべての例外もスローします。 この状況では、関連付けられた非同期状態は準備完了に設定されません。

2 番目のメソッドは、`Val` が関連付けられた非同期状態に移動されたときにスローされるすべての例外もスローします。 この状況では、関連付けられた非同期状態は準備完了に設定されません。

部分的特殊化 `promise<Ty&>` の場合、格納されている値は、実際には `Val` への参照です。

特殊化 `promise<void>` の場合、格納されている値は存在しません。

## <a name="set_value_at_thread_exit"></a>  promise::set_value_at_thread_exit

アトミックにこの `promise` オブジェクトの結果として値を格納します。

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>パラメーター

`Val` 結果として格納される値です。

### <a name="remarks"></a>コメント

promise オブジェクトに*関連付けられた非同期状態*がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。

[set_exception](#set_exception)、[set_exception_at_thread_exit](#set_exception_at_thread_exit)、[set_value](#set_value)、または `set_value_at_thread_exit` が同じ関連付けられた非同期状態の `promise` オブジェクトに対して呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。

`set_value` とは対照的に、関連付けられた非同期状態は、現在のスレッドのスレッド ローカルのオブジェクトがすべて破棄されるまでは準備完了に設定されません。 通常、関連付けられた非同期状態に対してブロックされたスレッドは、現在のスレッドが終了するまでブロック解除されません。

最初のメソッドは、`Val` が関連付けられた非同期状態にコピーされたときにスローされるすべての例外もスローします。

2 番目のメソッドは、`Val` が関連付けられた非同期状態に移動されたときにスローされるすべての例外もスローします。

部分的特殊化 `promise<Ty&>` の場合、格納されている値は、事実上 `Val` への参照です。

特殊化 `promise<void>` の場合、格納されている値は存在しません。

## <a name="swap"></a>  promise::swap

この約束オブジェクトに*関連付けられた非同期状態*を指定したオブジェクトのものと交換します。

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

`Other` A`promise`オブジェクト。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
