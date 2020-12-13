---
description: '詳細情報: CCRTAllocator クラス'
title: CCRTAllocator クラス
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: 378a1c27a6c2dde9fbcb24eb9b51b64c3af7e8aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142065"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator クラス

このクラスには、CRT メモリルーチンを使用してメモリを管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class ATL::CCRTAllocator
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCRTAllocator:: Allocate](#allocate)|雑音メモリを割り当てるには、このメソッドを呼び出します。|
|[CCRTAllocator:: Free](#free)|雑音メモリを解放するには、このメソッドを呼び出します。|
|[CCRTAllocator:: 再割り当て](#reallocate)|雑音メモリを再割り当てするには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

このクラスは、CRT メモリ割り当てルーチンを提供するために [CHeapPtr](../../atl/reference/cheapptr-class.md) によって使用されます。 対応するクラス [CComAllocator](../../atl/reference/ccomallocator-class.md)は、COM ルーチンを使用して同じメソッドを提供します。

## <a name="requirements"></a>要件

**ヘッダー:** atlcore .h

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a> CCRTAllocator:: Allocate

メモリを割り当てる場合は、この静的関数を呼び出します。

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
割り当てるバイト数。

### <a name="return-value"></a>戻り値

メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。

### <a name="remarks"></a>解説

メモリを割り当てます。 詳細については、「 [malloc](../../c-runtime-library/reference/malloc.md) 」を参照してください。

## <a name="ccrtallocatorfree"></a><a name="free"></a> CCRTAllocator:: Free

メモリを解放するには、この静的関数を呼び出します。

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
割り当てられたメモリへのポインター。

### <a name="remarks"></a>解説

割り当てられたメモリを解放します。 詳細については、「 [無料](../../c-runtime-library/reference/free.md) 」を参照してください。

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a> CCRTAllocator:: 再割り当て

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

### <a name="remarks"></a>解説

割り当てられたメモリの量を変更します。 詳細については、 [realloc](../../c-runtime-library/reference/realloc.md) を参照してください。

## <a name="see-also"></a>関連項目

[CHeapPtr クラス](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator クラス](../../atl/reference/ccomallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
