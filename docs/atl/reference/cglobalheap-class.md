---
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
ms.openlocfilehash: cba15421fd0329df7a66a35979ed54b863b7cca0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278302"
---
# <a name="cglobalheap-class"></a>CGlobalHeap クラス

このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)グローバル ヒープの Win32 関数を使用します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CGlobalHeap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CGlobalHeap::Allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[CGlobalHeap::Free](#free)|このメモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。|
|[CGlobalHeap::GetSize](#getsize)|このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得するには、このメソッドを呼び出します。|
|[CGlobalHeap::Reallocate](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>Remarks

`CGlobalHeap` グローバルのヒープの Win32 関数を使用して、メモリ割り当て関数を実装します。

> [!NOTE]
>  グローバルのヒープ関数では、他のメモリ管理関数よりも低速で、多くの機能を提供しません。 そのため、新しいアプリケーションを使用する必要があります、[ヒープ関数](/windows/desktop/Memory/heap-functions)します。 これらで使用できる、 [CWin32Heap](../../atl/reference/cwin32heap-class.md)クラス。 グローバル関数は、DDE およびクリップボード機能によって引き続き使用されます。

## <a name="example"></a>例

例をご覧ください[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem.h

##  <a name="allocate"></a>  CGlobalHeap::Allocate

メモリ ブロックを割り当てるには、このメソッドを呼び出します。

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>Remarks

呼び出す[cglobalheap::free](#free)または[cglobalheap::reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。

使用して実装[GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) GMEM_FIXED のフラグ パラメーターを使用します。

##  <a name="free"></a>  CGlobalHeap::Free

このメモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値を何も行われません。

### <a name="remarks"></a>Remarks

使用して実装[GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree)します。

##  <a name="getsize"></a>  CGlobalHeap::GetSize

このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得するには、このメソッドを呼び出します。

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックのサイズをバイト単位で返します。

### <a name="remarks"></a>Remarks

使用して実装[GlobalSize](/windows/desktop/api/winbase/nf-winbase-globalsize)します。

##  <a name="reallocate"></a>  CGlobalHeap::Reallocate

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

### <a name="remarks"></a>Remarks

呼び出す[cglobalheap::free](#free)このメソッドによって割り当てられたメモリを解放します。

使用して実装[GlobalReAlloc](/windows/desktop/api/winbase/nf-winbase-globalrealloc)します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComHeap クラス](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap クラス](../../atl/reference/clocalheap-class.md)<br/>
[CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)
