---
description: '詳細情報: cache_suballoc クラス'
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
ms.openlocfilehash: 9df13155101a77d327c8bdee9da1fe03bfa00366
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325370"
---
# <a name="cache_suballoc-class"></a>cache_suballoc クラス

1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>パラメーター

*Sz*\
割り当てられる配列内の要素の数。

## <a name="remarks"></a>解説

Cache_suballoc クラステンプレートでは、を使用して、割り当てが解除されたメモリブロックをフリーリストに格納 `freelist<sizeof(Type), max_unbounded>` します。また、フリーリストが空の場合は、 **new 演算子** で割り当てられた大きなチャンクからメモリブロックを割り当てます。

各チャンクは、 `Sz * Nelts` 使用可能なメモリのバイト数と、 **operator new** および **operator delete** に必要なデータを保持します。 割り当てたチャンクが解放されることはありません。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[cache_suballoc](#cache_suballoc)|`cache_suballoc` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割当て](#allocate)|メモリのブロックを割り当てます。|
|[配置](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="cache_suballocallocate"></a><a name="allocate"></a> cache_suballoc:: allocate

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

## <a name="cache_suballoccache_suballoc"></a><a name="cache_suballoc"></a> cache_suballoc:: cache_suballoc

`cache_suballoc` 型のオブジェクトを構築します。

```cpp
cache_suballoc();
```

### <a name="remarks"></a>解説

## <a name="cache_suballocdeallocate"></a><a name="deallocate"></a> cache_suballoc::d eallocate

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

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)
