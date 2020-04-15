---
title: cache_chunklist クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: d0dd6176a34bd625069511106c491225d1467d08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366756"
---
# <a name="cache_chunklist-class"></a>cache_chunklist クラス

1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Sz*|割り当てられる配列内の要素の数。|

## <a name="remarks"></a>解説

このクラス テンプレートでは **、演算子 new**を使用して生メモリのチャンクを割り当て、必要に応じてメモリ ブロックの記憶域を割り当てるブロックをサブアローケートします。割り当て解除されたメモリ ブロックはチャンクごとに別の空きリストに格納され、使用されているメモリ ブロックがまったくない場合は **、演算子 delete**を使用してチャンクの割り当てを解除します。

各メモリ ブロックは、使用できるメモリの*Sz*バイトと、それが属するチャンクへのポインタを保持します。 各チャンクには`Nelts`、メモリブロック、3つのポインタ、int、**および演算子 new**および**operator delete**が必要とするデータが保持されます。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割り当てる](#allocate)|メモリのブロックを割り当てます。|
|[解放](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="cache_chunklistallocate"></a><a name="allocate"></a>cache_chunklist:割り当て

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

## <a name="cache_chunklistcache_chunklist"></a><a name="cache_chunklist"></a>cache_chunklist::cache_chunklist

`cache_chunklist` 型のオブジェクトを構築します。

```cpp
cache_chunklist();
```

### <a name="remarks"></a>解説

## <a name="cache_chunklistdeallocate"></a><a name="deallocate"></a>cache_chunklist::d割り当て

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

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)
