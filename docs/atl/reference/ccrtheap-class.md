---
description: '詳細情報: CCRTHeap クラス'
title: CCRTHeap クラス
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: c256139f37a4b0caa0a60f1a87fd71b6a3a8de3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142013"
---
# <a name="ccrtheap-class"></a>CCRTHeap クラス

このクラスは、CRT ヒープ関数を使用して [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。

## <a name="syntax"></a>構文

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCRTHeap:: Allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[CCRTHeap:: Free](#free)|このメモリマネージャーによって割り当てられたメモリブロックを解放するには、このメソッドを呼び出します。|
|[CCRTHeap:: GetSize](#getsize)|このメモリマネージャーによって割り当てられたメモリブロックの割り当てサイズを取得するには、このメソッドを呼び出します。|
|[CCRTHeap:: 再割り当て](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>解説

`CCRTHeap` は、 [malloc](../../c-runtime-library/reference/malloc.md)、 [free](../../c-runtime-library/reference/free.md)、 [realloc](../../c-runtime-library/reference/realloc.md)、および [_msize](../../c-runtime-library/reference/msize.md)を含む CRT ヒープ関数を使用して、メモリ割り当て関数を実装します。

## <a name="example"></a>例

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>要件

**ヘッダー:** atlmem. h

## <a name="ccrtheapallocate"></a><a name="allocate"></a> CCRTHeap:: Allocate

メモリ ブロックを割り当てるには、このメソッドを呼び出します。

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

このメソッドによって割り当てられたメモリを解放するには、 [Ccrtheap:: free](#free) または [Ccrtheap:: 再割り当て](#reallocate) を呼び出します。

[Malloc](../../c-runtime-library/reference/malloc.md)を使用して実装されます。

## <a name="ccrtheapfree"></a><a name="free"></a> CCRTHeap:: Free

このメモリマネージャーによって割り当てられたメモリブロックを解放するには、このメソッドを呼び出します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も行いません。

### <a name="remarks"></a>解説

[Free](../../c-runtime-library/reference/free.md)を使用して実装されます。

## <a name="ccrtheapgetsize"></a><a name="getsize"></a> CCRTHeap:: GetSize

このメモリマネージャーによって割り当てられたメモリブロックの割り当てサイズを取得するには、このメソッドを呼び出します。

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="return-value"></a>戻り値

割り当てられたメモリブロックのサイズをバイト数で返します。

### <a name="remarks"></a>解説

[_Msize](../../c-runtime-library/reference/msize.md)を使用して実装されます。

## <a name="ccrtheapreallocate"></a><a name="reallocate"></a> CCRTHeap:: 再割り当て

このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

このメソッドによって割り当てられたメモリを解放するには、 [Ccrtheap:: free](#free) を呼び出します。 [Realloc](../../c-runtime-library/reference/realloc.md)を使用して実装されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComHeap クラス](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap クラス](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)<br/>
[IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)
