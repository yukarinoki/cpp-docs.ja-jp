---
title: CCRTAllocator クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfd7d5a040da4d27838e8045b6c4c64950e515dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054845"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator クラス

このクラスは、CRT メモリ ルーチンを使用してメモリを管理するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class ATL::CCRTAllocator
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Ccrtallocator::allocate](#allocate)|(静的)メモリを割り当てるには、このメソッドを呼び出します。|
|[Ccrtallocator::free](#free)|(静的)メモリを解放するには、このメソッドを呼び出します。|
|[Ccrtallocator::reallocate](#reallocate)|(静的)メモリを再割り当てするには、このメソッドを呼び出します。|

## <a name="remarks"></a>Remarks

このクラスによって使用されます[CHeapPtr](../../atl/reference/cheapptr-class.md) CRT メモリ割り当てルーチンを提供します。 対応するクラス、 [CComAllocator](../../atl/reference/ccomallocator-class.md)COM のルーチンを使用する同じメソッドを提供します。

## <a name="requirements"></a>要件

**ヘッダー:** atlcore.h

##  <a name="allocate"></a>  Ccrtallocator::allocate

メモリを割り当てる場合は、この静的関数を呼び出します。

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
割り当てるバイト数。

### <a name="return-value"></a>戻り値

メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。

### <a name="remarks"></a>Remarks

メモリを割り当てます。 参照してください[malloc](../../c-runtime-library/reference/malloc.md)の詳細。

##  <a name="free"></a>  Ccrtallocator::free

メモリを解放する、この静的関数を呼び出します。

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
割り当てられたメモリへのポインター。

### <a name="remarks"></a>Remarks

割り当てられたメモリを解放します。 参照してください[無料](../../c-runtime-library/reference/free.md)の詳細。

##  <a name="reallocate"></a>  Ccrtallocator::reallocate

メモリを再割り当てする場合は、この静的関数を呼び出します。

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
割り当てられたメモリへのポインター。

*nBytes*<br/>
再割り当てするバイト数。

### <a name="return-value"></a>戻り値

メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。

### <a name="remarks"></a>Remarks

割り当てられたメモリの量を変更します。 参照してください[realloc](../../c-runtime-library/reference/realloc.md)の詳細。

## <a name="see-also"></a>関連項目

[CHeapPtr クラス](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator クラス](../../atl/reference/ccomallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
