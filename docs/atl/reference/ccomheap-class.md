---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
ms.openlocfilehash: a38d1147e718870c03af84ec1487e226805b956e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327821"
---
# <a name="ccomheap-class"></a>クラス

このクラスは、COM メモリ割り当て関数を使用して[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)を実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ココモヒープ::割り当て](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[ココムヒープ::無料](#free)|このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。|
|[次の値を指定します。](#getsize)|このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得します。|
|[CComヒープ::再割り当て](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|

## <a name="remarks"></a>解説

`CComHeap`[COM](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)割り当て関数を使用してメモリ割り当て関数を実装します[CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)[。](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc) [IMalloc::GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize) 割り振ることができるメモリの最大量は、INT_MAX (2147483647) バイトと等しくなります。

## <a name="example"></a>例

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>必要条件

**ヘッダー:** ATLComMem.h

## <a name="ccomheapallocate"></a><a name="allocate"></a>ココモヒープ::割り当て

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

呼び出し[CComHeap::Free](#free)または[CComHeap::この](#reallocate)メソッドによって割り当てられたメモリを解放するために再割り当てします。

[を](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)使用して実装されました。

## <a name="ccomheapfree"></a><a name="free"></a>ココムヒープ::無料

このメモリ マネージャによって割り当てられたメモリ ブロックを解放します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も実行しません。

### <a name="remarks"></a>解説

[を](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)使用して実装されました。

## <a name="ccomheapgetsize"></a><a name="getsize"></a>次の値を指定します。

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

[IMalloc::GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)を使用して実装されています。

## <a name="ccomheapreallocate"></a><a name="reallocate"></a>CComヒープ::再割り当て

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

[CComHeap を呼び出します::この](#free)メソッドによって割り当てられたメモリを解放するフリー。

を使用して実装[します](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)。

## <a name="see-also"></a>関連項目

[動的コンシューマサンプル](../../overview/visual-cpp-samples.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラスを使用します。](../../atl/reference/cwin32heap-class.md)<br/>
[クラス](../../atl/reference/clocalheap-class.md)<br/>
[クラス](../../atl/reference/cglobalheap-class.md)<br/>
[クラス](../../atl/reference/ccrtheap-class.md)<br/>
[イアトルメムグラムクラス](../../atl/reference/iatlmemmgr-class.md)
