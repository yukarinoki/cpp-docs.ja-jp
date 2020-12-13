---
description: '詳細情報: CGlobalHeap クラス'
title: CGlobalHeap クラス
ms.date: 11/04/2016
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
ms.openlocfilehash: 349dd2155bdc68024171c07e48c648bae2b6aa7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141688"
---
# <a name="cglobalheap-class"></a>CGlobalHeap クラス

このクラスは、Win32 グローバルヒープ関数を使用して [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CGlobalHeap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CGlobalHeap:: Allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[CGlobalHeap:: Free](#free)|このメモリマネージャーによって割り当てられたメモリブロックを解放するには、このメソッドを呼び出します。|
|[CGlobalHeap:: GetSize](#getsize)|このメモリマネージャーによって割り当てられたメモリブロックの割り当てサイズを取得するには、このメソッドを呼び出します。|
|[CGlobalHeap:: 再割り当て](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>解説

`CGlobalHeap` Win32 グローバルヒープ関数を使用して、メモリ割り当て関数を実装します。

> [!NOTE]
> グローバルヒープ関数は、他のメモリ管理関数よりも低速であり、多くの機能を提供するわけではありません。 そのため、新しいアプリケーションでは、 [ヒープ関数](/windows/win32/Memory/heap-functions)を使用する必要があります。 これらは、 [CWin32Heap](../../atl/reference/cwin32heap-class.md) クラスで使用できます。 グローバル関数は、DDE およびクリップボード関数によって引き続き使用されます。

## <a name="example"></a>例

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>要件

**ヘッダー:** atlmem. h

## <a name="cglobalheapallocate"></a><a name="allocate"></a> CGlobalHeap:: Allocate

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

このメソッドによって割り当てられたメモリを解放するには、 [Cglobalheap:: Free](#free) または [cglobalheap:: 再割り当て](#reallocate) を呼び出します。

GMEM_FIXED のフラグパラメーターを持つ [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) を使用して実装されます。

## <a name="cglobalheapfree"></a><a name="free"></a> CGlobalHeap:: Free

このメモリマネージャーによって割り当てられたメモリブロックを解放するには、このメソッドを呼び出します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も行いません。

### <a name="remarks"></a>解説

[GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)を使用して実装されます。

## <a name="cglobalheapgetsize"></a><a name="getsize"></a> CGlobalHeap:: GetSize

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

[Globalsize](/windows/win32/api/winbase/nf-winbase-globalsize)を使用して実装されます。

## <a name="cglobalheapreallocate"></a><a name="reallocate"></a> CGlobalHeap:: 再割り当て

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

このメソッドによって割り当てられたメモリを解放するには、 [Cglobalheap:: free](#free) を呼び出します。

[Globalrealloc](/windows/win32/api/winbase/nf-winbase-globalrealloc)を使用して実装されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComHeap クラス](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap クラス](../../atl/reference/clocalheap-class.md)<br/>
[CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)
