---
title: '&lt;atomic&gt; 関数'
ms.date: 07/11/2018
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
ms.openlocfilehash: 6ec4ff879b70e4d2cc16a3328217660db695e859
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533758"
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

*Atom*<br/>
ポインター、*アトミック*型の値を格納するオブジェクト`Ty`します。

*Exp*<br/>
`Ty` 型の値へのポインター。

*[値]*<br/>
`Ty` 型の値。

### <a name="return-value"></a>戻り値

**true**値が等しい場合**false**します。

### <a name="remarks"></a>Remarks

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

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*Exp*<br/>
`Ty` 型の値へのポインター。

*[値]*<br/>
`Ty` 型の値。

*Order1*<br/>
最初の [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 引数。

*Order2*<br/>
2 番目の `memory_order` 引数。 値*Order2*することはできません`memory_order_release`または`memory_order_acq_rel`の値よりも強力にすることはできません*Order1*します。

### <a name="return-value"></a>戻り値

**true**値が等しい場合**false**します。

### <a name="remarks"></a>Remarks

*アトミック比較および交換操作*が指すオブジェクトに格納されている値と比較します*Atom*が指す値に対して*Exp*します。場合は、値が等しい、値が指すオブジェクトに格納されている*atom*は置き換え*値*を使用して、`read-modify-write`操作しているメモリ順序制約を適用します。指定された*Order1*します。 操作が指す値を置換値が等しくない場合は、 *Exp*が指すオブジェクトに格納されている値を持つ*Atom*はメモリ順序制約を適用指定された*Order2*します。

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

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*Exp*<br/>
`Ty` 型の値へのポインター。

*[値]*<br/>
`Ty` 型の値。

### <a name="return-value"></a>戻り値

**true**値が等しい場合**false**します。

### <a name="remarks"></a>Remarks

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

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*Exp*<br/>
`Ty` 型の値へのポインター。

*[値]*<br/>
`Ty` 型の値。

*Order1*<br/>
最初の [memory_order](../standard-library/atomic-enums.md#memory_order_enum) 引数。

*Order2*<br/>
2 番目の `memory_order` 引数。 値*Order2*することはできません`memory_order_release`または`memory_order_acq_rel`の値よりも強くすることも*Order1*します。

### <a name="return-value"></a>戻り値

**true**値が等しい場合**false**します。

### <a name="remarks"></a>Remarks

強力と脆弱の両方の種類、*アトミック比較および交換操作*保証を保存しない新しい値、予想されると、現在の値が等しくない場合。 予想されると、現在の値が等しい場合に、新しい値を格納、強力なフレーバーが保証されます。 弱いフレーバーが返される場合があります**false**現在と予期される値が等しい場合でも、新しい値が格納されません。 つまり、関数は**false**が予期される値の後で調べることがあります、変更はありませんし、等価比較が必要があります。

## <a name="atomic_exchange"></a>  atomic_exchange

使用して*値*の格納されている値を置換する*Atom*します。

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>パラメーター

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*[値]*<br/>
`Ty` 型の値。

### <a name="return-value"></a>戻り値

格納されている値*Atom*交換する前にします。

### <a name="remarks"></a>Remarks

`atomic_exchange`関数の実行、`read-modify-write`に格納されている値を交換する操作*Atom*で*値*を使用して、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_exchange_explicit"></a>  atomic_exchange_explicit

ストアドの値の置換*Atom*で*値*します。

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

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*[値]*<br/>
`Ty` 型の値。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

格納されている値*Atom*交換する前にします。

### <a name="remarks"></a>Remarks

`atomic_exchange_explicit`関数の実行、`read-modify-write`に格納されている値を交換する操作*Atom*で*値*で指定されているメモリ制約内で*順序*します。

## <a name="atomic_fetch_add"></a>  atomic_fetch_add

`atomic` オブジェクトに格納されている既存の値に値を加算します。

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>パラメーター

*Atom*<br/>
`atomic` 型のポインターが格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`ptrdiff_t` 型の値。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>Remarks

`atomic_fetch_add`関数を実行、`read-modify-write`操作をアトミックに加算する*値*で格納されている値に*Atom*を使用して、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

場合、atomic 型は`atomic_address`、*値*型を持つ`ptrdiff_t`操作は、格納されたポインターとして処理し、`char *`します。

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

*Atom*<br/>
`atomic` 型のポインターが格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`ptrdiff_t` 型の値。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>Remarks

`atomic_fetch_add_explicit`関数の実行、`read-modify-write`操作をアトミックに加算する*値*で格納されている値に*Atom*内で、 [memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約指定されている`Order`します。

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

*Atom*<br/>
`atomic` 型の値が格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`T` 型の値。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>Remarks

`atomic_fetch_and`関数を実行、`read-modify-write`の格納されている値を置き換える操作*Atom*をビットごと`and`の*値*に格納されている現在の値と*Atom*を使用して、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

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

*Atom*<br/>
`atomic` 型の値が格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`T` 型の値。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>Remarks

`atomic_fetch_and_explicit`関数を実行、`read-modify-write`の格納されている値を置き換える操作*Atom*をビットごと`and`の*値*に格納されている現在の値と*Atom*で指定されているメモリ制約内で*順序*します。

## <a name="atomic_fetch_or"></a>  atomic_fetch_or

値と `or` オブジェクトに格納されている既存の値にビットごとの `atomic` を実行します。

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>パラメーター

*Atom*<br/>
`atomic` 型の値が格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`T` 型の値。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>Remarks

`atomic_fetch_or`関数を実行、`read-modify-write`の格納されている値を置き換える操作*Atom*をビットごと`or`の*値*に格納されている現在の値と*Atom*を使用して、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)します。

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

*Atom*<br/>
`atomic` 型の値が格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`T` 型の値。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>Remarks

`atomic_fetch_or_explicit`関数を実行、`read-modify-write`の格納されている値を置き換える操作*Atom*をビットごと`or`の*値*に格納されている現在の値と*Atom*内で、 [memory_order](../standard-library/atomic-enums.md#memory_order_enum)で指定された制約*順序*します。

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

*Atom*<br/>
`atomic` 型のポインターが格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`ptrdiff_t` 型の値。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>Remarks

`atomic_fetch_sub`関数の実行、`read-modify-write`操作がアトミックに減算する*値*で格納されている値から*Atom*を使用して、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

場合、atomic 型は`atomic_address`、*値*型を持つ`ptrdiff_t`操作は、格納されたポインターとして処理し、`char *`します。

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

*Atom*<br/>
`atomic` 型のポインターが格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`ptrdiff_t` 型の値。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納されたポインター。

### <a name="remarks"></a>Remarks

`atomic_fetch_sub_explicit`関数の実行、`read-modify-write`操作がアトミックに減算する*値*で格納されている値から*Atom*内で、 [memory_order](../standard-library/atomic-enums.md#memory_order_enum)指定されている制約`Order`します。

場合、atomic 型は`atomic_address`、*値*型を持つ`ptrdiff_t`操作は、格納されたポインターとして処理し、`char *`します。

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

*Atom*<br/>
`atomic` 型の値が格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`T` 型の値。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>Remarks

`atomic_fetch_xor`関数を実行、`read-modify-write`の格納されている値を置き換える操作*Atom*をビットごと`exclusive or`の*値*に格納されている現在の値と*Atom*を使用して、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)します。

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

*Atom*<br/>
`atomic` 型の値が格納された `T` オブジェクトへのポインター。

*[値]*<br/>
`T` 型の値。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

操作の直前にアトミック オブジェクトによって格納された値。

### <a name="remarks"></a>Remarks

`atomic_fetch_xor_explicit`関数を実行、`read-modify-write`の格納されている値を置き換える操作*Atom*をビットごと`exclusive or`の*値*に格納されている現在の値と*Atom*内で、 [memory_order](../standard-library/atomic-enums.md#memory_order_enum)で指定されている制約*順序*します。

## <a name="atomic_flag_clear"></a>  atomic_flag_clear

セット、 **bool**フラグ、 [atomic_flag](../standard-library/atomic-flag-structure.md)オブジェクトを**false**内で、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)します。

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
`atomic_flag` オブジェクトへのポインター。

## <a name="atomic_flag_clear_explicit"></a>  atomic_flag_clear_explicit

セット、 **bool**フラグ、 [atomic_flag](../standard-library/atomic-flag-structure.md)オブジェクトを**false**、指定した[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
`atomic_flag` オブジェクトへのポインター。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

## <a name="atomic_flag_test_and_set"></a>  atomic_flag_test_and_set

セット、 **bool**フラグ、 [atomic_flag](../standard-library/atomic-flag-structure.md)オブジェクトを**true**の制約内で、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)します。

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
`atomic_flag` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

初期値*フラグ*します。

## <a name="atomic_flag_test_and_set_explicit"></a>  atomic_flag_test_and_set_explicit

セット、 **bool**フラグ、 [atomic_flag](../standard-library/atomic-flag-structure.md)オブジェクトを**true**、指定した[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
`atomic_flag` オブジェクトへのポインター。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

初期値*フラグ*します。

## <a name="atomic_init"></a>  atomic_init

`atomic` オブジェクトに格納されている値を設定します。

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>パラメーター

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*[値]*<br/>
`Ty` 型の値。

### <a name="remarks"></a>Remarks

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

*Atom*<br/>
`atomic` 型の値が格納された `T` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

**true**場合に対するアトミック操作*Atom*ロックしない場合は**false**します。

### <a name="remarks"></a>Remarks

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

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

取得した値に格納されている*Atom*します。

### <a name="remarks"></a>Remarks

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

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。 `memory_order_release` または `memory_order_acq_rel` を使用しないでください。

### <a name="return-value"></a>戻り値

取得した値に格納されている*Atom*します。

## <a name="atomic_signal_fence"></a>  atomic_signal_fence

同じスレッドで実行されるシグナル ハンドラーを持つ呼び出し元のスレッドで、他のフェンス間で (読み込み/ストア操作間の命令を実装するメモリの同期プリミティブである) *フェンス*として機能します。

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*<br/>
フェンスの種類を決定するメモリ オーダリングの制約。

### <a name="remarks"></a>Remarks

*順序*引数は、フェンスの種類を決定します。

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

*Atom*<br/>
`Ty` 型の値が格納されたアトミック オブジェクトへのポインター。

*[値]*<br/>
`Ty` 型の値。

### <a name="remarks"></a>Remarks

`atomic_store` 格納*値*が指すオブジェクトに*Atom*内で、 `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

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

*Atom*<br/>
`atomic` 型の値が格納された `Ty` オブジェクトへのポインター。

*[値]*<br/>
`Ty` 型の値。

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。 `memory_order_consume`、`memory_order_acquire`、または `memory_order_acq_rel` を使用しないでください。

### <a name="remarks"></a>Remarks

`atomic_store` 格納*値*が指すオブジェクトに*Atom*内で、`memory_order`で指定された*順序*します。

## <a name="atomic_thread_fence"></a>  atomic_thread_fence

関連付けられているアトミックな操作なしで、読み込み/ストア操作間の命令を実装するメモリの同期プリミティブである*フェンス*として機能します。

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*<br/>
フェンスの種類を決定するメモリ オーダリングの制約。

### <a name="remarks"></a>Remarks

*順序*引数は、フェンスの種類を決定します。

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

*arg*<br/>
`Ty` 型の値。

### <a name="return-value"></a>戻り値

戻り値は*Arg*します。 評価*Arg*関数呼び出しに依存関係を伝達しません。 可能な依存関係チェーンを分割することで、関数はより効率的なコードを生成することをコンパイラに許可できます。

## <a name="see-also"></a>関連項目

[\<atomic>](../standard-library/atomic.md)<br/>
