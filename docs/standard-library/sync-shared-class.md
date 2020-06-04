---
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
ms.openlocfilehash: 029edea59f29534491232d5d99353ccb093447bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376536"
---
# <a name="sync_shared-class"></a>sync_shared クラス

すべてのアロケーターによって共有されているキャッシュ オブジェクトへのアクセスを制御するためにミューテックスを使用する[同期フィルター](../standard-library/allocators-header.md)を表します。

## <a name="syntax"></a>構文

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Cache*|同期フィルターに関連付けられているキャッシュの型。 これは、[cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割り当てる](#allocate)|メモリのブロックを割り当てます。|
|[解放](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a>sync_shared::割り当て

メモリのブロックを割り当てます。

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*count*|割り当てられる配列内の要素の数。|

### <a name="return-value"></a>戻り値

割り当てられたオブジェクトへのポインター。

### <a name="remarks"></a>解説

メンバー関数はミューテックスをロックし、`cache.allocate(count)` を呼び出し、ミューテックスをロック解除し、以前の `cache.allocate(count)` の呼び出しの結果を返します。 `cache` はキャッシュ オブジェクトを表します。

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a>sync_shared::d割り当て

指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ptr*|記憶域から割り当てを解除される最初のオブジェクトへのポインター。|
|*count*|記憶域から割り当てを解除されるオブジェクトの数。|

### <a name="remarks"></a>解説

このメンバー関数は、ミューテックスをロックし、`cache.deallocate(ptr, count)` (`cache` はキャッシュ オブジェクトを表す) を呼び出し、その後ミューテックスをロック解除します。

## <a name="sync_sharedequals"></a><a name="equals"></a>sync_shared::等しい

2 つのキャッシュが等しいかどうかを比較します。

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Cache*|同期フィルターに関連付けられているキャッシュの型。|
|*その他*|等しいかどうかを比較するキャッシュ。|

### <a name="return-value"></a>戻り値

の結果が`cache`true の場合は**true、** **true** `cache.equals(Other.cache)`それ以外の場合**は false。**

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
