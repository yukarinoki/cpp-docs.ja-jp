---
title: '&lt;atomic&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- atomic/std::atomic_compare_exchange_strong
- atomic/std::atomic_compare_exchange_strong_explicit
- atomic/std::atomic_compare_exchange_weak
- atomic/std::atomic_compare_exchange_weak_explicit
- atomic/std::atomic_exchange
- atomic/std::atomic_exchange_explicit
- atomic/std::atomic_fetch_add
- atomic/std::atomic_fetch_add_explicit
- atomic/std::atomic_fetch_and
- atomic/std::atomic_fetch_and_explicit
- atomic/std::atomic_fetch_or
- atomic/std::atomic_fetch_or_explicit
- atomic/std::atomic_fetch_sub
- atomic/std::atomic_fetch_sub_explicit
- atomic/std::atomic_fetch_xor
- atomic/std::atomic_fetch_xor_explicit
- atomic/std::atomic_flag_clear
- atomic/std::atomic_flag_clear_explicit
- atomic/std::atomic_flag_test_and_set
- atomic/std::atomic_flag_test_and_set_explicit
- atomic/std::atomic_init
- atomic/std::atomic_is_lock_free
- atomic/std::atomic_load
- atomic/std::atomic_load_explicit
- atomic/std::atomic_signal_fence
- atomic/std::atomic_store
- atomic/std::atomic_store_explicit
- atomic/std::atomic_thread_fence
- atomic/std::kill_dependency
ms.assetid: 5c53b4f8-6ff5-47d7-beb2-2d6ee3c6ea89
author: mikeblome
ms.author: mblome
helpviewer_keywords:
- std::atomic_compare_exchange_strong [C++]
- std::atomic_compare_exchange_strong_explicit [C++]
- std::atomic_compare_exchange_weak [C++]
- std::atomic_compare_exchange_weak_explicit [C++]
- std::atomic_exchange [C++]
- std::atomic_exchange_explicit [C++]
- std::atomic_fetch_add [C++]
- std::atomic_fetch_add_explicit [C++]
- std::atomic_fetch_and [C++]
- std::atomic_fetch_and_explicit [C++]
- std::atomic_fetch_or [C++]
- std::atomic_fetch_or_explicit [C++]
- std::atomic_fetch_sub [C++]
- std::atomic_fetch_sub_explicit [C++]
- std::atomic_fetch_xor [C++]
- std::atomic_fetch_xor_explicit [C++]
- std::atomic_flag_clear [C++]
- std::atomic_flag_clear_explicit [C++]
- std::atomic_flag_test_and_set [C++]
- std::atomic_flag_test_and_set_explicit [C++]
- std::atomic_init [C++]
- std::atomic_is_lock_free [C++]
- std::atomic_load [C++]
- std::atomic_load_explicit [C++]
- std::atomic_signal_fence [C++]
- std::atomic_store [C++]
- std::atomic_store_explicit [C++]
- std::atomic_thread_fence [C++]
- std::kill_dependency [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: 50e70230dd5b8d9aa61f4df8c1288569192048b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848792"
---
# <a name="ltatomicgt-functions"></a>&lt;atomic&gt; 関数

||||
|-|-|-|
|[atomic_compare_exchange_strong](#atomic_compare_exchange_strong)|[atomic_compare_exchange_strong_explicit](#atomic_compare_exchange_strong_explicit)|[atomic_compare_exchange_weak](#atomic_compare_exchange_weak)|
|[atomic_compare_exchange_weak_explicit](#atomic_compare_exchange_weak_explicit)|[atomic_exchange](#atomic_exchange)|[atomic_exchange_explicit](#atomic_exchange_explicit)|
|[atomic_fetch_add](#atomic_fetch_add)|[atomic_fetch_add_explicit](#atomic_fetch_add_explicit)|[atomic_fetch_and](#atomic_fetch_and)|
|[atomic_fetch_and_explicit](#atomic_fetch_and_explicit)|[atomic_fetch_or](#atomic_fetch_or)|[atomic_fetch_or_explicit](#atomic_fetch_or_explicit)|
|[atomic_fetch_sub](#atomic_fetch_sub)|[atomic_fetch_sub_explicit](#atomic_fetch_sub_explicit)|[atomic_fetch_xor](#atomic_fetch_xor)|
|[atomic_fetch_xor_explicit](#atomic_fetch_xor_explicit)|[atomic_flag_clear](#atomic_flag_clear)|[atomic_flag_clear_explicit](#atomic_flag_clear_explicit)|
|[atomic_flag_test_and_set](#atomic_flag_test_and_set)|[atomic_flag_test_and_set_explicit](#atomic_flag_test_and_set_explicit)|[atomic_init](#atomic_init)|
|[atomic_is_lock_free](#atomic_is_lock_free)|[atomic_load](#atomic_load)|[atomic_load_explicit](#atomic_load_explicit)|
|[atomic_signal_fence](#atomic_signal_fence)|[atomic_store](#atomic_store)|[atomic_store_explicit](#atomic_store_explicit)|
|[atomic_thread_fence](#atomic_thread_fence)|[kill_dependency](#kill_dependency)|

## <a name="atomic_compare_exchange_strong"></a>  atomic_compare_exchange_strong

アトミックの比較および交換の操作を実行します。

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`Ty`です。

`Exp` 型の値へのポインター`Ty`です。

`Value` 型の値`Ty`です。

### <a name="return-value"></a>戻り値

値の比較の結果を示す `bool`。

### <a name="remarks"></a>コメント

このメソッドは暗黙の `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) 引数でアトミックを比較し、交換の操作を実行します。 詳細については、「[atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)」を参照してください。

## <a name="atomic_compare_exchange_strong_explicit"></a>  atomic_compare_exchange_strong_explicit

*アトミックの比較および交換*の操作を実行します。

```cpp
template <class T>
inline bool atomic_compare_exchange_strong_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`Ty`です。

`Exp` 型の値へのポインター`Ty`です。

`Value` 型の値`Ty`です。

`Order1` 最初[memory_order](../standard-library/atomic-enums.md#memory_order_enum)引数。

`Order2` 2 番目`memory_order`引数。 `Order2` の値は `memory_order_release` または `memory_order_acq_rel` にすることはできず、`Order1`、の値よりも強くすることもできません。

### <a name="return-value"></a>戻り値

値の比較の結果を示す `bool`。

### <a name="remarks"></a>コメント

*アトミックの比較および交換*の操作は、`Atom` が指す値と `Exp` が指すオブジェクトに格納されている値を比較します。 値が等しい場合、`read-modify-write` 操作を使用して、`Order1` によって指定されたメモリ順序制約を適用して、`atom` で指定されるオブジェクトに格納された値を `Val` と置き換えます。 値が等しくない場合、操作は `Exp` で指定された値を `Atom` に指定されたオブジェクト内に格納された値と置き換え、`Order2` によって指定されたメモリ順序制約を適用します。

## <a name="atomic_compare_exchange_weak"></a>  atomic_compare_exchange_weak

*弱いアトミックの比較および交換*の操作を実行します。

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`Ty`です。

`Exp` 型の値へのポインター`Ty`です。

`Value` 型の値`Ty`です。

### <a name="return-value"></a>戻り値

値の比較の結果を示す `bool`。

### <a name="remarks"></a>コメント

このメソッドは、暗黙の `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) 引数を持つ*弱いアトミックの比較および交換の操作*を実行します。 詳細については、「[atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)」を参照してください。

## <a name="atomic_compare_exchange_weak_explicit"></a>  atomic_compare_exchange_weak_explicit

*弱いアトミックの比較および交換*の操作を実行します。

```cpp
template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`Ty`です。

`Exp` 型の値へのポインター`Ty`です。

`Value` 型の値`Ty`です。

`Order1` 最初[memory_order](../standard-library/atomic-enums.md#memory_order_enum)引数。

`Order2` 2 番目`memory_order`引数。 `Order2` の値は `memory_order_release` または `memory_order_acq_rel` にすることはできず、`Order1` の値よりも強くすることもできません。

### <a name="return-value"></a>戻り値

値の比較の結果を示す `bool`。

### <a name="remarks"></a>コメント

*アトミック比較と交換操作*は、`Atom` が指す値と持つ `Exp` が指すオブジェクトに格納されている値を比較します。 値が等しい場合、操作は `Atom` 操作を使用して、`Val` によって指定されたメモリ順序制約を適用して、`read-modify-write` で指定されるオブジェクトに格納された値を `Order1` と置き換えます。 値が等しくない場合、操作は `Exp` で指定された値を `Atom` に指定されたオブジェクト内に格納された値と置き換え、`Order2` によって指定されたメモリ順序制約を適用します。

比較された値が同一の場合、*弱い*アトミック比較および交換操作は交換を実行します。 ただし、値が同じでない場合、操作による交換の実行は保証されません。

## <a name="atomic_exchange"></a>  atomic_exchange

`Value` を使用して `Atom` の格納されている値を置き換えます。

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`Ty`です。

`Value` 型の値`Ty`です。

### <a name="return-value"></a>戻り値

交換前の `Atom` の格納された値。

### <a name="remarks"></a>コメント

`atomic_exchange` 関数は、`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) を使用して、`Atom` に格納された値を `Value` に交換するために、`read-modify-write` 操作を実行します。

## <a name="atomic_exchange_explicit"></a>  atomic_exchange_explicit

`Atom` に格納されている値を `Value` に置き換えます。

```cpp
template <class Ty>
inline Ty atomic_exchange_explicit(
    volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_exchange_explicit(
    atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`Ty`です。

`Value` 型の値`Ty`です。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。

### <a name="return-value"></a>戻り値

交換前の `Atom` の格納された値。

### <a name="remarks"></a>コメント

`atomic_exchange_explicit` 関数は、`read-modify-write` が指定したメモリの制約内で、`Atom` に格納された値を `Value` に交換するために、`Order` 操作を実行します。

## <a name="atomic_fetch_add"></a>  atomic_fetch_add

`atomic` オブジェクトに格納されている既存の値に値を加算します。

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型へのポインターを格納するオブジェクト`T`です。

`Value` 型の値`ptrdiff_t`です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>コメント

`atomic_fetch_add` 関数は、`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) 制約を使用して、`Atom` に格納されている値に `Value` を自動的に加算するために `read-modify-write` 操作を実行します。

アトミック型が `atomic_address` の場合、`Value` に `ptrdiff_t` 型があり、操作は `char *` として格納されているポインターを処理します。

この操作は、整数型に対してもオーバーロードします。

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a>  atomic_fetch_add_explicit

`atomic` オブジェクトに格納されている既存の値に値を加算します。

```cpp
template <class T>
T* atomic_fetch_add_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_add_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型へのポインターを格納するオブジェクト`T`です。

`Value` 型の値`ptrdiff_t`です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>コメント

`atomic_fetch_add_explicit` 関数は、`Order` が指定した [memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で `Atom` に格納されている値に `Value` をアトミックに加算するために `read-modify-write` 操作を実行します。

アトミック型が `atomic_address` の場合、`Value` に `ptrdiff_t` 型があり、操作は `char *` として格納されているポインターを処理します。

この操作は、整数型に対してもオーバーロードします。

```cpp
integral atomic_fetch_add_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_add_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_and"></a>  atomic_fetch_and

値と `and` オブジェクトに格納されている既存の値にビットごとの `atomic` を実行します。

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`T`です。

`Value` 型の値`T`です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>コメント

`atomic_fetch_and` 関数は、`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) 制約を使用して `Atom` の格納されている値を `Value` のビットごとの `and` と `Atom` に格納されている現在の値を置換する `read-modify-write` 操作を実行します。

## <a name="atomic_fetch_and_explicit"></a>  atomic_fetch_and_explicit

値と `and` オブジェクトに格納されている既存の値のビットごとの `atomic` を実行します。

```cpp
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`T`です。

`Value` 型の値`T`です。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>コメント

`atomic_fetch_and_explicit` 関数は、`read-modify-write` で指定されているメモリ制約内で、`Atom` に格納されている値をビットごとの `and` の `Value` と `Atom` に格納されている現在の値に置換する `Order` 演算を実行します。

## <a name="atomic_fetch_or"></a>  atomic_fetch_or

値と `or` オブジェクトに格納されている既存の値にビットごとの `atomic` を実行します。

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`T`です。

`Value` 型の値`T`です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>コメント

`atomic_fetch_or` 関数は、`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) を使用して `Atom` の格納されている値を `Value` のビットごとの `or` と `Atom` に格納されている現在の値を置換する `read-modify-write` 操作を実行します。

## <a name="atomic_fetch_or_explicit"></a>  atomic_fetch_or_explicit

値と `or` オブジェクトに格納されている既存の値にビットごとの `atomic` を実行します。

```cpp
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`T`です。

`Value` 型の値`T`です。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>コメント

`atomic_fetch_or_explicit` 関数は、`Order` で指定されている [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 制約内で、`Atom` に格納されている値をビットごとの `Value` の `or` と `Atom` に格納されている現在の値に置換する `read-modify-write` 操作を実行します。

## <a name="atomic_fetch_sub"></a>  atomic_fetch_sub

`atomic` オブジェクトに格納されている既存の値から値を減算します。

```cpp
template <class T>
T* atomic_fetch_sub(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;

template <class T>
T* atomic_fetch_sub(
    atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型へのポインターを格納するオブジェクト`T`です。

`Value` 型の値`ptrdiff_t`です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>コメント

`atomic_fetch_sub` 関数は、`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) 制約を使用して、`Atom` に格納されている値から `Value` をアトミックに減算するために `read-modify-write` 操作を実行します。

アトミック型が `atomic_address` の場合、`Value` に `ptrdiff_t` 型があり、操作は `char *` として格納されているポインターを処理します。

この操作は、整数型に対してもオーバーロードします。

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a>  atomic_fetch_sub_explicit

`atomic` オブジェクトに格納されている既存の値から値を減算します。

```cpp
template <class T>
T* atomic_fetch_sub_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_sub_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value, memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型へのポインターを格納するオブジェクト`T`です。

`Value` 型の値`ptrdiff_t`です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>コメント

`atomic_fetch_sub_explicit` 関数は、`Order` が指定した [memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で `Atom` に格納されている値から `Value` をアトミックに減算するために `read-modify-write` 操作を実行します。

アトミック型が `atomic_address` の場合、`Value` に `ptrdiff_t` 型があり、操作は `char *` として格納されているポインターを処理します。

この操作は、整数型に対してもオーバーロードします。

```cpp
integral atomic_fetch_sub_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_sub_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_xor"></a>  atomic_fetch_xor

値と `exclusive or` オブジェクトに格納されている既存の値にビットごとの `atomic` を実行します。

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`T`です。

`Value` 型の値`T`です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>コメント

`atomic_fetch_xor` 関数は、`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) を使用して `Atom` の格納されている値を `Value` のビットごとの `exclusive or` と `Atom` に格納されている現在の値を置換する `read-modify-write` 操作を実行します。

## <a name="atomic_fetch_xor_explicit"></a>  atomic_fetch_xor_explicit

値と `exclusive or` オブジェクトに格納されている既存の値にビットごとの `atomic` を実行します。

```cpp
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`T`です。

`Value` 型の値`T`です。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>コメント

`atomic_fetch_xor_explicit` 関数は、`Order` で指定されている [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 制約内で、`Atom` に格納されている値をビットごとの `Value` の `exclusive or` と `Atom` に格納されている現在の値に置換する `read-modify-write` 演算を実行します。

## <a name="atomic_flag_clear"></a>  atomic_flag_clear

`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) の範囲内で、[atomic_flag](../standard-library/atomic-flag-structure.md) オブジェクトの `bool` フラグを `false` に設定します。

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>パラメーター

`Flag` ポインター、`atomic_flag`オブジェクト。

## <a name="atomic_flag_clear_explicit"></a>  atomic_flag_clear_explicit

指定された [memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で、[atomic_flag](../standard-library/atomic-flag-structure.md) オブジェクトの `bool` フラグを `false` に設定します。

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Flag` ポインター、`atomic_flag`オブジェクト。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。

## <a name="atomic_flag_test_and_set"></a>  atomic_flag_test_and_set

`memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で、[atomic_flag](../standard-library/atomic-flag-structure.md) オブジェクトの `bool` フラグを `true` に設定します。

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>パラメーター

`Flag` ポインター、`atomic_flag`オブジェクト。

### <a name="return-value"></a>戻り値

`Flag` の初期値になります。

## <a name="atomic_flag_test_and_set_explicit"></a>  atomic_flag_test_and_set_explicit

指定された [memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で、[atomic_flag](../standard-library/atomic-flag-structure.md) オブジェクトの `bool` フラグを `true` に設定します。

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Flag` ポインター、`atomic_flag`オブジェクト。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。

### <a name="return-value"></a>戻り値

`Flag` の初期値になります。

## <a name="atomic_init"></a>  atomic_init

`atomic` オブジェクトに格納されている値を設定します。

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`Ty`です。

`Value` 型の値`Ty`です。

### <a name="remarks"></a>コメント

`atomic_init` はアトミック操作ではありません。 これはスレッド セーフではありません。

## <a name="atomic_is_lock_free"></a>  atomic_is_lock_free

`atomic` オブジェクトに対するアトミック操作が*ロック制御不要*であるかどうかを指定します。

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納するオブジェクト`T`です。

### <a name="return-value"></a>戻り値

`Atom` に対するアトミック操作がロック制御不要の場合は `true`、それ以外の場合は `false`。

### <a name="remarks"></a>コメント

その型に対してロックを使用するアトミック操作がない場合、atomic 型はロック制御不要になります。 この関数が true を返す場合、その型はシグナル ハンドラーで使用しても安全です。

## <a name="atomic_load"></a>  atomic_load

`atomic` オブジェクトに格納されている値を取得します。

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納しているオブジェクト`Ty`です。

### <a name="return-value"></a>戻り値

`Atom` に格納された取得された値。

### <a name="remarks"></a>コメント

`atomic_load` は暗黙的に `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) を使用します。

## <a name="atomic_load_explicit"></a>  atomic_load_explicit

指定された [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 内の `atomic` オブジェクトに格納されている値を取得します。

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納しているオブジェクト`Ty`です。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。 `memory_order_release` または `memory_order_acq_rel` を使用しないでください。

### <a name="return-value"></a>戻り値

`Atom` に格納された取得された値。

## <a name="atomic_signal_fence"></a>  atomic_signal_fence

同じスレッドで実行されるシグナル ハンドラーを持つ呼び出し元のスレッドで、他のフェンス間で (読み込み/ストア操作間の命令を実装するメモリの同期プリミティブである) *フェンス*として機能します。

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Order` メモリ オーダリングのフェンスの種類を決定する制約です。

### <a name="remarks"></a>コメント

`Order` 引数により、フェンスの種類が決まります。

|||
|-|-|
|`memory_order_relaxed`|フェンスは無効です。|
|`memory_order_consume`|フェンスは取得フェンスです。|
|`memory_order_acquire`|フェンスは取得フェンスです。|
|`memory_order_release`|フェンスは解放フェンスです。|
|`memory_order_acq_rel`|フェンスは取得フェンスと解放フェンスの両方です。|
|`memory_order_seq_cst`|フェンスは取得フェンスと解放フェンスの両方であり、順番に一貫性があります。|

## <a name="atomic_store"></a>  atomic_store

アトミック オブジェクトに値をアトミックに格納します。

```cpp
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` 型の値を格納しているアトミック オブジェクトへのポインター`Ty`です。

`Value` 型の値`Ty`です。

### <a name="remarks"></a>コメント

`atomic_store` は `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で `Atom` が指すオブジェクト内に `Value` を格納します。

## <a name="atomic_store_explicit"></a>  atomic_store_explicit

アトミック オブジェクトに値をアトミックに格納します。

```cpp
template <class Ty>
inline Ty atomic_store_explicit(
    const volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_store_explicit(
    const atomic<Ty>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Atom` ポインター、`atomic`型の値を格納しているオブジェクト`Ty`です。

`Value` 型の値`Ty`です。

`Order` A [memory_order](../standard-library/atomic-enums.md#memory_order_enum)です。 `memory_order_consume`、`memory_order_acquire`、または `memory_order_acq_rel` を使用しないでください。

### <a name="remarks"></a>コメント

`atomic_store` は `Value` で指定された `Atom` 内で `memory_order` が指すオブジェクト内に `Order` を格納します。

## <a name="atomic_thread_fence"></a>  atomic_thread_fence

関連付けられているアトミックな操作なしで、読み込み/ストア操作間の命令を実装するメモリの同期プリミティブである*フェンス*として機能します。

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

`Order` メモリ オーダリングのフェンスの種類を決定する制約です。

### <a name="remarks"></a>コメント

`Order` 引数により、フェンスの種類が決まります。

|||
|-|-|
|`memory_order_relaxed`|フェンスは無効です。|
|`memory_order_consume`|フェンスは取得フェンスです。|
|`memory_order_acquire`|フェンスは取得フェンスです。|
|`memory_order_release`|フェンスは解放フェンスです。|
|`memory_order_acq_rel`|フェンスは取得フェンスと解放フェンスの両方です。|
|`memory_order_seq_cst`|フェンスは取得フェンスと解放フェンスの両方であり、順番に一貫性があります。|

## <a name="kill_dependency"></a>  kill_dependency

依存関係を削除します。

```cpp
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```

### <a name="parameters"></a>パラメーター

`Arg` 型の値`Ty`です。

### <a name="return-value"></a>戻り値

戻り値は `Arg` です。 `Arg` の評価は関数呼び出しに依存関係を伝達しません。 可能な依存関係チェーンを分割することで、関数はより効率的なコードを生成することをコンパイラに許可できます。

## <a name="see-also"></a>関連項目

[\<atomic>](../standard-library/atomic.md)<br/>
