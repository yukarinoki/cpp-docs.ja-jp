---
title: rts_alloc クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4bff519ea12646e94e92cde219fa38e4009a767
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956457"
---
# <a name="rtsalloc-class"></a>rts_alloc クラス

rts_alloc テンプレート クラスは、キャッシュ インスタンスの配列を保持し、コンパイル時ではなく、実行時に割り当てと割り当て解除に使用するインスタンスを判別する[フィルター](../standard-library/allocators-header.md)を記述します。

## <a name="syntax"></a>構文

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*キャッシュ*|配列に含まれているキャッシュ インスタンスの型。 これは、[cache_chunklist クラス](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|

## <a name="remarks"></a>Remarks

このテンプレート クラスは、複数のブロック アロケーター インスタンスを保持し、コンパイル時ではなく、実行時に割り当てと割り当て解除に使用するインスタンスを判別します。 再バインドをコンパイルできないコンパイラと一緒に使用します。

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[allocate](#allocate)|メモリのブロックを割り当てます。|
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<allocators>

**名前空間:** stdext

## <a name="allocate"></a>  rts_alloc::allocate

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

メンバー関数を返します`caches[_IDX].allocate(count)`ここで、インデックス`_IDX`は要求されたブロックのサイズによって決まります*カウント*、または、*数*は返しますが大きすぎて、`operator new(count)`します。 キャッシュ オブジェクトを表す `cache`。

## <a name="deallocate"></a>  rts_alloc::deallocate

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

メンバー関数の呼び出し`caches[_IDX].deallocate(ptr, count)`ここで、インデックス`_IDX`は要求されたブロックのサイズによって決まります*カウント*、または、*数*は返しますが大きすぎて、`operator delete(ptr)`します。

## <a name="equals"></a>  rts_alloc::equals

2 つのキャッシュが等しいかどうかを比較します。

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Cache*|フィルターに関連付けられているキャッシュ オブジェクト。|
|*_Other*|等しいかどうかを比較するキャッシュ オブジェクト。|

### <a name="remarks"></a>Remarks

**true**場合の結果`caches[0].equals(other.caches[0])`、それ以外の**false**します。 `caches` はキャッシュ オブジェクトの配列を表します。

## <a name="see-also"></a>関連項目

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)<br/>
[\<allocators>](../standard-library/allocators-header.md)<br/>
