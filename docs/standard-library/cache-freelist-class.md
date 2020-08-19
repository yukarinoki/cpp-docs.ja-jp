---
title: cache_freelist クラス
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
ms.openlocfilehash: bbe0ff0f2297afcec99bd162ebe6a6d3e10f9bce
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560727"
---
# <a name="cache_freelist-class"></a>cache_freelist クラス

1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>パラメーター

*Sz*\
割り当てられる配列内の要素の数。

*制限*\
フリー リストの最大サイズを表す max クラスです。 [max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md)、[max_variable_size](../standard-library/max-variable-size-class.md) のいずれかにすることができます。

## <a name="remarks"></a>解説

Cache_freelist クラステンプレートは、サイズ *Sz*のメモリブロックの空きリストを保持します。 フリーリストがいっぱいの場合は、 **operator delete** を使用してメモリブロックの割り当てを解除します。 フリーリストが空の場合は、 **operator new** を使用して新しいメモリブロックを割り当てます。 フリーリストの最大サイズは、 *max* パラメーターで渡されるクラス max クラスによって決まります。

各メモリブロックは、使用可能なメモリの *Sz* バイトと、 **operator new** および **operator delete** に必要なデータを保持します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[cache_freelist](#cache_freelist)|`cache_freelist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割当て](#allocate)|メモリのブロックを割り当てます。|
|[配置](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<allocators>

**名前空間:** stdext

## <a name="cache_freelistallocate"></a><a name="allocate"></a> cache_freelist:: allocate

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

## <a name="cache_freelistcache_freelist"></a><a name="cache_freelist"></a> cache_freelist:: cache_freelist

`cache_freelist` 型のオブジェクトを構築します。

```cpp
cache_freelist();
```

### <a name="remarks"></a>解説

## <a name="cache_freelistdeallocate"></a><a name="deallocate"></a> cache_freelist::d eallocate

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
