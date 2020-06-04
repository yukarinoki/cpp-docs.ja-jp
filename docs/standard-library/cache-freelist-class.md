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
ms.openlocfilehash: d757909d3e54fed35bf42b943b9f9740dffee115
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366746"
---
# <a name="cache_freelist-class"></a>cache_freelist クラス

1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。

## <a name="syntax"></a>構文

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Sz*|割り当てられる配列内の要素の数。|
|*最大*|フリー リストの最大サイズを表す max クラスです。 [max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md)、[max_variable_size](../standard-library/max-variable-size-class.md) のいずれかにすることができます。|

## <a name="remarks"></a>解説

cache_freelistクラス テンプレートは、サイズ*Sz*のメモリ ブロックの空きリストを保持します。 空きリストがいっぱいになると、オペレーター **delete**を使用してメモリー・ブロックの割り振り解除を行います。 空きリストが空の場合、新しいメモリ ブロックを割り当てる**ため、演算子 new**を使用します。 フリー リストの最大サイズは *、Max*パラメーターで渡されるクラスの最大クラスによって決まります。

各メモリブロックは、使用できるメモリの*Sz*バイトを保持し、**オペレータnew**と**オペレータの削除**が必要とするデータを保持します。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[cache_freelist](#cache_freelist)|`cache_freelist` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割り当てる](#allocate)|メモリのブロックを割り当てます。|
|[解放](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="cache_freelistallocate"></a><a name="allocate"></a>cache_freelist::割り当て

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

## <a name="cache_freelistcache_freelist"></a><a name="cache_freelist"></a>cache_freelist::cache_freelist

`cache_freelist` 型のオブジェクトを構築します。

```cpp
cache_freelist();
```

### <a name="remarks"></a>解説

## <a name="cache_freelistdeallocate"></a><a name="deallocate"></a>cache_freelist::d割り当て

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
