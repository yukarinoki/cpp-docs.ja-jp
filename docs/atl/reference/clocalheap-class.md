---
title: クラス
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
ms.openlocfilehash: 303e3b85ad11c309f862f59d6ec610701c4ef6db
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326760"
---
# <a name="clocalheap-class"></a>クラス

このクラスは、Win32 ローカル ヒープ関数を使用して[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)を実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[割り当て](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[Cローカルヒープ::無料](#free)|このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。|
|[を指定します。](#getsize)|このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得します。|
|[再割り当て](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>解説

`CLocalHeap`は、Win32 ローカル ヒープ関数を使用してメモリ割り当て関数を実装します。

> [!NOTE]
> ローカル ヒープ関数は、他のメモリ管理機能よりも低速で、多くの機能を提供しません。 したがって、新しいアプリケーションでは[ヒープ関数](/windows/win32/Memory/heap-functions)を使用する必要があります。 これらは[CWin32Heap](../../atl/reference/cwin32heap-class.md)クラスで使用できます。

## <a name="example"></a>例

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem.h

## <a name="clocalheapallocate"></a><a name="allocate"></a>割り当て

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

呼び出し[CLocalHeap::Free](#free)または[CLocalHeap:この](#reallocate)メソッドによって割り当てられたメモリを解放するために再割り当てします。

LMEM_FIXEDのフラグ パラメーターを持つ[LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc)を使用して実装されます。

## <a name="clocalheapfree"></a><a name="free"></a>Cローカルヒープ::無料

このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も実行しません。

### <a name="remarks"></a>解説

[LocalFree](/windows/win32/api/winbase/nf-winbase-localfree)を使用して実装されます。

## <a name="clocalheapgetsize"></a><a name="getsize"></a>を指定します。

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

[を](/windows/win32/api/winbase/nf-winbase-localsize)使用して実装します。

## <a name="clocalheapreallocate"></a><a name="reallocate"></a>再割り当て

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

呼び出し[CLocalHeap::この](#free)メソッドによって割り当てられたメモリを解放するフリー。

[を](/windows/win32/api/winbase/nf-winbase-localrealloc)使用して実装します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/ccomheap-class.md)<br/>
[クラスを使用します。](../../atl/reference/cwin32heap-class.md)<br/>
[クラス](../../atl/reference/cglobalheap-class.md)<br/>
[クラス](../../atl/reference/ccrtheap-class.md)<br/>
[イアトルメムグラムクラス](../../atl/reference/iatlmemmgr-class.md)
