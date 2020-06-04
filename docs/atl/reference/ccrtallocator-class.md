---
title: CCRTアロケータークラス
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
ms.openlocfilehash: 2f6bae3818fa0f1639e0e3cee4e09121580da768
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327177"
---
# <a name="ccrtallocator-class"></a>CCRTアロケータークラス

このクラスは、CRT メモリ ルーチンを使用してメモリを管理するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class ATL::CCRTAllocator
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCRTAllocator::割り当て](#allocate)|(静的)メモリを割り当てるには、このメソッドを呼び出します。|
|[CCRTAllocator::無料](#free)|(静的)メモリを解放するには、このメソッドを呼び出します。|
|[CCRTAllocator::再割り当て](#reallocate)|(静的)メモリを再割り当てします。|

## <a name="remarks"></a>解説

このクラスは、CRT メモリ割り当てルーチンを提供するために[CHeapPtr](../../atl/reference/cheapptr-class.md)によって使用されます。 対応するクラス[である CComAllocator](../../atl/reference/ccomallocator-class.md)は、COM ルーチンを使用して同じメソッドを提供します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a>CCRTAllocator::割り当て

メモリを割り当てる場合は、この静的関数を呼び出します。

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
割り当てるバイト数。

### <a name="return-value"></a>戻り値

メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。

### <a name="remarks"></a>解説

メモリを割り当てます。 詳細については[、malloc](../../c-runtime-library/reference/malloc.md)を参照してください。

## <a name="ccrtallocatorfree"></a><a name="free"></a>CCRTAllocator::無料

この静的関数を呼び出して、メモリを解放します。

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
割り当てられたメモリへのポインター。

### <a name="remarks"></a>解説

割り当てられたメモリを解放します。 詳細については[、無料](../../c-runtime-library/reference/free.md)で見てください。

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a>CCRTAllocator::再割り当て

メモリを再割り当てする場合は、この静的関数を呼び出します。

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
割り当てられたメモリへのポインター。

*Nbytes*<br/>
再割り当てするバイト数。

### <a name="return-value"></a>戻り値

メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。

### <a name="remarks"></a>解説

割り当てられたメモリの量を変更します。 詳細については[、realloc](../../c-runtime-library/reference/realloc.md)を参照してください。

## <a name="see-also"></a>関連項目

[Cヒーププタークラス](../../atl/reference/cheapptr-class.md)<br/>
[コマッロロケータクラス](../../atl/reference/ccomallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
