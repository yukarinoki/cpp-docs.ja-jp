---
title: クラス
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
ms.openlocfilehash: d596fd51c1bf33f606c1f14c9e8dbd2f1926c7f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326938"
---
# <a name="cglobalheap-class"></a>クラス

このクラスは、Win32 グローバル ヒープ関数を使用して[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)を実装します。

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
|[割り当て](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[Cグローバルヒープ::無料](#free)|このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。|
|[を指定します。](#getsize)|このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得します。|
|[再割り当て](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>解説

`CGlobalHeap`は、Win32 グローバル ヒープ関数を使用してメモリ割り当て関数を実装します。

> [!NOTE]
> グローバル ヒープ関数は、他のメモリ管理機能よりも低速で、多くの機能を提供しません。 したがって、新しいアプリケーションでは[ヒープ関数](/windows/win32/Memory/heap-functions)を使用する必要があります。 これらは[CWin32Heap](../../atl/reference/cwin32heap-class.md)クラスで使用できます。 グローバル関数は、DDE およびクリップボード関数で引き続き使用されます。

## <a name="example"></a>例

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem.h

## <a name="cglobalheapallocate"></a><a name="allocate"></a>割り当て

メモリ ブロックを割り当てるには、このメソッドを呼び出します。

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

呼び出します[CGlobalHeap::Free](#free)または[CGlobalHeap:このメソッドによって割り当てられたメモリを解放するために再割り当て](#reallocate)します。

GMEM_FIXEDのフラグパラメータを持つ[GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc)を使用して実装されます。

## <a name="cglobalheapfree"></a><a name="free"></a>Cグローバルヒープ::無料

このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も実行しません。

### <a name="remarks"></a>解説

[グローバルフリー](/windows/win32/api/winbase/nf-winbase-globalfree)を使用して実装.

## <a name="cglobalheapgetsize"></a><a name="getsize"></a>を指定します。

このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得します。

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックのサイズをバイト単位で返します。

### <a name="remarks"></a>解説

[グローバル サイズ](/windows/win32/api/winbase/nf-winbase-globalsize)を使用して実装します。

## <a name="cglobalheapreallocate"></a><a name="reallocate"></a>再割り当て

このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

*Nbytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

呼び出し[CGlobalヒープ::この](#free)メソッドによって割り当てられたメモリを解放するフリー。

[グローバル再アロック](/windows/win32/api/winbase/nf-winbase-globalrealloc)を使用して実装されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/ccomheap-class.md)<br/>
[クラスを使用します。](../../atl/reference/cwin32heap-class.md)<br/>
[クラス](../../atl/reference/clocalheap-class.md)<br/>
[クラス](../../atl/reference/ccrtheap-class.md)<br/>
[イアトルメムグラムクラス](../../atl/reference/iatlmemmgr-class.md)
