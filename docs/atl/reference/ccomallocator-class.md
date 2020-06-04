---
title: コマッロロケータクラス
ms.date: 11/04/2016
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
ms.openlocfilehash: 165cdb8b0b16a4872214f4556c26ee141e6a4d89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321139"
---
# <a name="ccomallocator-class"></a>コマッロロケータクラス

このクラスは、COM メモリ ルーチンを使用してメモリを管理するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComAllocator
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コマッロケータ::割り当て](#allocate)|メモリを割り当てるには、この静的メソッドを呼び出します。|
|[コマッロケータ::無料](#free)|割り当てられたメモリを解放するには、この静的メソッドを呼び出します。|
|[コマッロケータ::再割り当て](#reallocate)|メモリを再割り当てするには、この静的メソッドを呼び出します。|

## <a name="remarks"></a>解説

このクラスは、COM メモリ割り当てルーチンを提供するために[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)によって使用されます。 対応するクラスの[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)は、CRT ルーチンを使用して同じメソッドを提供します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomallocatorallocate"></a><a name="allocate"></a>コマッロケータ::割り当て

メモリを割り当てる場合は、この静的関数を呼び出します。

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
割り当てるバイト数。

### <a name="return-value"></a>戻り値

メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。

### <a name="remarks"></a>解説

メモリを割り当てます。 詳細については[、CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)を参照してください。

## <a name="ccomallocatorfree"></a><a name="free"></a>コマッロケータ::無料

割り当てられたメモリを解放するには、この静的関数を呼び出します。

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
割り当てられたメモリへのポインター。

### <a name="remarks"></a>解説

割り当てられたメモリを解放します。 詳細については[、CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)を参照してください。

## <a name="ccomallocatorreallocate"></a><a name="reallocate"></a>コマッロケータ::再割り当て

メモリを再割り当てする場合は、この静的関数を呼び出します。

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
割り当てられたメモリへのポインター。

*Nbytes*<br/>
再割り当てするバイト数。

### <a name="return-value"></a>戻り値

割り当てられた領域への void ポインタを返します。

### <a name="remarks"></a>解説

割り当てられたメモリの量を変更します。 詳細については[、コタスクメムリアルロック](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)を参照してください。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTアロケータークラス](../../atl/reference/ccrtallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
