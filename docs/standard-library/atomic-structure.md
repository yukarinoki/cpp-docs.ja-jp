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
ms.openlocfilehash: 0e5982fc303362a9636c4bf1b0e2d89c6aa05031
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962359"
---
# <a name="atomic-structure"></a>atomic 構造体

型の格納された値に対してアトミックな操作を実行するオブジェクトについて説明します*Ty*します。

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
|[atomic::operator =](#op_eq)|格納されている値を置き換えるために指定された値を使用します。 ([atomic::store](#store))|
|[atomic::operator++](#op_inc)|格納されている値をインクリメントします。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator + =](#op_add_eq)|指定した値を格納されている値に加算します。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator--](#op_dec)|格納されている値をデクリメントします。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator-=](#op_sub_eq)|指定した値を格納されている値から減算します。 整数およびポインターの特殊化でのみ使用されます。|
|[atomic::operator & =](#op_and_eq)|和演算を実行し、指定した値と格納されている値。 整数の特殊化でのみ使用されます。|
|[atomic::operator&#124;=](#op_or_eq)|ビットごとの実行または指定した値と格納されている値。 整数の特殊化でのみ使用されます。|
|[atomic::operator ^ =](#op_xor_eq)|ビットごとの排他的を実行します。 または、指定した値と格納されている値。 整数の特殊化でのみ使用されます。|
|**関数**||
|[compare_exchange_strong](#compare_exchange_strong)|実行、 *atomic_compare_and_exchange*操作**これ**し、結果を返します。|
|[compare_exchange_weak](#compare_exchange_weak)|実行、 *weak_atomic_compare_and_exchange*操作**この**し、結果を返します。|
|[fetch_add](#fetch_add)|指定した値を格納されている値に加算します。|
|[fetch_and](#fetch_and)|和演算を実行し、指定した値と格納されている値。|
|[fetch_or](#fetch_or)|ビットごとの実行または指定した値と格納されている値。|
|[fetch_sub](#fetch_sub)|指定した値を格納されている値から減算します。|
|[fetch_xor](#fetch_xor)|ビットごとの排他的を実行します。 または、指定した値と格納されている値。|
|[is_lock_free](#is_lock_free)|指定するかどうかアトミックな操作を**この**は*ロック制御不要*。 その型に対する分割不可能な操作においてロックが使用される場合、atomic 型は*ロック制御不要*になります。|
|[ロード](#load)|格納されている値を読み取って返します。|
|[store](#store)|格納されている値を置き換えるために指定された値を使用します。|

## <a name="remarks"></a>Remarks

型*Ty*あります*普通にコピー可能*します。 つまりを使用して[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)そのバイトをコピーするは、有効な生成する必要があります*Ty*元のオブジェクトと等しいオブジェクト。 [Compare_exchange_weak](#compare_exchange_weak)と[compare_exchange_strong](#compare_exchange_strong)メンバー関数の使用[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) 2 つかどうかを判断する*Ty*値等しくなります。 これらの関数は使用しない、 *Ty*-定義`operator==`します。 メンバー関数は、`atomic`使用`memcpy`型の値をコピーする*Ty*します。

部分的特殊化では、**アトミック\<Ty \* >** 、すべてのポインター型に存在します。 特殊化により、マネージド ポインター値のオフセットの加算またはマネージド ポインター値からのオフセットの減算が可能になります。 算術演算は、型の引数を受け取る`ptrdiff_t`のサイズに従ってその引数を調整および*Ty*通常のアドレス算術一致するようにします。

以外のすべての整数型の特殊化が存在する**bool**します。 それぞれの特殊化には、分割不可能な算術演算および論理演算のための豊富な一連のメソッドが用意されています。

||||
|-|-|-|
|**アトミック\<char >**|**アトミック\<署名 char >**|**アトミック\<unsigned char >**|
|**アトミック\<char16_t >**|**アトミック\<char32_t >**|**アトミック\<wchar_t >**|
|**アトミック\<短い >**|**アトミック\<短い符号なし >**|**アトミック\<int >**|
|**アトミック\<符号なし int >**|**アトミック\<長い >**|**アトミック\<時間の長い符号なし >**|
|**アトミック\<long >**|**アトミック\<unsigned long long 型 >**|

整数の特殊化は、対応する `atomic_integral` 型から派生します。 たとえば、**アトミック\<符号なし int >** から派生`atomic_uint`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<atomic >

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

### <a name="remarks"></a>Remarks

アトミック オブジェクトをコピーまたは移動することはできません。

アトミックのインスタンスであるオブジェクト\<*Ty*> 型の引数を受け取るコンス トラクターによってのみ初期化できます*Ty*集約の初期化ではなく、します。 ただし、集約の初期化を使用してのみ atomic_integral オブジェクトを初期化することができます。

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> atomic::operator *Ty*

分割不可能なテンプレートに指定された型の演算子\<*Ty*>。 格納されている値を取得します。 **\*この**します。

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Remarks

この演算子が適用され、 `memory_order_seq_cst` [memory_order](atomic-enums.md)します。

## <a name="op_eq"></a> atomic::operator =

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

返します*値*します。

## <a name="op_inc"></a> atomic::operator++

格納されている値をインクリメントします。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>戻り値

最初の 2 つの演算子は、インクリメントした値を返す最後の 2 つの演算子は、インクリメント前に、の値を返します。 演算子を使用して、 `memory_order_seq_cst` [memory_order](atomic-enums.md)します。

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

### <a name="remarks"></a>Remarks

この演算子を使用して、 `memory_order_seq_cst` [memory_order](atomic-enums.md)します。

## <a name="op_dec"></a> atomic::operator--

格納されている値をデクリメントします。 整数およびポインターの特殊化でのみ使用されます。

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>戻り値

最初の 2 つの演算子は、デクリメントした値を返す最後の 2 つの演算子は、デクリメントの前に、の値を返します。 演算子を使用して、 `memory_order_seq_cst` [memory_order](atomic-enums.md)します。

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

A *Ty*減算の結果を格納するオブジェクト。

### <a name="remarks"></a>Remarks

この演算子を使用して、 `memory_order_seq_cst` [memory_order](atomic-enums.md)します。

## <a name="op_and_eq"></a> atomic::operator & =

排他的 or 演算を指定した値との格納されている値で**\*これ**します。 整数の特殊化でのみ使用されます。

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
型の値*Ty*します。

### <a name="return-value"></a>戻り値

ビットごとの結果とします。

### <a name="remarks"></a>Remarks

この演算子の格納されている値を置換する読み取り/変更/書き込み操作を実行する**\*この**し、ビットごとの*値*と現在の値に格納されている **\*この**の制約内で、 `memory_order_seq_cst` [memory_order](atomic-enums.md)します。

## <a name="op_or_eq"></a> atomic::operator&#124;=

排他的 or 演算を指定した値と、格納された値の上または**\*これ**。 整数の特殊化でのみ使用されます。

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
型の値*Ty*します。

### <a name="return-value"></a>戻り値

ビットごとの結果またはします。

### <a name="remarks"></a>Remarks

この演算子の格納されている値を置換する読み取り/変更/書き込み操作を実行する**\*この**をビットごとまたは*値*と現在の値に格納されている **\*この**の制約内で、 `memory_order_seq_cst` [memory_order](atomic-enums.md)制約。

## <a name="op_xor_eq"></a> atomic::operator ^ =

ビットごとの排他的を実行します。 指定した値と、格納された値の上または**\*この**します。 整数の特殊化でのみ使用されます。

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
型の値*Ty*します。

### <a name="return-value"></a>戻り値

ビットごとの排他的の結果またはします。

### <a name="remarks"></a>Remarks

この演算子の格納されている値を置換する読み取り/変更/書き込み操作を実行する**\*この**またはのビットごとの排他*値*と現在の値に格納されている**\*この**の制約内で、 `memory_order_seq_cst` [memory_order](atomic-enums.md)制約。

## <a name="compare_exchange_strong"></a> atomic::compare_exchange_strong

に対してアトミック比較および交換操作を実行します。 **\*この**します。

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
型の値*Ty*します。

*値*<br/>
型の値*Ty*します。

*Order1*<br/>
最初`memory_order`引数。

*Order2*<br/>
2 番目の `memory_order` 引数。

### <a name="return-value"></a>戻り値

A **bool**値の比較の結果を示します。

### <a name="remarks"></a>Remarks

このアトミック比較および交換操作に格納されている値を比較します。 **\*この**で*Exp*します。格納されている値が、操作に置き換えられます、値が等しい場合は、 **\*この**で*値*読み取り/変更/書き込み操作を使用しているメモリ順序制約を適用して指定された*Order1*します。 操作に格納されている値を使用して、値が等しくない場合は、 **\*この**を置き換える*Exp*によって指定されたメモリ順序制約を適用および*Order2*.

2 つ目がないオーバー ロード`memory_order`暗黙的な使用*Order2*の値に基づく*Order1*します。 場合*Order1*は`memory_order_acq_rel`、 *Order2*は`memory_order_acquire`します。 場合*Order1*は`memory_order_release`、 *Order2*は`memory_order_relaxed`します。 その他のすべてのケースで*Order2*と等しい*Order1*します。

受け取る 2 つのオーバー ロードの`memory_order`パラメーターの値は、 *Order2*必要があります`memory_order_release`または`memory_order_acq_rel`、ありの値よりも強力であってはいけません*Order1*します。

## <a name="compare_exchange_weak"></a> atomic::compare_exchange_weak

に対して弱いアトミックの比較および交換操作を実行します。 **\*この**します。

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
型の値*Ty*します。

*値*<br/>
型の値*Ty*します。

*Order1*<br/>
最初`memory_order`引数。

*Order2*<br/>
2 番目の `memory_order` 引数。

### <a name="return-value"></a>戻り値

A **bool**値の比較の結果を示します。

### <a name="remarks"></a>Remarks

このアトミック比較および交換操作に格納されている値を比較します。 **\*この**で*Exp*します。格納されている値が、操作に置き換えられます、値が等しい場合は、 **\*この**で*値*読み取り/変更/書き込み操作を使用しているメモリ順序制約を適用して指定された*Order1*します。 操作に格納されている値を使用して、値が等しくない場合は、 **\*この**を置き換える*Exp*によって指定されたメモリ順序制約を適用および*Order2*.

弱いアトミックの比較および交換操作は、比較対象の値が等しい場合に交換を実行します。 値が同じでない場合、操作による交換の実行は保証されません。

2 つ目がないオーバー ロード`memory_order`暗黙的な使用*Order2*の値に基づく*Order1*します。 場合*Order1*は`memory_order_acq_rel`、 *Order2*は`memory_order_acquire`します。 場合*Order1*は`memory_order_release`、 *Order2*は`memory_order_relaxed`します。 その他のすべてのケースで*Order2*と等しい*Order1*します。

受け取る 2 つのオーバー ロードの`memory_order`パラメーターの値は、 *Order2*必要があります`memory_order_release`または`memory_order_acq_rel`、ありの値よりも強力であってはいけません*Order1*します。

## <a name="exchange"></a> atomic::exchange

指定した値を使用しての格納されている値を置き換えます**\*この**します。

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
型の値*Ty*します。

*順序*<br/>
`memory_order`。

### <a name="return-value"></a>戻り値

格納されている値**\*この**交換する前にします。

### <a name="remarks"></a>Remarks

この操作は、使用する読み取り/変更/書き込み操作を実行します*値*に格納されている値に置き換える**\*この**、で指定されているメモリ制約内で *。順序*します。

## <a name="fetch_add"></a> atomic::fetch_add

格納されている値をフェッチ**\*この**、格納されている値を指定した値に追加します。

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
型の値*Ty*します。

*順序*<br/>
`memory_order`。

### <a name="return-value"></a>戻り値

A *Ty*オブジェクトに格納されている値を含む**\*この**を追加する前にします。

### <a name="remarks"></a>Remarks

`fetch_add`アトミックに加算する読み取り/変更/書き込み操作はなに*値*で格納されている値に**\*これ**で指定されているメモリの制約を適用*順序*します。

## <a name="fetch_and"></a> atomic::fetch_and

排他的 or 演算を値と既存の値に格納されているのと**\*この**。

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
型の値*Ty*します。

*順序*<br/>
`memory_order`。

### <a name="return-value"></a>戻り値

A *Ty*ビットごとの結果を格納しているオブジェクトとします。

### <a name="remarks"></a>Remarks

`fetch_and`の格納されている値を置換する読み取り/変更/書き込み操作はなに**\*これ**し、ビットごとの*値*に格納されている現在の値と**\*この**で指定されているメモリ制約内で*順序*します。

## <a name="fetch_or"></a> atomic::fetch_or

排他的 or 演算またはの値と既存の値に格納されている**\*この**します。

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
型の値*Ty*します。

*順序*<br/>
`memory_order`。

### <a name="return-value"></a>戻り値

A *Ty*ビットごとの結果を格納しているオブジェクトまたはします。

### <a name="remarks"></a>Remarks

`fetch_or`の格納されている値を置換する読み取り/変更/書き込み操作はなに**\*この**またはのビットごと*値*に格納されている現在の値と**\*この**で指定されているメモリ制約内で*順序*します。

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
型の値*Ty*します。

*順序*<br/>
`memory_order`。

### <a name="return-value"></a>戻り値

A *Ty*減算の結果を格納するオブジェクト。

### <a name="remarks"></a>Remarks

`fetch_sub`アトミックに減算する読み取り/変更/書き込み操作はなに*値*で格納されている値から**\*この**で指定されているメモリ制約内で*順序*します。

## <a name="fetch_xor"></a> atomic::fetch_xor

ビットごとの排他的を実行します。 値と格納されている既存の値を上または**\*この**します。

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
型の値*Ty*します。

*順序*<br/>
`memory_order`。

### <a name="return-value"></a>戻り値

A *Ty*排他的論理和の結果を格納しているオブジェクトまたはします。

### <a name="remarks"></a>Remarks

`fetch_xor`の格納されている値を置換する読み取り/変更/書き込み操作はなに**\*この**またはのビットごとの排他*値*と現在の値に格納されています。**\*この**で指定されているメモリの制約を適用および*順序*します。

## <a name="is_lock_free"></a> atomic::is_lock_free

指定するかどうかアトミックな操作を**\*これ**はロック制御不要。

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>戻り値

に対する分割不可能な場合は true。 操作**\*この**はロックが無料、それ以外は false。

### <a name="remarks"></a>Remarks

Atomic 型は、その型に対するアトミック操作がロックを使用しない場合、ロック フリーは。

## <a name="load"></a> atomic::load

格納されている値を取得します。 **\*この**、指定されたメモリ制約内で。

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
`memory_order`。 *順序*必要があります`memory_order_release`または`memory_order_acq_rel`します。

### <a name="return-value"></a>戻り値

取得した値に格納されている**\*この**します。

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
A`memory_order`制約。

### <a name="remarks"></a>Remarks

このメンバー関数はアトミックに格納*値*で`*this`で指定されているメモリ制約内で*順序*します。

## <a name="see-also"></a>関連項目

[\<atomic>](../standard-library/atomic.md)<br/>
[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
