---
title: sync_none クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
ms.openlocfilehash: 046cbca30b6cdef2dc4e7dbbe2791d52384d9f25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376573"
---
# <a name="sync_none-class"></a>sync_none クラス

同期を提供しない[同期フィルター](../standard-library/allocators-header.md)を表します。

## <a name="syntax"></a>構文

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Cache`|同期フィルターに関連付けられているキャッシュの型。 これは、[cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割り当てる](#allocate)|メモリのブロックを割り当てます。|
|[解放](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="sync_noneallocate"></a><a name="allocate"></a>sync_none::割り当て

メモリのブロックを割り当てます。

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*count*|割り当てられる配列内の要素の数。|

### <a name="remarks"></a>解説

このメンバー関数は `cache.allocate(count)` を返します。ここで、`cache` はキャッシュ オブジェクトです。

## <a name="sync_nonedeallocate"></a><a name="deallocate"></a>sync_none::d割り当て

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

このメンバー関数は `cache.deallocate(ptr, count)` を呼び出します。ここで、`cache` はキャッシュ オブジェクトを表します。

## <a name="sync_noneequals"></a><a name="equals"></a>sync_none::等しい

2 つのキャッシュが等しいかどうかを比較します。

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Cache*|同期フィルターのキャッシュ オブジェクト。|
|*その他*|等しいかどうかを比較するキャッシュ オブジェクト。|

### <a name="return-value"></a>戻り値

メンバー関数は常に**true**を返します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
