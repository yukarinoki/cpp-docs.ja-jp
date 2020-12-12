---
description: '詳細情報: allocator_base クラス'
title: allocator_base クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
helpviewer_keywords:
- stdext::allocator_base [C++]
- stdext::allocators [C++], allocator_base
- stdext::allocator_base [C++], const_pointer
- stdext::allocator_base [C++], const_reference
- stdext::allocator_base [C++], difference_type
- stdext::allocator_base [C++], pointer
- stdext::allocator_base [C++], reference
- stdext::allocator_base [C++], size_type
- stdext::allocator_base [C++], value_type
- stdext::allocator_base [C++], _Charalloc
- stdext::allocator_base [C++], _Chardealloc
- stdext::allocator_base [C++], address
- stdext::allocator_base [C++], allocate
- stdext::allocator_base [C++], construct
- stdext::allocator_base [C++], deallocate
- stdext::allocator_base [C++], destroy
- stdext::allocator_base [C++], max_size
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
ms.openlocfilehash: 95da41fd480101c26a2ab71b445790da47144189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163640"
---
# <a name="allocator_base-class"></a>allocator_base クラス

同期フィルターからユーザー定義のアロケーターを作成するために必要な、基底クラスと共通の関数を定義します。

## <a name="syntax"></a>構文

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>パラメーター

*各種*\
アロケーターによって割り当てられた要素の型。

*頻度*\
アロケーターの同期ポリシー。[sync_none クラス](sync-none-class.md)、[sync_per_container クラス](sync-per-container-class.md)、[sync_per_thread クラス](sync-per-thread-class.md)、[sync_shared クラス](sync-shared-class.md)のいずれかです。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[allocator_base](#allocator_base)|`allocator_base` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[const_pointer](#const_pointer)|アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。|
|[const_reference](#const_reference)|アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。|
|[difference_type](#difference_type)|アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。|
|[pointer](#pointer)|アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。|
|[reference](#reference)|アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。|
|[size_type](#size_type)|型のオブジェクトが割り当てることができる任意のシーケンスの長さを表すことができる符号なし整数型 `allocator_base` 。|
|[value_type](#value_type)|アロケーターによって管理される型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[_Charalloc](#charalloc)|型の配列のストレージを割り当て **`char`** ます。|
|[_Chardealloc](#chardealloc)|型の要素を含む配列のストレージを解放 **`char`** します。|
|[address](#address)|値が指定されたオブジェクトのアドレスを検索します。|
|[割当て](#allocate)|指定された要素数だけは格納できるメモリのブロックを割り当てます。|
|[構築](#construct)|指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。|
|[配置](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|
|[倒す](#destroy)|オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。|
|[max_size](#max_size)|空きメモリがすべて使用される前にクラス アロケーター オブジェクトによって割り当てることのできる、*Type* 型の要素の数を返します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="allocator_base_charalloc"></a><a name="charalloc"></a> allocator_base:: _Charalloc

型の配列のストレージを割り当て **`char`** ます。

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>パラメーター

*数*\
割り当てられる配列内の要素の数。

### <a name="return-value"></a>戻り値

割り当てられたオブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、再バインドをコンパイルできないコンパイラでコンパイルした場合に、コンテナーによって使用されます。 この関数は、同期フィルターの `allocate` 関数への呼び出しの結果を返すことで、ユーザー定義のアロケーターに `_Charalloc` を実装します。

## <a name="allocator_base_chardealloc"></a><a name="chardealloc"></a> allocator_base:: _Chardealloc

型の要素を含む配列のストレージを解放 **`char`** します。

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
記憶域から割り当てを解除される最初のオブジェクトへのポインター。

*数*\
記憶域から割り当てを解除されるオブジェクトの数。

### <a name="remarks"></a>解説

このメンバー関数は、再バインドをコンパイルできないコンパイラでコンパイルした場合に、コンテナーによって使用されます。 この関数は、同期フィルターの `deallocate` 関数を呼び出すことで、ユーザー定義のアロケーターに `_Chardealloc` を実装します。 と `_Charalloc` 等しいを比較し **`*this`** 、同じサイズと型の配列オブジェクトを割り当てるアロケーターオブジェクトに対して、への呼び出しによってポインター ptr が既に返されている必要があります。 `_Chardealloc` は例外をスローしません。

## <a name="allocator_baseaddress"></a><a name="address"></a> allocator_base:: address

値が指定されたオブジェクトのアドレスを検索します。

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>パラメーター

*val*\
アドレスが検索対象となっているオブジェクトの const 値または nonconst 値。

### <a name="return-value"></a>戻り値

見つかった const 値または nonconst 値のそれぞれのオブジェクトに対する const ポインターまたは nonconst ポインター。

### <a name="remarks"></a>解説

このメンバー関数は、`&val` を返すことで、ユーザー定義のアロケーターに実装されます。

## <a name="allocator_baseallocate"></a><a name="allocate"></a> allocator_base:: allocate

指定された要素数だけは格納できるメモリのブロックを割り当てます。

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>パラメーター

*_Nx*\
割り当てられる配列内の要素の数。

*_Hint*\
このパラメーターは無視されます。

### <a name="return-value"></a>戻り値

割り当てられたオブジェクトへのポインター。

### <a name="remarks"></a>解説

メンバー関数は、`_Nx == 1` の場合、Type `*` 型の同期フィルターの `allocate` 関数への呼び出しの結果を返すことで、ユーザー定義のアロケーターにメモリ割り当てを実装します。それ以外の場合は、`operator new(_Nx * sizeof(Type))` への呼び出しの結果を返すことで、Type `*` 型にキャストします。

## <a name="allocator_baseallocator_base"></a><a name="allocator_base"></a> allocator_base:: allocator_base

`allocator_base` 型のオブジェクトを構築します。

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
コピーするアロケーター オブジェクト。

### <a name="remarks"></a>解説

1 つ目のコンストラクターは、[allocator_base](allocator-base-class.md) インスタンスを構築します。 2 番目のコンストラクターは、`allocator_base<Type, _Sync>` インスタンス `a`、`allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a` などのいずれかに対し、`allocator_base` インスタンスを構築します。

## <a name="allocator_baseconst_pointer"></a><a name="const_pointer"></a> allocator_base:: const_pointer

アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。

```cpp
typedef const Type *const_pointer;
```

## <a name="allocator_baseconst_reference"></a><a name="const_reference"></a> allocator_base:: const_reference

アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。

```cpp
typedef const Type& const_reference;
```

## <a name="allocator_baseconstruct"></a><a name="construct"></a> allocator_base:: construct

指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
オブジェクトが構築される場所へのポインター。

*val*\
構築されるオブジェクトが初期化される値。

### <a name="remarks"></a>解説

このメンバー関数は、`new((void*)ptr Type(val)` を呼び出すことで、ユーザー定義のアロケーターに実装されます。

## <a name="allocator_basedeallocate"></a><a name="deallocate"></a> allocator_base::d eallocate

指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
記憶域から割り当てを解除される最初のオブジェクトへのポインター。

*_Nx*\
記憶域から割り当てを解除されるオブジェクトの数。

### <a name="remarks"></a>解説

このメンバー関数は、`_Nx == 1` の場合は同期フィルター `Sync` で `deallocate(ptr)` を呼び出すことで、それ以外の場合は `operator delete(_Nx * ptr)` を呼び出すことで、ユーザー定義のアロケーターに実装されます。

## <a name="allocator_basedestroy"></a><a name="destroy"></a> allocator_base::d estroy

オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
破棄するオブジェクトのアドレスを指定するポインター。

### <a name="remarks"></a>解説

このメンバー関数は、`ptr->~Type()` を呼び出すことで、ユーザー定義のアロケーターに実装されます。

## <a name="allocator_basedifference_type"></a><a name="difference_type"></a> allocator_base::d ifference_type

アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="allocator_basemax_size"></a><a name="max_size"></a> allocator_base:: max_size

空きメモリがすべて使用される前にクラス アロケーター オブジェクトによって割り当てることのできる、型 `Type` の要素の数を返します。

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>戻り値

割り当てることができる要素の数。

### <a name="remarks"></a>解説

このメンバー関数は、`0 < (size_t)-1 / sizeof(Type)` の場合は `(size_t)-1 / sizeof(Type)` を返すことで、それ以外は `1` を返すことで、ユーザー定義のアロケーターに実装されます。

## <a name="allocator_basepointer"></a><a name="pointer"></a> allocator_base::p ointer

アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。

```cpp
typedef Type *pointer;
```

## <a name="allocator_basereference"></a><a name="reference"></a> allocator_base:: reference

アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。

```cpp
typedef Type& reference;
```

## <a name="allocator_basesize_type"></a><a name="size_type"></a> allocator_base:: size_type

型のオブジェクトが割り当てることができる任意のシーケンスの長さを表すことができる符号なし整数型 `allocator_base` 。

```cpp
typedef std::size_t size_type;
```

## <a name="allocator_basevalue_type"></a><a name="value_type"></a> allocator_base:: value_type

アロケーターによって管理される型。

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>関連項目

[\<allocators>](allocators-header.md)
