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
ms.openlocfilehash: 94ae4dfc8f5f9073c0a39f315adfbed3e5c14daf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380172"
---
# <a name="cachechunklist-class"></a>cache_chunklist クラス

1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*sz*|割り当てられる配列内の要素の数。|

## <a name="remarks"></a>Remarks

このテンプレート クラスを使用して**演算子 new**を生のメモリのチャンクを割り当てるには、記憶域を割り当てるために必要なときに、メモリ ブロックのブロックないときは、各チャンクの独立したフリー リストの割り当てが解除されたメモリ ブロックを格納し、を使用**delete 演算子**はそのメモリ ブロックの使用時に、チャンクの割り当てを解除します。

各メモリ ブロックを保持*Sz*バイトの使用可能なメモリおよびが属しているチャンクへのポインター。 各チャンクを保持`Nelts`メモリ ブロック、3 つのポインター、int、およびデータを**演算子 new**と**delete 演算子**が必要です。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocate](#allocate)|メモリのブロックを割り当てます。|
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="allocate"></a>  cache_chunklist::allocate

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

## <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist

`cache_chunklist` 型のオブジェクトを構築します。

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Remarks

## <a name="deallocate"></a>  cache_chunklist::deallocate

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

[\<allocators>](../standard-library/allocators-header.md)<br/>
