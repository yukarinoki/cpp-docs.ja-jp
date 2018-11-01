---
title: CLocalHeap クラス
ms.date: 11/04/2016
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
ms.openlocfilehash: 7f4fa6b6035b9f0dda35a8e989192505ccf126d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515467"
---
# <a name="clocalheap-class"></a>CLocalHeap クラス

このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)ローカル ヒープの Win32 関数を使用します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Clocalheap::allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[Clocalheap::free](#free)|このメモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。|
|[CLocalHeap::GetSize](#getsize)|このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得するには、このメソッドを呼び出します。|
|[Clocalheap::reallocate](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>Remarks

`CLocalHeap` ローカル ヒープの Win32 関数を使用して、メモリ割り当て関数を実装します。

> [!NOTE]
>  ローカル ヒープ関数では、他のメモリ管理関数よりも低速で、多くの機能を提供しません。 そのため、新しいアプリケーションを使用する必要があります、[ヒープ関数](/windows/desktop/Memory/heap-functions)します。 これらで使用できる、 [CWin32Heap](../../atl/reference/cwin32heap-class.md)クラス。

## <a name="example"></a>例

例をご覧ください[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem.h

##  <a name="allocate"></a>  Clocalheap::allocate

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

呼び出す[clocalheap::free](#free)または[clocalheap::reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。

使用して実装[LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) LMEM_FIXED のフラグ パラメーターを使用します。

##  <a name="free"></a>  Clocalheap::free

このメモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値を何も行われません。

### <a name="remarks"></a>Remarks

使用して実装[LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree)します。

##  <a name="getsize"></a>  CLocalHeap::GetSize

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

使用して実装[LocalSize](/windows/desktop/api/winbase/nf-winbase-localsize)します。

##  <a name="reallocate"></a>  Clocalheap::reallocate

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

呼び出す[clocalheap::free](#free)このメソッドによって割り当てられたメモリを解放します。

使用して実装[LocalReAlloc](/windows/desktop/api/winbase/nf-winbase-localrealloc)します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CComHeap クラス](../../atl/reference/ccomheap-class.md)<br/>
[CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)<br/>
[CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)
