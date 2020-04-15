---
title: クラス
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
ms.openlocfilehash: caf5508079332689c2fff42f130951375dc35512
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327161"
---
# <a name="ccrtheap-class"></a>クラス

このクラスは、CRT ヒープ関数を使用して[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)を実装します。

## <a name="syntax"></a>構文

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[割り当て](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[CCRTヒープ::無料](#free)|このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。|
|[を返します。](#getsize)|このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得します。|
|[再割り当て](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>解説

`CCRTHeap`[malloc](../../c-runtime-library/reference/malloc.md)、 free 、 [realloc](../../c-runtime-library/reference/free.md)、 [_msize](../../c-runtime-library/reference/msize.md)などの[realloc](../../c-runtime-library/reference/realloc.md)CRT ヒープ関数を使用して、メモリ割り当て関数を実装します。

## <a name="example"></a>例

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem.h

## <a name="ccrtheapallocate"></a><a name="allocate"></a>割り当て

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

呼び出し[CCRTHeap::Free](#free)または[CCRTHeap::このメソッドによって割り当てられたメモリを解放するために再割り当て](#reallocate)します。

[malloc](../../c-runtime-library/reference/malloc.md)を使用して実装されます。

## <a name="ccrtheapfree"></a><a name="free"></a>CCRTヒープ::無料

このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も実行しません。

### <a name="remarks"></a>解説

[無料](../../c-runtime-library/reference/free.md)を使用して実装.

## <a name="ccrtheapgetsize"></a><a name="getsize"></a>を返します。

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

[_msize](../../c-runtime-library/reference/msize.md)を使用して実装されます。

## <a name="ccrtheapreallocate"></a><a name="reallocate"></a>再割り当て

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

[CCRTHeap::この](#free)メソッドによって割り当てられたメモリを解放するフリーを呼び出します。 [realloc](../../c-runtime-library/reference/realloc.md)を使用して実装されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/ccomheap-class.md)<br/>
[クラスを使用します。](../../atl/reference/cwin32heap-class.md)<br/>
[クラス](../../atl/reference/clocalheap-class.md)<br/>
[クラス](../../atl/reference/cglobalheap-class.md)<br/>
[イアトルメムグラムクラス](../../atl/reference/iatlmemmgr-class.md)
