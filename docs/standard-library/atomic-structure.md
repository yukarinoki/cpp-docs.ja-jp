---
title: atomic 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 04/20/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7308c127bebd2185429509315ebafb3d83a7efea
ms.sourcegitcommit: b0d5557dbb57128da560a0a4634312ec4a050a90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="atomic-structure"></a>atomic 構造体

型の格納されている値に対して分割不可能な操作を実行するオブジェクトを記述*Ty*です。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>メンバー

|メンバー|説明|
|----------|-----------------|
|**コンストラクター**||
|[atomic](#atomic)|アトミック オブジェクトを構築します。|
|**演算子**||
|[atomic::operator Ty](#op_ty)|格納されている値を読み取って返します。 ([atomic::load](#load))|
|[atomic::operator = =](#op_eq)|格納されている値を置き換えるために指定された値を使用します。 ([atomic::store](#store))|
|[atomic::operator++](#op_inc)|格納されている値をインクリメントします。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator + =](#op_add_eq)|指定した値を格納されている値に加算します。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator--](#op_dec)|格納されている値をデクリメントします。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator-=](#op_sub_eq)|指定した値を格納されている値から減算します。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator & =](#op_and_eq)|排他的 or 演算と、指定した値と格納されている値にします。 整数の特殊化でのみ使用されます。|
|[atomic::operator&#124;=](#op_or_eq)|排他的 or 演算または指定した値と格納されている値。 整数の特殊化でのみ使用されます。|
|[atomic::operator ^ =](#op_xor_eq)|ビットごとの排他的に実行または指定した値と格納されている値。 整数の特殊化でのみ使用されます。|
|**関数**||
|[compare_exchange_strong](#compare_exchange_strong)|実行、 *atomic_compare_and_exchange*操作**この**結果を返します。|
|[compare_exchange_weak](#compare_exchange_weak)|実行、 *weak_atomic_compare_and_exchange*操作**この**結果を返します。|
|[fetch_add](#fetch_add)|指定した値を格納されている値に加算します。|
|[fetch_and](#fetch_and)|排他的 or 演算と、指定した値と格納されている値にします。|
|[fetch_or](#fetch_or)|排他的 or 演算または指定した値と格納されている値。|
|[fetch_sub](#fetch_sub)|指定した値を格納されている値から減算します。|
|[fetch_xor](#fetch_xor)|ビットごとの排他的に実行または指定した値と格納されている値。|
|[is_lock_free](#is_lock_free)|指定するかどうかアトミックな操作を**この**は*ロック制御不要*です。 その型に対する分割不可能な操作においてロックが使用される場合、atomic 型は*ロック制御不要*になります。|
|[負荷](#load)|格納されている値を読み取って返します。|
|[ストア](#store)|格納されている値を置き換えるために指定された値を使用します。|

## <a name="remarks"></a>コメント

型*Ty*する必要があります*普通にコピー可能*です。 使用して、 [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)そのバイトのコピーは、有効な生成する必要があります*Ty*元のオブジェクトと等しいを比較するオブジェクト。 [Compare_exchange_weak](#compare_exchange_weak)と[compare_exchange_strong](#compare_exchange_strong)メンバー関数を使用して[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)を 2 つあるかどうかを判断*Ty*値等価です。 これらの関数は使用しない、 *Ty*-定義**演算子 = =** です。 メンバー関数は、**アトミック**使用**memcpy**型の値をコピーする*Ty*です。

部分的特殊化では、**アトミック\<Ty \* >** 、すべてのポインター型に存在します。 特殊化により、マネージ ポインター値のオフセットの加算またはマネージ ポインター値からのオフセットの減算が可能になります。 算術演算型の引数として受け取ります**ptrdiff_t**のサイズに従ってその引数を調整および*Ty*通常のアドレス算術と一致するようにします。

すべての整数型を除く、特殊化が存在する**bool**です。 それぞれの特殊化には、分割不可能な算術演算および論理演算のための豊富な一連のメソッドが用意されています。

||||
|-|-|-|
|**アトミック\<char >**|**アトミック\<char を署名 >**|**アトミック\<char 型の符号なし >**|
|**アトミック\<char16_t >**|**アトミック\<char32_t >**|**アトミック\<wchar_t >**|
|**アトミック\<短い >**|**アトミック\<短い符号なし >**|**アトミック\<int >**|
|**アトミック\<符号なし int >**|**アトミック\<長い >**|**アトミック\<長い符号なし >**|
|**アトミック\<long >**|**アトミック\<long long 型の符号なし >**|

整数の特殊化は、対応する由来**atomic_integral**型です。 たとえば、**アトミック\<符号なし int >** から派生した**atomic_uint**です。

## <a name="requirements"></a>要件

**ヘッダー:** \<アトミック >

**名前空間:** std

## <a name="atomic"></a> atomic::atomic

アトミック オブジェクトを構築します。

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>パラメーター

*値*<br/>
初期化値。

### <a name="remarks"></a>コメント

アトミック オブジェクトをコピーまたは移動することはできません。

アトミックのインスタンス化であるオブジェクト\<*Ty*> 型の引数を受け取るコンス トラクターによってのみ初期化できます*Ty*集約の初期化ではなくです。 ただし、atomic_integral オブジェクトは、集約の初期化によってのみ初期化できます。

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> atomic::operator *Ty*

分割不可能なテンプレートに指定された型の演算子\<*Ty*>。 格納されている値を取得**\*この**です。

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>コメント

この演算子が適用され、 **memory_order_seq_cst** [memory_order](atomic-enums.md)です。

## <a name="op_eq"></a> atomic::operator = =

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

*値*<br/>
A *Ty*オブジェクト。

### <a name="return-value"></a>戻り値

返します*値*です。

## <a name="op_inc"></a> atomic::operator++

格納されている値をインクリメントします。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>戻り値

最初の 2 つの演算子を返すインクリメントされた値です。最後の 2 つの演算子は、インクリメント前に、の値を返します。 演算子を使用して、 **memory_order_seq_cst** [memory_order](atomic-enums.md)です。

## <a name="op_add_eq"></a> atomic::operator + =

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

*値*<br/>
整数型またはポインター値です。

### <a name="return-value"></a>戻り値

A *Ty*加算の結果を格納しているオブジェクト。

### <a name="remarks"></a>コメント

この演算子を使用して、 **memory_order_seq_cst** [memory_order](atomic-enums.md)です。

## <a name="op_dec"></a> atomic::operator--

格納されている値をデクリメントします。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>戻り値

最初の 2 つの演算子を返すデクリメントされた値です。最後の 2 つの演算子は、デクリメントする前に値を返します。 演算子を使用して、 **memory_order_seq_cst** [memory_order](atomic-enums.md)です。

## <a name="op_sub_eq"></a> atomic::operator-=

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

*値*<br/>
整数型またはポインター値です。

### <a name="return-value"></a>戻り値

A *Ty*減算の結果を格納しているオブジェクト。

### <a name="remarks"></a>コメント

この演算子を使用して、 **memory_order_seq_cst** [memory_order](atomic-enums.md)です。

## <a name="op_and_eq"></a> atomic::operator & =

排他的 or 演算とで指定した値と格納されている値の**\*この**です。 整数の特殊化でのみ使用されます。

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*値*<br/>
型の値*Ty*です。

### <a name="return-value"></a>戻り値

ビットごとの結果とします。

### <a name="remarks"></a>コメント

この操作の格納されている値を置換する読み取り/変更/書き込み操作が実行**\*この**演算との*値*と現在の値に格納されている **\*この**の制約内で、 **memory_order_seq_cst** [memory_order](atomic-enums.md)です。

## <a name="op_or_eq"></a> atomic::operator&#124;=

排他的 or 演算またはファイルの指定した値と格納されている値の**\*この**です。 整数の特殊化でのみ使用されます。

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*値*<br/>
型の値*Ty*です。

### <a name="return-value"></a>戻り値

ビットごとの結果またはします。

### <a name="remarks"></a>コメント

この操作の格納されている値を置換する読み取り/変更/書き込み操作が実行**\*この**、ビットごとの有無の*値*と現在の値に格納されている **\*この**の制約内で、 **memory_order_seq_cst** [memory_order](atomic-enums.md)制約。

## <a name="op_xor_eq"></a> atomic::operator ^ =

ビットごとの排他的に実行またはファイルの指定した値と格納されている値の**\*この**です。 整数の特殊化でのみ使用されます。

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>パラメーター

*値*<br/>
型の値*Ty*です。

### <a name="return-value"></a>戻り値

排他的論理和の結果またはします。

### <a name="remarks"></a>コメント

この操作の格納されている値を置換する読み取り/変更/書き込み操作が実行**\*この**またはのビットごとの排他*値*と現在の値に格納されている**\*この**の制約内で、 **memory_order_seq_cst** [memory_order](atomic-enums.md)制約。

## <a name="compare_exchange_strong"></a> atomic::compare_exchange_strong

に対してアトミックな比較および交換操作を実行**\*この**です。

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

*Exp*<br/>
型の値*Ty*です。

*値*<br/>
型の値*Ty*です。

*Order1*<br/>
最初の **memory_order** 引数。

*Order2*<br/>
2 番目**memory_order**引数。

### <a name="return-value"></a>戻り値

A **bool**値の比較の結果を示すです。

### <a name="remarks"></a>コメント

このアトミック比較および交換操作に格納されている値を比較する**\*この**で*Exp*です。操作に格納されている値で置き換え、値が等しい場合は、 **\*この**で*値*読み取り/変更/書き込み操作を使用しているメモリ順序制約を適用します。指定した*Order1*です。 操作に保存されている値を使用して、値が等しくない場合は、 **\*この**を置き換える*Exp*によって指定されたメモリ順序制約を適用して*Order2*.

2 つ目がないオーバー ロード**memory_order**暗黙的な使用*Order2*の値に基づく*Order1*です。 場合*Order1*は**memory_order_acq_rel**、 *Order2*は**memory_order_acquire**です。 場合*Order1*は**memory_order_release**、 *Order2*は**memory_order_relaxed**です。 その他のすべてのケースで*Order2*と等しい*Order1*です。

受け取る 2 つのオーバー ロード**memory_order**パラメーター、値の*Order2*することはできません**memory_order_release**または**memory_order_acq_rel**の値よりも厳しくする必要がありますいない*Order1*です。

## <a name="compare_exchange_weak"></a> atomic::compare_exchange_weak

弱いアトミックの比較および交換操作を実行**\*この**です。

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

*Exp*<br/>
型の値*Ty*です。

*値*<br/>
型の値*Ty*です。

*Order1*<br/>
最初の **memory_order** 引数。

*Order2*<br/>
2 番目**memory_order**引数。

### <a name="return-value"></a>戻り値

A **bool**値の比較の結果を示すです。

### <a name="remarks"></a>コメント

このアトミック比較および交換操作に格納されている値を比較する**\*この**で*Exp*です。操作に格納されている値で置き換え、値が等しい場合は、 **\*この**で*値*読み取り/変更/書き込み操作を使用しているメモリ順序制約を適用します。指定した*Order1*です。 操作に保存されている値を使用して、値が等しくない場合は、 **\*この**を置き換える*Exp*によって指定されたメモリ順序制約を適用して*Order2*.

弱いアトミックの比較および交換操作は、比較対象の値が等しい場合に交換を実行します。 値が同じでない場合、操作による交換の実行は保証されません。

2 つ目がないオーバー ロード**memory_order**暗黙的な使用*Order2*の値に基づく*Order1*です。 場合*Order1*は**memory_order_acq_rel**、 *Order2*は**memory_order_acquire**です。 場合*Order1*は**memory_order_release**、 *Order2*は**memory_order_relaxed**です。 その他のすべてのケースで*Order2*と等しい*Order1*です。

受け取る 2 つのオーバー ロード**memory_order**パラメーター、値の*Order2*することはできません**memory_order_release**または**memory_order_acq_rel**の値よりも厳しくする必要がありますいない*Order1*です。

## <a name="exchange"></a> atomic::exchange

指定した値を使用してに格納された値を置き換えます**\*この**です。

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

*値*<br/>
型の値*Ty*です。

*順序*<br/>
**memory_order**。

### <a name="return-value"></a>戻り値

格納されている値の**\*この**交換する前にします。

### <a name="remarks"></a>コメント

この操作を使用する読み取り/変更/書き込み操作を実行する*値*に格納されている値を置き換えるため**\*この**で指定されているメモリ制約内で*順序*です。

## <a name="fetch_add"></a> atomic::fetch_add

格納されている値をフェッチ**\*この**、し、格納されている値に指定された値を追加します。

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

*値*<br/>
型の値*Ty*です。

*順序*<br/>
**memory_order**。

### <a name="return-value"></a>戻り値

A *Ty*に格納されている値を含むオブジェクト**\*この**追加する前にします。

### <a name="remarks"></a>コメント

**Fetch_add**メソッドをアトミックに追加する読み取り/変更/書き込み操作を実行*値*で格納されている値を**\*この**、し、メモリの適用指定されている制約*順序*です。

## <a name="fetch_and"></a> atomic::fetch_and

排他的 or 演算値と既存の値に格納されているのと**\*この**です。

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

*値*<br/>
型の値*Ty*です。

*順序*<br/>
**memory_order**。

### <a name="return-value"></a>戻り値

A *Ty*ビットごとの結果を格納しているオブジェクトとします。

### <a name="remarks"></a>コメント

**Fetch_and**メソッドの格納されている値を置換する読み取り/変更/書き込み操作を実行**\*この**演算との*値*と現在格納されている値**\*この**で指定されているメモリ制約内で*順序*です。

## <a name="fetch_or"></a> atomic::fetch_or

排他的 or 演算またはファイルの値と既存の値に格納されている**\*この**です。

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

*値*<br/>
型の値*Ty*です。

*順序*<br/>
**memory_order**。

### <a name="return-value"></a>戻り値

A *Ty*ビットごとの結果を格納しているオブジェクトまたはします。

### <a name="remarks"></a>コメント

**Fetch_or**メソッドの格納されている値を置換する読み取り/変更/書き込み操作を実行**\*この**、ビットごとの有無の*値*と現在の値格納されている**\*この**で指定されているメモリ制約内で*順序*です。

## <a name="fetch_sub"></a> atomic::fetch_sub

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

*値*<br/>
型の値*Ty*です。

*順序*<br/>
**memory_order**。

### <a name="return-value"></a>戻り値

A *Ty*減算の結果を格納しているオブジェクト。

### <a name="remarks"></a>コメント

**Fetch_sub**メソッド アトミックに減算する読み取り/変更/書き込み操作を実行*値*で格納されている値から**\*この**メモリ内で指定されている制約*順序*です。

## <a name="fetch_xor"></a> atomic::fetch_xor

ビットごとの排他的に実行またはファイルの値と既存の値に格納されている**\*この**です。

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

*値*<br/>
型の値*Ty*です。

*順序*<br/>
**memory_order**。

### <a name="return-value"></a>戻り値

A *Ty*排他的論理和の結果を格納しているオブジェクトまたはします。

### <a name="remarks"></a>コメント

**Fetch_xor**メソッドの格納されている値を置換する読み取り/変更/書き込み操作を実行**\*この**またはのビットごとの排他*値*および格納されている現在の値**\*この**で指定されているメモリの制約を適用して*順序*です。

## <a name="is_lock_free"></a> atomic::is_lock_free

指定するかどうかアトミックな操作を**\*この**はロック制御不要です。

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>戻り値

に対する分割不可能な場合は true。 操作**\*この**、ロック フリー。 それ以外の場合は false。

### <a name="remarks"></a>コメント

アトミック型は、その型に対するアトミック操作がロックを使用する場合のロック空きです。

## <a name="load"></a> atomic::load

格納されている値を取得**\*この**、指定されたメモリ制約内で。

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*<br/>
**memory_order**。 *順序*することはできません**memory_order_release**または**memory_order_acq_rel**です。

### <a name="return-value"></a>戻り値

取得した値に格納されている**\*この**です。

## <a name="store"></a> atomic::store

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

*値*<br/>
A *Ty*オブジェクト。

*順序*<br/>
A **memory_order**制約。

### <a name="remarks"></a>コメント

このメンバー関数をアトミックに格納*値*で`*this`で指定されているメモリ制約内で*順序*です。

## <a name="see-also"></a>関連項目

[\<atomic>](../standard-library/atomic.md)<br/>
[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
