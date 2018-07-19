---
title: CLocalHeap クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e0489d46ada0e68456f6ae16e7cd702c892a7b9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880116"
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
>  ローカル ヒープ関数では、他のメモリ管理関数よりも低速で、多くの機能を提供しません。 そのため、新しいアプリケーションを使用する必要があります、[ヒープ関数](http://msdn.microsoft.com/library/windows/desktop/aa366711)します。 これらで使用できる、 [CWin32Heap](../../atl/reference/cwin32heap-class.md)クラス。  
  
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
 *nBytes*  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す[clocalheap::free](#free)または[clocalheap::reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) LMEM_FIXED のフラグ パラメーターを使用します。  
  
##  <a name="free"></a>  Clocalheap::free  
 このメモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値を何も行われません。  
  
### <a name="remarks"></a>Remarks  
 使用して実装[LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730)します。  
  
##  <a name="getsize"></a>  CLocalHeap::GetSize  
 このメモリ マネージャーによって割り当てられたメモリ ブロックの割り当てサイズを取得するには、このメソッドを呼び出します。  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックのサイズをバイト単位で返します。  
  
### <a name="remarks"></a>Remarks  
 使用して実装[LocalSize](http://msdn.microsoft.com/library/windows/desktop/aa366745)します。  
  
##  <a name="reallocate"></a>  Clocalheap::reallocate  
 このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
 *nBytes*  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す[clocalheap::free](#free)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[LocalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)
