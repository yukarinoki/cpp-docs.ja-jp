---
description: '詳細情報: sync_shared クラス'
title: sync_shared クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
ms.openlocfilehash: 4093b85ce6f10552cba462074aee2a448cc5ce3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183283"
---
# <a name="sync_shared-class"></a>sync_shared クラス

すべてのアロケーターによって共有されているキャッシュ オブジェクトへのアクセスを制御するためにミューテックスを使用する[同期フィルター](../standard-library/allocators-header.md)を表します。

## <a name="syntax"></a>構文

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>パラメーター

*Cache*\
同期フィルターに関連付けられているキャッシュの型。 、、またはを指定でき [`cache_chunklist`](../standard-library/cache-chunklist-class.md) [`cache_freelist`](../standard-library/cache-freelist-class.md) [`cache_suballoc`](../standard-library/cache-suballoc-class.md) ます。

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割当て](#allocate)|メモリのブロックを割り当てます。|
|[配置](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a> sync_shared:: allocate

メモリのブロックを割り当てます。

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>パラメーター

*数*\
割り当てられる配列内の要素の数。

### <a name="return-value"></a>戻り値

割り当てられたオブジェクトへのポインター。

### <a name="remarks"></a>解説

メンバー関数はミューテックスをロックし、`cache.allocate(count)` を呼び出し、ミューテックスをロック解除し、以前の `cache.allocate(count)` の呼び出しの結果を返します。 `cache` はキャッシュ オブジェクトを表します。

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a> sync_shared::d eallocate

指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
記憶域から割り当てを解除される最初のオブジェクトへのポインター。

*数*\
記憶域から割り当てを解除されるオブジェクトの数。

### <a name="remarks"></a>解説

このメンバー関数は、ミューテックスをロックし、`cache.deallocate(ptr, count)` (`cache` はキャッシュ オブジェクトを表す) を呼び出し、その後ミューテックスをロック解除します。

## <a name="sync_sharedequals"></a><a name="equals"></a> sync_shared:: equals

2 つのキャッシュが等しいかどうかを比較します。

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>パラメーター

*Cache*\
同期フィルターに関連付けられているキャッシュの型。

*他の*\
等しいかどうかを比較するキャッシュ。

### <a name="return-value"></a>戻り値

**`true`** の結果が `cache.equals(Other.cache)` `cache` キャッシュオブジェクトを表している場合は。 **`true`** それ以外 **`false`** の場合は。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
