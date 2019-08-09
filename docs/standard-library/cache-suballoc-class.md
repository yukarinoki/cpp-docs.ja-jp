---
title: cache_suballoc クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: aa0ceda69fc169593719c3a4f81d308bb6cde284
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449656"
---
# <a name="cachesuballoc-class"></a>cache_suballoc クラス

1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Sz*|割り当てられる配列内の要素の数。|

## <a name="remarks"></a>Remarks

Cache_suballoc テンプレートクラスは、を使用して`freelist<sizeof(Type), max_unbounded>`、割り当てが解除されたメモリブロックをフリーリストに格納します。また、フリーリストが空の場合は、 **new 演算子**で割り当てられた大きなチャンクからメモリブロックを割り当てます。

各チャンクは`Sz * Nelts` 、使用可能なメモリのバイト数と、 **operator new**および**operator delete**に必要なデータを保持します。 割り当てたチャンクが解放されることはありません。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[cache_suballoc](#cache_suballoc)|`cache_suballoc` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocate](#allocate)|メモリのブロックを割り当てます。|
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="allocate"></a>  cache_suballoc::allocate

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

### <a name="remarks"></a>Remarks

## <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc

`cache_suballoc` 型のオブジェクトを構築します。

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Remarks

## <a name="deallocate"></a>  cache_suballoc::deallocate

指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ptr*|記憶域から割り当てを解除される最初のオブジェクトへのポインター。|
|*count*|記憶域から割り当てを解除されるオブジェクトの数。|

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
