---
description: '詳細情報: cache_chunklist クラス'
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
ms.openlocfilehash: 264713ed12727d45928f40f2bc6a790e0e3b1db1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325399"
---
# <a name="cache_chunklist-class"></a>cache_chunklist クラス

1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>パラメーター

*Sz*\
割り当てられる配列内の要素の数。

## <a name="remarks"></a>解説

このクラステンプレートは、 **operator new** を使用して生メモリのチャンクを割り当てます。また、必要に応じてメモリブロックにストレージを割り当てるようにブロックを割り当てます。割り当て解除されたメモリブロックをチャンクごとに個別のフリーリストに格納し、 **operator delete** を使用して、メモリブロックが使用されていない場合にチャンクの割り当てを解除します。

各メモリブロックは、使用可能なメモリの *Sz* バイトとそれが属するチャンクへのポインターを保持します。 各チャンクは `Nelts` 、メモリブロック、3つのポインター、int、 **operator new** および **operator delete** に必要なデータを保持します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割当て](#allocate)|メモリのブロックを割り当てます。|
|[配置](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="cache_chunklistallocate"></a><a name="allocate"></a> cache_chunklist:: allocate

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

## <a name="cache_chunklistcache_chunklist"></a><a name="cache_chunklist"></a> cache_chunklist:: cache_chunklist

`cache_chunklist` 型のオブジェクトを構築します。

```cpp
cache_chunklist();
```

### <a name="remarks"></a>解説

## <a name="cache_chunklistdeallocate"></a><a name="deallocate"></a> cache_chunklist::d eallocate

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
