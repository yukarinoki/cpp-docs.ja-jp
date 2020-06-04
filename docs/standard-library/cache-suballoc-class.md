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
ms.openlocfilehash: 55860a65fc77f834ed699f3a5114768b7efdde6f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366733"
---
# <a name="cache_suballoc-class"></a>cache_suballoc クラス

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

## <a name="remarks"></a>解説

cache_suballoc クラス テンプレートは、割り当て解除されたメモリ ブロックを、 を`freelist<sizeof(Type), max_unbounded>`使用して非制限長の空きリストに格納し、空のリストが空の場合に **、演算子 new**で割り当てられた大きなチャンクからメモリ ブロックを suballocate します。

各チャンクは`Sz * Nelts`、使用できるメモリのバイトと **、演算子 new**および operator **delete**が必要とするデータを保持します。 割り当てたチャンクが解放されることはありません。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[cache_suballoc](#cache_suballoc)|`cache_suballoc` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割り当てる](#allocate)|メモリのブロックを割り当てます。|
|[解放](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="cache_suballocallocate"></a><a name="allocate"></a>cache_suballoc:割り当て

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

## <a name="cache_suballoccache_suballoc"></a><a name="cache_suballoc"></a>cache_suballoc::cache_suballoc

`cache_suballoc` 型のオブジェクトを構築します。

```cpp
cache_suballoc();
```

### <a name="remarks"></a>解説

## <a name="cache_suballocdeallocate"></a><a name="deallocate"></a>cache_suballoc::d割り当て

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
