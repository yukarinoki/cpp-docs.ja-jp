---
title: scoped_allocator_adaptor クラス
ms.date: 11/04/2016
f1_keywords:
- scoped_allocator/std::scoped_allocator_adaptor
- scoped_allocator/std::scoped_allocator_adaptor::rebind Struct
- scoped_allocator/std::scoped_allocator_adaptor::allocate
- scoped_allocator/std::scoped_allocator_adaptor::construct
- scoped_allocator/std::scoped_allocator_adaptor::deallocate
- scoped_allocator/std::scoped_allocator_adaptor::destroy
- scoped_allocator/std::scoped_allocator_adaptor::inner_allocator
- scoped_allocator/std::scoped_allocator_adaptor::max_size
- scoped_allocator/std::scoped_allocator_adaptor::outer_allocator
- scoped_allocator/std::scoped_allocator_adaptor::select_on_container_copy_construction
helpviewer_keywords:
- std::scoped_allocator_adaptor
- std::scoped_allocator_adaptor::allocate
- std::scoped_allocator_adaptor::construct
- std::scoped_allocator_adaptor::deallocate
- std::scoped_allocator_adaptor::destroy
- std::scoped_allocator_adaptor::inner_allocator
- std::scoped_allocator_adaptor::max_size
- std::scoped_allocator_adaptor::outer_allocator
- std::scoped_allocator_adaptor::select_on_container_copy_construction
ms.assetid: 0d9b06a1-9a4a-4669-9470-8805cae48e89
ms.openlocfilehash: b08cf1858cb0f9bf4dc6201edc2502d48754ff77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373395"
---
# <a name="scoped_allocator_adaptor-class"></a>scoped_allocator_adaptor クラス

アロケーターの入れ子を表します。

## <a name="syntax"></a>構文

```cpp
template <class Outer, class... Inner>
class scoped_allocator_adaptor;
```

## <a name="remarks"></a>解説

クラス テンプレートは、1 つ以上のアロケーターの入れ子をカプセル化します。 このような各クラスは、`outer_allocator_type` 型の最も外側のアロケーターである `Outer` のシノニムを持ちます。これは、`scoped_allocator_adaptor` オブジェクトのパブリック ベースです。 `Outer` はコンテナーで使用されるメモリの割り当てに使用されます。 このアロケーター基本オブジェクトへの参照を取得するには、`outer_allocator` を呼び出します。

入れ子の残りの部分には `inner_allocator_type` 型が含まれます。 内部のアロケーターを使用して、コンテナー内の要素にメモリを割り当てます。 格納されているこの型のオブジェクトへの参照を取得するには、`inner_allocator` を呼び出します。 `Inner...` が空ではない場合、`inner_allocator_type` は型 `scoped_allocator_adaptor<Inner...>` を持ち、`inner_allocator` はメンバー オブジェクトを指定します。 それ以外の場合、`inner_allocator_type` は型 `scoped_allocator_adaptor<Outer>` を持ち、`inner_allocator` はオブジェクト全体を指定します。

入れ子は、必要に応じて、最も内側のカプセル化されたアロケーターをレプリケートする任意の深さがあるかのように動作します。

このクラス テンプレートの動作を記述する際に、表示可能なインターフェイスの一部ではないいくつかの概念。 *最も外側のアロケーター*は、コンストラクトのすべての呼び出しを仲介し、メソッドを破棄します。 再帰関数 `OUTERMOST(X)` で効率的に定義されます。ここで `OUTERMOST(X)` は、次のいずれかです。

- `X.outer_allocator()` が整形式である場合、`OUTERMOST(X)` は `OUTERMOST(X.outer_allocator())` です。

- それ以外の場合、`OUTERMOST(X)` は `X` です。

説明のために 3 つの型が定義されています。

|Type|説明|
|----------|-----------------|
|`Outermost`|`OUTERMOST(*this)` の型。|
|`Outermost_traits`|`allocator_traits<Outermost>`|
|`Outer_traits`|`allocator_traits<Outer>`|

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[scoped_allocator_adaptor](#scoped_allocator_adaptor)|`scoped_allocator_adaptor` オブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|名前|説明|
|----------|-----------------|
|`const_pointer`|この型は、アロケーター `Outer` に関連付けられている `const_pointer` のシノニムです。|
|`const_void_pointer`|この型は、アロケーター `Outer` に関連付けられている `const_void_pointer` のシノニムです。|
|`difference_type`|この型は、アロケーター `Outer` に関連付けられている `difference_type` のシノニムです。|
|`inner_allocator_type`|この型は、入れ子になったアダプター `scoped_allocator_adaptor<Inner...>` の型のシノニムです。|
|`outer_allocator_type`|この型は、基本アロケーター `Outer` の型のシノニムです。|
|`pointer`|この型は、アロケーター `Outer` に関連付けられている `pointer` のシノニムです。|
|`propagate_on_container_copy_assignment`|`Outer_traits::propagate_on_container_copy_assignment` が true を保持するか、または `inner_allocator_type::propagate_on_container_copy_assignment` が true を保持する場合にのみ、この型は true を保持します。|
|`propagate_on_container_move_assignment`|`Outer_traits::propagate_on_container_move_assignment` が true を保持するか、または `inner_allocator_type::propagate_on_container_move_assignment` が true を保持する場合にのみ、この型は true を保持します。|
|`propagate_on_container_swap`|`Outer_traits::propagate_on_container_swap` が true を保持するか、または `inner_allocator_type::propagate_on_container_swap` が true を保持する場合にのみ、この型は true を保持します。|
|`size_type`|この型は、アロケーター `Outer` に関連付けられている `size_type` のシノニムです。|
|`value_type`|この型は、アロケーター `Outer` に関連付けられている `value_type` のシノニムです。|
|`void_pointer`|この型は、アロケーター `Outer` に関連付けられている `void_pointer` のシノニムです。|

### <a name="structs"></a>構造体

|名前|説明|
|----------|-----------------|
|[scoped_allocator_adaptor::構造体の再バインド](#rebind_struct)|`scoped_allocator_adaptor\<Other, Inner...>` のシノニムとして `Outer::rebind\<Other>::other` 型を定義します。|

### <a name="methods"></a>メソッド

|名前|説明|
|----------|-----------------|
|[割り当てる](#allocate)|`Outer` アロケーターを使用してメモリを割り当てます。|
|[構築](#construct)|オブジェクトを構築します。|
|[解放](#deallocate)|外側のアロケーターを使用してオブジェクトの割り当てを解除します。|
|[破壊](#destroy)|指定したオブジェクトを破棄します。|
|[inner_allocator](#inner_allocator)|`inner_allocator_type` 型の格納されているオブジェクトへの参照を取得します。|
|[max_size](#max_size)|外側のアロケーターが割り当てることができるオブジェクトの最大数を指定します。|
|[outer_allocator](#outer_allocator)|`outer_allocator_type` 型の格納されているオブジェクトへの参照を取得します。|
|[select_on_container_copy_construction](#select_on_container_copy_construction)|対応するアロケーターごとに `select_on_container_copy_construction` を呼び出すことによって、格納されている各アロケーター オブジェクトが初期化された新しい `scoped_allocator_adaptor` オブジェクトを作成します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_as)||
|[演算子==](#op_eq_eq)||
|[演算子!=](#op_noeq)||

## <a name="requirements"></a>必要条件

**ヘッダー:** \<scoped_allocator>

**名前空間:** std

## <a name="scoped_allocator_adaptorallocate"></a><a name="allocate"></a>scoped_allocator_adaptor:割り当て

`Outer` アロケーターを使用してメモリを割り当てます。

```cpp
pointer allocate(size_type count);pointer allocate(size_type count, const_void_pointer hint);
```

### <a name="parameters"></a>パラメーター

*カウント*\
十分な記憶域を割り当てる要素の数。

*ヒント*\
要求の前に割り当てられたオブジェクトのアドレスを見つけることによって、アロケーター オブジェクトを支援できるポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数は `Outer_traits::allocate(outer_allocator(), count)` を返します。 2 番目のメンバー関数は `Outer_traits::allocate(outer_allocator(), count, hint)` を返します。

## <a name="scoped_allocator_adaptorconstruct"></a><a name="construct"></a>scoped_allocator_adaptor::コンストラクト

オブジェクトを構築します。

```cpp
template <class Ty, class... Atypes>
void construct(Ty* ptr, Atypes&&... args);

template <class Ty1, class Ty2, class... Atypes1, class... Atypes2>
void construct(pair<Ty1, Ty2>* ptr, piecewise_construct_t,
    tuple<Atypes1&&...>
first, tuple<Atypes1&&...> second);

template <class Ty1, class Ty2>
void construct(pair<Ty1, Ty2>* ptr);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr,
    class Uy1&& first, class Uy2&& second);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, const pair<Uy1, Uy2>& right);

template <class Ty1, class Ty2, class Uy1, class Uy2>
void construct(pair<Ty1, Ty2>* ptr, pair<Uy1, Uy2>&& right);
```

### <a name="parameters"></a>パラメーター

*Ptr*\
オブジェクトが構築されるメモリの場所へのポインター。

*Args*\
引数リスト。

*まずは*\
ペアの最初の型のオブジェクト。

*2 番目*\
ペアの 2 番目の型のオブジェクト。

*そうです*\
移動またはコピーされる既存のオブジェクト。

### <a name="remarks"></a>解説

最初のメソッドは、 を`Outermost_traits::construct(OUTERMOST(*this), ptr, xargs...)``xargs...`呼び出すことによって*ptr*でオブジェクトを構築します。

- `uses_allocator<Ty, inner_allocator_type>` が false を保持する場合、`xargs...` は `args...` です。

- `uses_allocator<Ty, inner_allocator_type>` が true を保持し、`is_constructible<Ty, allocator_arg_t, inner_allocator_type, args...>` が true を保持する場合、`xargs...` は `allocator_arg, inner_allocator(), args...` です。

- `uses_allocator<Ty, inner_allocator_type>` が true を保持し、`is_constructible<Ty, args..., inner_allocator()>` が true を保持する場合、`xargs...` は `args..., inner_allocator()` です。

2 番目のメソッドは、 を呼び出`Outermost_traits::construct(OUTERMOST(*this), &ptr->first, xargs...)`すことによって*ptr*でペア オブジェクトを構築します`Outermost_traits::construct(OUTERMOST(*this), &ptr->second, xargs...)``xargs...``second...`。 `xargs...` `first...`

3 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, tuple<>, tuple<>)` と同じです。

4 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(first), forward_as_tuple(std::forward<Uy2>(second))` と同じです。

5 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, forward_as_tuple(right.first), forward_as_tuple(right.second))` と同じです。

6 番目のメソッドの動作は `this->construct(ptr, piecewise_construct, forward_as_tuple(std::forward<Uy1>(right.first), forward_as_tuple(std::forward<Uy2>(right.second))` と同じです。

## <a name="scoped_allocator_adaptordeallocate"></a><a name="deallocate"></a>scoped_allocator_adaptor::d割り当て

外側のアロケーターを使用してオブジェクトの割り当てを解除します。

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>パラメーター

*Ptr*\
割り当てを解除されるオブジェクトの開始位置へのポインター。

*カウント*\
割り当てを解除するオブジェクトの数。

## <a name="scoped_allocator_adaptordestroy"></a><a name="destroy"></a>scoped_allocator_adaptor::dエストロイ

指定したオブジェクトを破棄します。

```cpp
template <class Ty>
void destroy(Ty* ptr)
```

### <a name="parameters"></a>パラメーター

*Ptr*\
破棄するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

`Outermost_traits::destroy(OUTERMOST(*this), ptr)`

## <a name="scoped_allocator_adaptorinner_allocator"></a><a name="inner_allocator"></a>scoped_allocator_adaptor::inner_allocator

`inner_allocator_type` 型の格納されているオブジェクトへの参照を取得します。

```cpp
inner_allocator_type& inner_allocator() noexcept;
const inner_allocator_type& inner_allocator() const noexcept;
```

### <a name="return-value"></a>戻り値

`inner_allocator_type` 型の格納されているオブジェクトへの参照。

## <a name="scoped_allocator_adaptormax_size"></a><a name="max_size"></a>scoped_allocator_adaptor::max_size

外側のアロケーターが割り当てることができるオブジェクトの最大数を指定します。

```cpp
size_type max_size();
```

### <a name="return-value"></a>戻り値

`Outer_traits::max_size(outer_allocator())`

## <a name="a-nameop_as--scoped_allocator_adaptoroperator"></a><a name="op_as">scoped_allocator_adaptor::演算子=

```cpp
scoped_allocator_adaptor& operator=(const scoped_allocator_adaptor&) = default;
scoped_allocator_adaptor& operator=(scoped_allocator_adaptor&&) = default;
```

## <a name="a-nameop_eq_eq--scoped_allocator_adaptoroperator"></a><a name="op_eq_eq">scoped_allocator_adaptor::演算子==

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator==(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="a-nameop_noeq--scoped_allocator_adaptoroperator"></a><a name="op_noeq">scoped_allocator_adaptor::演算子!=

```cpp
template <class OuterA1, class OuterA2, class... InnerAllocs>
bool operator!=(const scoped_allocator_adaptor<OuterA1, InnerAllocs...>& a,
const scoped_allocator_adaptor<OuterA2, InnerAllocs...>& b) noexcept;
```

## <a name="scoped_allocator_adaptorouter_allocator"></a><a name="outer_allocator"></a>scoped_allocator_adaptor::outer_allocator

`outer_allocator_type` 型の格納されているオブジェクトへの参照を取得します。

```cpp
outer_allocator_type& outer_allocator() noexcept;
const outer_allocator_type& outer_allocator() const noexcept;
```

### <a name="return-value"></a>戻り値

`outer_allocator_type` 型の格納されているオブジェクトへの参照。

## <a name="scoped_allocator_adaptorrebind-struct"></a><a name="rebind_struct"></a>scoped_allocator_adaptor::構造体の再バインド

`scoped_allocator_adaptor\<Other, Inner...>` のシノニムとして `Outer::rebind\<Other>::other` 型を定義します。

構造体の再バインド { typedef Other_traits::他の>Other_allocを再バインド\<> Other_alloc scoped_allocator_adaptor\<します。

## <a name="scoped_allocator_adaptorscoped_allocator_adaptor-constructor"></a><a name="scoped_allocator_adaptor"></a>scoped_allocator_adaptor::scoped_allocator_adaptorコンストラクタ

`scoped_allocator_adaptor` オブジェクトを構築します。 また、デストラクターが含まれています。

```cpp
scoped_allocator_adaptor();

scoped_allocator_adaptor(const scoped_allocator_adaptor& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
const scoped_allocator_adaptor<Outer2, Inner...>& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(
scoped_allocator_adaptor<Outer2, Inner...>&& right) noexcept;
template <class Outer2>
scoped_allocator_adaptor(Outer2&& al,
    const Inner&... rest) noexcept;

~scoped_allocator_adaptor();
```

### <a name="parameters"></a>パラメーター

*そうです*\
既存の `scoped_allocator_adaptor`。

*アル*\
外側のアロケーターとして使用する既存のアロケーター。

*残り*\
内側のアロケーターとして使用するアロケーターのリスト。

### <a name="remarks"></a>解説

1 番目のコンストラクターは、格納されているアロケーター オブジェクトを既定で構築します。 次の 3 つのコンストラクターのそれぞれは、*右*の対応するオブジェクトから、格納されたアロケーター オブジェクトを構築します。 最後のコンストラクターは、引数リストの対応する引数から、格納されているアロケーター オブジェクトを構築します。

## <a name="scoped_allocator_adaptorselect_on_container_copy_construction"></a><a name="select_on_container_copy_construction"></a>scoped_allocator_adaptor::select_on_container_copy_construction

対応するアロケーターごとに `select_on_container_copy_construction` を呼び出すことによって、格納されている各アロケーター オブジェクトが初期化された新しい `scoped_allocator_adaptor` オブジェクトを作成します。

```cpp
scoped_allocator_adaptor select_on_container_copy_construction();
```

### <a name="return-value"></a>戻り値

このメソッドは、実質的に `scoped_allocator_adaptor(Outer_traits::select_on_container_copy_construction(*this), inner_allocator().select_on_container_copy_construction())` を返します。 結果は、新しい`scoped_allocator_adaptor`オブジェクトであり、それぞれの格納されたアロケーター オブジェクト`al.select_on_container_copy_construction()`が、対応するアロケーター *al*を呼び出して初期化されます。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
