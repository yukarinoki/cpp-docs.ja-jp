---
title: packaged_task クラス
ms.date: 11/04/2016
f1_keywords:
- future/std::packaged_task
- future/std::packaged_task::packaged_task
- future/std::packaged_task::get_future
- future/std::packaged_task::make_ready_at_thread_exit
- future/std::packaged_task::reset
- future/std::packaged_task::swap
- future/std::packaged_task::valid
- future/std::packaged_task::operator()
- future/std::packaged_task::operator bool
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
helpviewer_keywords:
- std::packaged_task [C++]
- std::packaged_task [C++], packaged_task
- std::packaged_task [C++], get_future
- std::packaged_task [C++], make_ready_at_thread_exit
- std::packaged_task [C++], reset
- std::packaged_task [C++], swap
- std::packaged_task [C++], valid
ms.openlocfilehash: eb171e09451e16e89716dfdc44ed6c611e2d2280
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372123"
---
# <a name="packaged_task-class"></a>packaged_task クラス

呼び出しラッパーであり、呼び出しシグネチャが `Ty(ArgTypes...)` である*非同期プロバイダー*を記述します。 *関連付けられた非同期状態*は、潜在的な結果に加えて、呼び出し可能オブジェクトのコピーを保持します。

## <a name="syntax"></a>構文

```cpp
template <class>
class packaged_task;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[packaged_task](#packaged_task)|`packaged_task` オブジェクトを構築します。|
|[packaged_task::~packaged_taskデストラクタ](#dtorpackaged_task_destructor)|`packaged_task` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_future](#get_future)|同じ関連付けられた非同期状態の [future](../standard-library/future-class.md) オブジェクトを返します。|
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|関連付けられた非同期状態に格納された呼び出し可能オブジェクトを呼び出し、戻り値をアトミックに格納します。|
|[リセット](#reset)|関連付けられた非同期状態を置き換えます。|
|[スワップ](#swap)|関連付けられた非同期状態を、指定したオブジェクトのものと交換します。|
|[有効](#valid)|オブジェクトが関連付けられた非同期状態であるかどうかを指定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[packaged_task:演算子=](#op_eq)|関連付けられた非同期状態から、指定したオブジェクトを転送します。|
|[packaged_task::演算子()](#op_call)|関連付けられた非同期状態に格納された呼び出し可能オブジェクトを呼び出し、戻り値をアトミックに格納し、状態を *ready* に設定します。|
|[packaged_task::operator bool](#op_bool)|オブジェクトが関連付けられた非同期状態であるかどうかを指定します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<将来の>

**名前空間:** std

## <a name="packaged_taskget_future"></a><a name="get_future"></a>packaged_task::get_future

同じ*関連付けられた非同期状態*の `future<Ty>` 型のオブジェクトを返します。

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>解説

`packaged_task` オブジェクトが関連付けられた非同期状態ではない場合、このメソッドはエラー コード `no_state` で [future_error](../standard-library/future-error-class.md) をスローします。

このメソッドが同じ関連付けられた非同期状態の `packaged_task` オブジェクトに対して既に呼び出されている場合、このメソッドはエラー コード `future_already_retrieved` で `future_error` をスローします。

## <a name="packaged_taskmake_ready_at_thread_exit"></a><a name="make_ready_at_thread_exit"></a>packaged_task::make_ready_at_thread_exit

*関連付けられた非同期状態*に格納された呼び出し可能オブジェクトを呼び出し、戻り値をアトミックに格納します。

```cpp
void make_ready_at_thread_exit(ArgTypes... args);
```

### <a name="remarks"></a>解説

`packaged_task` オブジェクトが関連付けられた非同期状態ではない場合、このメソッドはエラー コード `no_state` で [future_error](../standard-library/future-error-class.md) をスローします。

このメソッドまたは [make_ready_at_thread_exit](#make_ready_at_thread_exit) が同じ関連付けられた非同期状態の `packaged_task` オブジェクトに対して既に呼び出されている場合、このメソッドはエラー コード `promise_already_satisfied` で `future_error` をスローします。

それ以外の場合、この演算子は `INVOKE(fn, args..., Ty)` を呼び出します。ここで、*fn* は関連付けられた非同期状態に格納された呼び出し可能オブジェクトです。 すべての戻り値は、関連付けられた非同期状態の返された結果としてアトミックに格納されます。

[packaged_task::operator()](#op_call) とは対照的に、呼び出し元のスレッドのスレッド ローカルのオブジェクトがすべて破棄されるまでは、関連付けられた非同期状態は `ready` に設定されません。 通常、関連付けられた非同期状態でブロックされたスレッドは、呼び出し元のスレッドが終了するまでブロック解除されません。

## <a name="packaged_taskoperator"></a><a name="op_eq"></a>packaged_task:演算子=

指定したオブジェクトから*関連付けられた非同期状態*を転送します。

```cpp
packaged_task& operator=(packaged_task&& Right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`packaged_task` オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>解説

操作の後 *、Right*には非同期状態が関連付けなくなります。

## <a name="packaged_taskoperator"></a><a name="op_call"></a>packaged_task::演算子()

*関連付けられた非同期状態*に格納されている呼び出し可能オブジェクトを呼び出し、返された値をアトミックに格納し、状態を*ready*に設定します。

```cpp
void operator()(ArgTypes... args);
```

### <a name="remarks"></a>解説

`packaged_task` オブジェクトが関連付けられた非同期状態ではない場合、このメソッドはエラー コード `no_state` で [future_error](../standard-library/future-error-class.md) をスローします。

このメソッドまたは [make_ready_at_thread_exit](#make_ready_at_thread_exit) が同じ関連付けられた非同期状態の `packaged_task` オブジェクトに対して既に呼び出されている場合、このメソッドはエラー コード `promise_already_satisfied` で `future_error` をスローします。

それ以外の場合、この演算子は `INVOKE(fn, args..., Ty)` を呼び出します。ここで、*fn* は関連付けられた非同期状態に格納された呼び出し可能オブジェクトです。 すべての戻り値は、関連付けられた非同期状態の返された結果としてアトミックに格納され、状態が ready に設定されます。 その結果、関連付けられた非同期状態でブロックされているすべてのスレッドがブロック解除されます。

## <a name="packaged_taskoperator-bool"></a><a name="op_bool"></a>packaged_task::オペレーターブール

オブジェクトが `associated asynchronous state` であるかどうかを指定します。

```cpp
operator bool() const noexcept;
```

### <a name="return-value"></a>戻り値

オブジェクトに非同期状態が関連付けられている場合は**true、** その他の値は true です。それ以外の場合**は false。**

## <a name="packaged_taskpackaged_task-constructor"></a><a name="packaged_task"></a>packaged_task::packaged_taskコンストラクタ

`packaged_task` オブジェクトを構築します。

```cpp
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`packaged_task` オブジェクト。

*Alloc*\
メモリ割り当て。 詳細については、「[\<アロケーター>](../standard-library/allocators-header.md)」を参照してください。

*Fn*\
関数オブジェクトを指定します。

### <a name="remarks"></a>解説

最初のコンストラクターは、`packaged_task`*関連付けられた非同期状態*を持たないオブジェクトを構築します。

2 番目のコンストラクターは`packaged_task`、オブジェクトを構築し、関連する非同期状態を*Right*から転送します。 操作の後 *、Right*には非同期状態が関連付けなくなります。

3 番目のコンストラクターは`packaged_task`、関連付けられた非同期状態に格納されている*fn*のコピーを持つオブジェクトを構築します。

4 番目のコンストラクターは`packaged_task`、関連付けられた非同期状態に格納されている*fn*のコピーを持`alloc`ち、メモリの割り当てを使用するオブジェクトを構築します。

## <a name="packaged_taskpackaged_task-destructor"></a><a name="dtorpackaged_task_destructor"></a>packaged_task::~packaged_taskデストラクタ

`packaged_task` オブジェクトを破棄します。

```cpp
~packaged_task();
```

### <a name="remarks"></a>解説

*関連付けられた非同期状態*が*準備完了*ではない場合、デストラクターは、関連付けられた非同期状態の結果としてエラー コード `broken_promise` で [future_error](../standard-library/future-error-class.md) 例外を格納し、関連付けられた非同期状態でブロックされているすべてのスレッドがブロック解除されます。

## <a name="packaged_taskreset"></a><a name="reset"></a>packaged_task::リセット

新しい*関連付けられた非同期状態*を使用して、既存の関連付けられた非同期状態を置き換えます。

```cpp
void reset();
```

### <a name="remarks"></a>解説

実際には、このメソッドは `*this = packaged_task(move(fn))` を実行します。ここで、*fn* は、このオブジェクトの関連付けられた非同期状態に格納された関数オブジェクトです。 そのため、オブジェクトの状態が削除され、[get_future](#get_future)、[operator()](#op_call)、および [make_ready_at_thread_exit](#make_ready_at_thread_exit) を新しく構築されたオブジェクトでのように呼び出すことができます。

## <a name="packaged_taskswap"></a><a name="swap"></a>packaged_task::スワップ

関連付けられた非同期状態を、指定したオブジェクトのものと交換します。

```cpp
void swap(packaged_task& Right) noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
`packaged_task` オブジェクト。

## <a name="packaged_taskvalid"></a><a name="valid"></a>packaged_task::有効

オブジェクトが `associated asynchronous state` であるかどうかを指定します。

```cpp
bool valid() const;
```

### <a name="return-value"></a>戻り値

オブジェクトに非同期状態が関連付けられている場合は**true、** その他の値は true です。それ以外の場合**は false。**

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<将来の>](../standard-library/future.md)
