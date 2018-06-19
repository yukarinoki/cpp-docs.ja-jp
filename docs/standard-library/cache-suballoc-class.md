---
title: cache_suballoc クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28dc4e52e2f114600ad3a22697500ce9d8594113
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850308"
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
|`Sz`|割り当てられる配列内の要素の数。|

## <a name="remarks"></a>コメント

cache_suballoc テンプレート クラスは、`freelist<sizeof(Type), max_unbounded>` を使用して、割り当てが解除されたメモリ ブロックを無限の長さのフリー リストに格納し、フリー リストが空になると、`operator new` で割り当てられた大きいチャンクからメモリ ブロックをサブ割り当てします。

各チャンクは `Sz * Nelts` バイトの使用可能なメモリと、`operator new` および `operator delete` に必要なデータを保持します。 割り当てたチャンクが解放されることはありません。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[cache_suballoc](#cache_suballoc)|`cache_suballoc` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocate](#allocate)|メモリのブロックを割り当てます。|
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>要件

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
|`count`|割り当てられる配列内の要素の数。|

### <a name="return-value"></a>戻り値

割り当てられたオブジェクトへのポインター。

### <a name="remarks"></a>コメント

## <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc

`cache_suballoc` 型のオブジェクトを構築します。

```cpp
cache_suballoc();
```

### <a name="remarks"></a>コメント

## <a name="deallocate"></a>  cache_suballoc::deallocate

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

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)<br/>
