---
title: sync_shared クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e275bd195c11b605891b250e9264bad587eb853
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33865608"
---
# <a name="syncshared-class"></a>sync_shared クラス

すべてのアロケーターによって共有されているキャッシュ オブジェクトへのアクセスを制御するためにミューテックスを使用する[同期フィルター](../standard-library/allocators-header.md)を表します。

## <a name="syntax"></a>構文

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Cache`|同期フィルターに関連付けられているキャッシュの型。 これは、[cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocate](#allocate)|メモリのブロックを割り当てます。|
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="allocate"></a>  sync_shared::allocate

メモリのブロックを割り当てます。

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`count`|割り当てられる配列内の要素の数。|

### <a name="return-value"></a>戻り値

割り当てられたオブジェクトへのポインター。

### <a name="remarks"></a>コメント

メンバー関数はミューテックスをロックし、`cache.allocate(count)` を呼び出し、ミューテックスをロック解除し、以前の `cache.allocate(count)` の呼び出しの結果を返します。 `cache` はキャッシュ オブジェクトを表します。

## <a name="deallocate"></a>  sync_shared::deallocate

指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`ptr`|記憶域から割り当てを解除される最初のオブジェクトへのポインター。|
|`count`|記憶域から割り当てを解除されるオブジェクトの数。|

### <a name="remarks"></a>コメント

このメンバー関数は、ミューテックスをロックし、`cache.deallocate(ptr, count)` (`cache` はキャッシュ オブジェクトを表す) を呼び出し、その後ミューテックスをロック解除します。

## <a name="equals"></a>  sync_shared::equals

2 つのキャッシュが等しいかどうかを比較します。

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Cache`|同期フィルターに関連付けられているキャッシュの型。|
|`Other`|等しいかどうかを比較するキャッシュ。|

### <a name="return-value"></a>戻り値

`cache.equals(Other.cache)` (`cache` はキャッシュ オブジェクトを表す) の結果が `true` の場合は `true`、それ以外の場合は `false`。

### <a name="remarks"></a>コメント

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)<br/>
