---
title: atomic 構造体
ms.date: 04/20/2018
f1_keywords:
- atomic/std::atomic
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
ms.openlocfilehash: 8701078f8a034d80dae41eee0d842fb15fd8d3a4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203937"
---
# <a name="atomic-structure"></a>atomic 構造体

*Ty*型の格納された値に対してアトミック操作を実行するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>メンバー

|メンバー|説明|
|----------|-----------------|
|**コンストラクター**||
|[アトミック (atomic)](#atomic)|アトミック オブジェクトを構築します。|
|**オペレーター**||
|[atomic:: operator Ty](#op_ty)|格納されている値を読み取って返します。 ([atomic:: load](#load))|
|[atomic:: operator =](#op_eq)|格納されている値を置き換えるために指定された値を使用します。 ([atomic:: store](#store))|
|[atomic:: operator + +](#op_inc)|格納されている値をインクリメントします。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic:: operator + =](#op_add_eq)|指定した値を格納されている値に加算します。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic:: operator--](#op_dec)|格納されている値をデクリメントします。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic:: operator-=](#op_sub_eq)|指定した値を格納されている値から減算します。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic:: operator&=](#op_and_eq)|指定した値と格納されている値に対してビットごとの and を実行します。 整数の特殊化でのみ使用されます。|
|[atomic:: operator&#124;=](#op_or_eq)|指定した値と格納されている値に対してビットごとの or を実行します。 整数の特殊化でのみ使用されます。|
|[atomic:: operator ^ =](#op_xor_eq)|指定した値と格納されている値に対してビットごとの排他的 or を実行します。 整数の特殊化でのみ使用されます。|
|**関数**||
|[compare_exchange_strong](#compare_exchange_strong)|に対して*atomic_compare_and_exchange*操作を実行 **`this`** し、結果を返します。|
|[compare_exchange_weak](#compare_exchange_weak)|に対して*weak_atomic_compare_and_exchange*操作を実行 **`this`** し、結果を返します。|
|[fetch_add](#fetch_add)|指定した値を格納されている値に加算します。|
|[fetch_and](#fetch_and)|指定した値と格納されている値に対してビットごとの and を実行します。|
|[fetch_or](#fetch_or)|指定した値と格納されている値に対してビットごとの or を実行します。|
|[fetch_sub](#fetch_sub)|指定した値を格納されている値から減算します。|
|[fetch_xor](#fetch_xor)|指定した値と格納されている値に対してビットごとの排他的 or を実行します。|
|[is_lock_free](#is_lock_free)|に対するアトミック操作がロックを解放するかどうかを指定し **`this`** ます。 *lock free* その型に対する分割不可能な操作においてロックが使用される場合、atomic 型は*ロック制御不要*になります。|
|[ロード](#load)|格納されている値を読み取って返します。|
|[store](#store)|格納されている値を置き換えるために指定された値を使用します。|

## <a name="remarks"></a>解説

型*Ty*は、*普通にコピー可能*である必要があります。 つまり、 [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)を使用してそのバイトをコピーするには、元のオブジェクトと等しい有効な*Ty*オブジェクトを生成する必要があります。 [Compare_exchange_weak](#compare_exchange_weak)および[compare_exchange_strong](#compare_exchange_strong)のメンバー関数は、 [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)を使用して2つの*Ty*値が等しいかどうかを判断します。 これらの関数は、 *Ty*定義を使用しません `operator==` 。 のメンバー関数は `atomic` 、 `memcpy` *Ty*型の値をコピーするために使用します。

すべてのポインター型に対して、部分的特殊化 ( **atomic \<Ty \*> **) が存在します。 特殊化により、マネージド ポインター値のオフセットの加算またはマネージド ポインター値からのオフセットの減算が可能になります。 算術演算は型の引数を受け取り、 `ptrdiff_t` 通常のアドレス演算との一貫性を確保するために、 *Ty*のサイズに従ってその引数を調整します。

を除くすべての整数型に特殊化が存在し **`bool`** ます。 それぞれの特殊化には、分割不可能な算術演算および論理演算のための豊富な一連のメソッドが用意されています。

||||
|-|-|-|
|**アトミック (atomic)\<char>**|**アトミック (atomic)\<signed char>**|**アトミック (atomic)\<unsigned char>**|
|**アトミック (atomic)\<char16_t>**|**アトミック (atomic)\<char32_t>**|**アトミック (atomic)\<wchar_t>**|
|**アトミック (atomic)\<short>**|**アトミック (atomic)\<unsigned short>**|**アトミック (atomic)\<int>**|
|**アトミック (atomic)\<unsigned int>**|**アトミック (atomic)\<long>**|**アトミック (atomic)\<unsigned long>**|
|**アトミック (atomic)\<long long>**|**アトミック (atomic)\<unsigned long long>**|

整数の特殊化は、対応する `atomic_integral` 型から派生します。 たとえば、 **atomic \<unsigned int> **はから派生 `atomic_uint` しています。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<atomic>

**名前空間:** std

## <a name="atomicatomic"></a><a name="atomic"></a>atomic:: atomic

アトミック オブジェクトを構築します。

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
初期化値。

### <a name="remarks"></a>解説

アトミック オブジェクトをコピーまたは移動することはできません。

Atomic のインスタンス化であるオブジェクトは \<*Ty*> 、集約の初期化を使用するのではなく、型*Ty*の引数を受け取るコンストラクターによってのみ初期化できます。 ただし、atomic_integral オブジェクトは、集計の初期化を使用することによってのみ初期化できます。

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="atomicoperator-ty"></a><a name="op_ty"></a>atomic:: operator *Ty*

テンプレートに指定された型の演算子である atomic \<*Ty*> 。 ** \* この**に格納されている値を取得します。

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>解説

この操作では、 `memory_order_seq_cst` [memory_order](atomic-enums.md)を適用します。

## <a name="atomicoperator"></a><a name="op_eq"></a>atomic:: operator =

指定された値を格納します。

```cpp
Ty operator=(
   Ty Value
) volatile noexcept;
Ty operator=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*オブジェクト。

### <a name="return-value"></a>戻り値

*値*を返します。

## <a name="atomicoperator"></a><a name="op_inc"></a>atomic:: operator + +

格納されている値をインクリメントします。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>戻り値

最初の2つの演算子は、インクリメントされた値を返します。最後の2つの演算子は、インクリメントの前に値を返します。 演算子は memory_order を使用し `memory_order_seq_cst` [memory_order](atomic-enums.md)ます。

## <a name="atomicoperator"></a><a name="op_add_eq"></a>atomic:: operator + =

指定した値を格納されている値に加算します。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator+=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator+=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
整数またはポインターの値。

### <a name="return-value"></a>戻り値

加算の結果を格納する*Ty*オブジェクト。

### <a name="remarks"></a>解説

この演算子は、 `memory_order_seq_cst` [memory_order](atomic-enums.md)を使用します。

## <a name="atomicoperator--"></a><a name="op_dec"></a>atomic:: operator--

格納されている値をデクリメントします。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>戻り値

最初の2つの演算子は、デクリメントされた値を返します。最後の2つの演算子は、デクリメントの前に値を返します。 演算子は memory_order を使用し `memory_order_seq_cst` [memory_order](atomic-enums.md)ます。

## <a name="atomicoperator-"></a><a name="op_sub_eq"></a>atomic:: operator-=

指定した値を格納されている値から減算します。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator-=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator-=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
整数またはポインターの値。

### <a name="return-value"></a>戻り値

減算の結果を格納している*Ty*オブジェクト。

### <a name="remarks"></a>解説

この演算子は、 `memory_order_seq_cst` [memory_order](atomic-enums.md)を使用します。

## <a name="atomicoperator"></a><a name="op_and_eq"></a>atomic:: operator&=

指定した値と、 ** \* この**の格納された値に対してビットごとの and を実行します。 整数の特殊化でのみ使用されます。

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

### <a name="return-value"></a>戻り値

ビットごとの and の結果。

### <a name="remarks"></a>解説

この演算子は、読み取り/書き込み操作を実行して、 ** \* この**の格納された値を、memory_order の制約内で、*値*のビットごとの and と、 ** \* この**に格納されている現在の値に置き換え `memory_order_seq_cst` [memory_order](atomic-enums.md)ます。

## <a name="atomicoperator124"></a><a name="op_or_eq"></a>atomic:: operator&#124;=

指定した値と、 ** \* この**の格納された値に対してビットごとの or を実行します。 整数の特殊化でのみ使用されます。

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

### <a name="return-value"></a>戻り値

ビットごとの or の結果。

### <a name="remarks"></a>解説

この演算子は、読み取り/書き込み操作を実行して、 ** \* この**の格納されている値を、memory_order 制約の制約内で、ビットごとの or*値*と、 ** \* この**に格納されている現在の値に置き換え `memory_order_seq_cst` [memory_order](atomic-enums.md)ます。

## <a name="atomicoperator"></a><a name="op_xor_eq"></a>atomic:: operator ^ =

指定した値と、 ** \* この**の格納された値に対してビットごとの排他的 or を実行します。 整数の特殊化でのみ使用されます。

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

### <a name="return-value"></a>戻り値

ビットごとの排他的 or の結果。

### <a name="remarks"></a>解説

この演算子は、読み取り/書き込み操作を実行して、 ** \* この**の格納されている値を、memory_order 制約の制約内で、ビットごとの排他的 or*値*と、 ** \* この**に格納されている現在の値に置き換え `memory_order_seq_cst` [memory_order](atomic-enums.md)ます。

## <a name="atomiccompare_exchange_strong"></a><a name="compare_exchange_strong"></a>atomic:: compare_exchange_strong

** \* この**に対してアトミックの比較および交換操作を実行します。

```cpp
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*期限*\
*Ty*型の値。

*数値*\
*Ty*型の値。

*Order1*\
1番目 `memory_order` の引数。

*Order2*\
2 番目の `memory_order` 引数。

### <a name="return-value"></a>戻り値

**`bool`** 値の比較の結果を示す。

### <a name="remarks"></a>解説

このアトミックの比較および交換操作では、 ** \* この**に格納されている値と*Exp*を比較します。値が等しい場合、操作は、 ** \* この**に格納されている値を、読み取り/書き込み操作を使用し、 *Order1*で指定されたメモリ順序制約を適用して、*値*に置き換えます。 値が等しくない場合、この操作は、 ** \* この**に格納されている値を使用して*Exp*を置き換え、 *Order2*で指定されているメモリ順序制約を適用します。

2番目のを持たないオーバーロードで `memory_order` は、 *Order1*の値に基づく暗黙的な*Order2*が使用されます。 *Order1*がの場合 `memory_order_acq_rel` 、 *Order2*は `memory_order_acquire` です。 *Order1*がの場合 `memory_order_release` 、 *Order2*は `memory_order_relaxed` です。 それ以外の場合は、 *Order2*は*Order1*と等しくなります。

2つのパラメーターを受け取るオーバーロードで `memory_order` は、 *Order2*の値をまたはにすることはできません `memory_order_release` 。また、 `memory_order_acq_rel` *Order1*の値よりも強い値を指定することはできません。

## <a name="atomiccompare_exchange_weak"></a><a name="compare_exchange_weak"></a>atomic:: compare_exchange_weak

** \* この**に対して弱いアトミック比較と交換操作を実行します。

```cpp
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*期限*\
*Ty*型の値。

*数値*\
*Ty*型の値。

*Order1*\
1番目 `memory_order` の引数。

*Order2*\
2 番目の `memory_order` 引数。

### <a name="return-value"></a>戻り値

**`bool`** 値の比較の結果を示す。

### <a name="remarks"></a>解説

このアトミックの比較および交換操作では、 ** \* この**に格納されている値と*Exp*を比較します。値が等しい場合、操作は、 ** \* この**に格納されている値を、読み取り/書き込み操作を使用し、 *Order1*で指定されたメモリ順序制約を適用して、*値*に置き換えます。 値が等しくない場合、この操作は、 ** \* この**に格納されている値を使用して*Exp*を置き換え、 *Order2*で指定されているメモリ順序制約を適用します。

比較された値が同一の場合、弱いアトミック比較および交換操作は交換を実行します。 値が同じでない場合、操作による交換の実行は保証されません。

2番目のを持たないオーバーロードで `memory_order` は、 *Order1*の値に基づく暗黙的な*Order2*が使用されます。 *Order1*がの場合 `memory_order_acq_rel` 、 *Order2*は `memory_order_acquire` です。 *Order1*がの場合 `memory_order_release` 、 *Order2*は `memory_order_relaxed` です。 それ以外の場合は、 *Order2*は*Order1*と等しくなります。

2つのパラメーターを受け取るオーバーロードで `memory_order` は、 *Order2*の値をまたはにすることはできません `memory_order_release` 。また、 `memory_order_acq_rel` *Order1*の値よりも強い値を指定することはできません。

## <a name="atomicexchange"></a><a name="exchange"></a>atomic:: exchange

指定した値を使用して、 ** \* この**の格納されている値を置き換えます。

```cpp
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

*順序*\
`memory_order`。

### <a name="return-value"></a>戻り値

Exchange の前に格納されていた** \* この**の値。

### <a name="remarks"></a>解説

この操作では、*値*を使用して、 *Order*によって指定されたメモリ制約内で、 ** \* この**に格納されている値を置き換える読み取り/書き込み操作を実行します。

## <a name="atomicfetch_add"></a><a name="fetch_add"></a>atomic:: fetch_add

** \* この**に格納されている値をフェッチし、格納されている値に指定した値を加算します。

```cpp
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

*順序*\
`memory_order`。

### <a name="return-value"></a>戻り値

加算の前に、 ** \* この**に格納されている値を格納している*Ty*オブジェクト。

### <a name="remarks"></a>解説

メソッドは、 `fetch_add` 読み取り/書き込み操作を実行して、 ** \* この**の格納された値に*値*をアトミックに追加し、 *Order*によって指定されたメモリ制約を適用します。

## <a name="atomicfetch_and"></a><a name="fetch_and"></a>atomic:: fetch_and

値と、 ** \* この**に格納されている既存の値に対してビットごとの and を実行します。

```cpp
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

*順序*\
`memory_order`。

### <a name="return-value"></a>戻り値

ビットごとの and の結果を含む*Ty*オブジェクト。

### <a name="remarks"></a>解説

メソッドは、 `fetch_and` ** \* この**の格納された値を、 *Order*によって指定されたメモリ制約内で、*値*のビットごとの and と、 ** \* この**に格納されている現在の値に置換する読み取り/書き込み操作を実行します。

## <a name="atomicfetch_or"></a><a name="fetch_or"></a>atomic:: fetch_or

値と、 ** \* この**に格納されている既存の値に対してビットごとの or を実行します。

```cpp
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

*順序*\
`memory_order`。

### <a name="return-value"></a>戻り値

ビットごとの or の結果を格納する*Ty*オブジェクト。

### <a name="remarks"></a>解説

メソッドは、 `fetch_or` read/modify 書き込み操作を実行して、 ** \* この**の格納されている値を、 *Order*で指定されたメモリ制約内で、ビットごとの or*値*と、 ** \* この**に格納されている現在の値に置き換えます。

## <a name="atomicfetch_sub"></a><a name="fetch_sub"></a>atomic:: fetch_sub

指定した値を格納されている値から減算します。

```cpp
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

*順序*\
`memory_order`。

### <a name="return-value"></a>戻り値

減算の結果を格納している*Ty*オブジェクト。

### <a name="remarks"></a>解説

メソッドは、 `fetch_sub` *順序*によって指定されたメモリの制約内で、 ** \* この**の格納されている値から*値*をアトミックに減算するために、読み取り/書き込み操作を実行します。

## <a name="atomicfetch_xor"></a><a name="fetch_xor"></a>atomic:: fetch_xor

値と、 ** \* この**に格納されている既存の値に対してビットごとの排他的 or を実行します。

```cpp
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*型の値。

*順序*\
`memory_order`。

### <a name="return-value"></a>戻り値

ビットごとの排他的 or の結果を格納する*Ty*オブジェクト。

### <a name="remarks"></a>解説

メソッドは、 `fetch_xor` 読み取り/書き込み操作を実行して、 ** \* この**の格納された値をビットごとの排他的 or*値*に置き換え、 ** \* この**に格納されている現在の値を、 *Order*によって指定されたメモリ制約を適用します。

## <a name="atomicis_lock_free"></a><a name="is_lock_free"></a>atomic:: is_lock_free

** \* この**に対するアトミック操作がロックを解放するかどうかを指定します。

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>戻り値

** \* この**に対するアトミック操作がロックを解放している場合は true、それ以外の場合は false。

### <a name="remarks"></a>解説

その型に対する分割不可能な操作においてロックが使用される場合、atomic 型はロック制御不要になります。

## <a name="atomicload"></a><a name="load"></a>atomic:: load

指定されたメモリ制約内で、 ** \* この**内の格納されている値を取得します。

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*\
`memory_order`。 *順序*をまたはにすることはできません `memory_order_release` `memory_order_acq_rel` 。

### <a name="return-value"></a>戻り値

** \* この**に格納されている取得値。

## <a name="atomicstore"></a><a name="store"></a>atomic:: store

指定された値を格納します。

```cpp
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
*Ty*オブジェクト。

*順序*\
`memory_order`制約です。

### <a name="remarks"></a>解説

このメンバー関数は*Value* **`*this`** 、 *Order*によって指定されたメモリ制約内で、に値をアトミックに格納します。

## <a name="see-also"></a>関連項目

[\<atomic>](../standard-library/atomic.md)\
[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
