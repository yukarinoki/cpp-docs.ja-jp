---
title: '&lt;allocators&gt; マクロ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- allocators/std::ALLOCATOR_DECL
- allocators/std::CACHE_CHUNKLIST
- allocators/std::CACHE_FREELIST
- allocators/std::CACHE_SUBALLOC
- allocators/std::SYNC_DEFAULT
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
helpviewer_keywords:
- std::ALLOCATOR_DECL [C++]
- std::CACHE_CHUNKLIST [C++]
- std::CACHE_FREELIST [C++]
- std::CACHE_SUBALLOC [C++]
- std::SYNC_DEFAULT [C++]
ms.openlocfilehash: a24b854ac37dc0dfed44aec33fc1fb7e0bedcfc5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ltallocatorsgt-macros"></a>&lt;allocators&gt; マクロ

||||
|-|-|-|
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|

## <a name="allocator_decl"></a>  ALLOCATOR_DECL

アロケーター テンプレート クラスを生成します。

```cpp
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```

### <a name="remarks"></a>コメント

マクロはテンプレート定義 `template <class Type> class name {.....}` と特殊化 `template <> class name<void> {.....}` を生成します。これらは両方で同期フィルター `sync` と型 `cache` のキャッシュを使用するアロケーター テンプレート クラスを定義します。

再バインドをコンパイルできるコンパイラの場合、作成されるテンプレート定義は次のようになります。

```cpp
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };
```

再バインドをコンパイルできないコンパイラの場合、作成されるテンプレート定義は次のようになります。

```cpp
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```

## <a name="cache_chunklist"></a>  CACHE_CHUNKLIST

`stdext::allocators::cache_chunklist<sizeof(Type)>` を生成します。

```cpp
#define CACHE_CHUNKLIST <cache_class>
```

### <a name="remarks"></a>コメント

## <a name="cache_freelist"></a>  CACHE_FREELIST

`stdext::allocators::cache_freelist<sizeof(Type), max>` を生成します。

```cpp
#define CACHE_FREELIST(max) <cache_class>
```

### <a name="remarks"></a>コメント

## <a name="cache_suballoc"></a>  CACHE_SUBALLOC

`stdext::allocators::cache_suballoc<sizeof(Type)>` を生成します。

```cpp
#define CACHE_SUBALLOC <cache_class>
```

### <a name="remarks"></a>コメント

## <a name="sync_default"></a>  SYNC_DEFAULT

同期フィルターを生成します。

```cpp
#define SYNC_DEFAULT <sync_template>
```

### <a name="remarks"></a>コメント

コンパイラがシングル スレッド アプリケーションとマルチ スレッド アプリケーションの両方のコンパイルをサポートしている場合、マクロはシングル スレッド アプリケーションには `stdext::allocators::sync_none` を生成し、それ以外の場合は `stdext::allocators::sync_shared` を生成します。

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)<br/>
