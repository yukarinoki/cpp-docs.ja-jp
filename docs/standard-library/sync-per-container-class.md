---
title: sync_per_container クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: d38307c4ae19e5f87d0dbcca8943dc1c3f239917
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232899"
---
# <a name="sync_per_container-class"></a>sync_per_container クラス

アロケーター オブジェクトごとに個別のキャッシュ オブジェクトを提供する[同期フィルター](../standard-library/allocators-header.md)を記述します。

## <a name="syntax"></a>構文

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>パラメーター

|パラメーター|[説明]|
|---------------|-----------------|
|*キャッシュ*|同期フィルターに関連付けられているキャッシュの型。 これは、[cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="sync_per_containerequals"></a><a name="equals"></a>sync_per_container:: equals

2 つのキャッシュが等しいかどうかを比較します。

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|[説明]|
|---------------|-----------------|
|*キャッシュ*|同期フィルターのキャッシュ オブジェクト。|
|*その他*|等しいかどうかを比較するキャッシュ オブジェクト。|

### <a name="return-value"></a>戻り値

このメンバー関数は常にを返し **`false`** ます。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
