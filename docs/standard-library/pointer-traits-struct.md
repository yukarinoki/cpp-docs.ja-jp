---
description: '詳細については、次を参照してください: pointer_traits 構造体'
title: pointer_traits 構造体
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
ms.openlocfilehash: ba89d4df45517c142cad172860e4c9ab4d386ce1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340685"
---
# <a name="pointer_traits-struct"></a>pointer_traits 構造体

`allocator_traits`ポインター型を持つアロケーターを記述するために、型のオブジェクトに必要な情報を提供 `Ptr` します。

## <a name="syntax"></a>構文

```cpp
template <class Ptr>
    struct pointer_traits;
```

## <a name="remarks"></a>解説

Ptr には `Ty *` 型の生のポインターまたは次のプロパティを持つクラスを指定できます。

```cpp
struct Ptr
{ // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj); // optional
};
```

## <a name="members"></a>メンバー

### <a name="typedefs"></a>Typedefs

|名前|説明|
|-|-|
|`typedef T2 difference_type`|`T2` 型は、その型が存在する場合は `Ptr::difference_type`、それ以外の場合は `ptrdiff_t` です。 `Ptr` が生のポインターの場合、型は `ptrdiff_t` です。|
|`typedef T1 element_type`|`T1` 型は、その型が存在する場合は `Ptr::element_type`、それ以外の場合は `Ty` です。 `Ptr` が生のポインターの場合、型は `Ty` です。|
|`typedef Ptr pointer`|種類は `Ptr` です。|

### <a name="structs"></a>構造体

|名前|説明|
|-|-|
|`rebind`|基になるポインター型を指定された型に変換しようとします。|

### <a name="methods"></a>メソッド

|名前|説明|
|----------|-----------------|
|[pointer_to](#pointer_to)|任意の参照をクラス `Ptr` のオブジェクトに変換します。|

### <a name="pointer_to"></a><a name="pointer_to"></a> pointer_to

その関数が存在する場合に `Ptr::pointer_to(obj)` を返す静的メソッド。 それ以外の場合は、任意の参照をクラス `Ptr` のオブジェクトに変換できません。 `Ptr` が生のポインターの場合、このメソッドは `addressof(obj)` を返します。

```cpp
static pointer pointer_to(element_type& obj);
```
