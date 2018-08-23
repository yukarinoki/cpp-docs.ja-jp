---
title: CWin32Heap クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWin32Heap
- ATLMEM/ATL::CWin32Heap
- ATLMEM/ATL::CWin32Heap::CWin32Heap
- ATLMEM/ATL::CWin32Heap::Allocate
- ATLMEM/ATL::CWin32Heap::Attach
- ATLMEM/ATL::CWin32Heap::Detach
- ATLMEM/ATL::CWin32Heap::Free
- ATLMEM/ATL::CWin32Heap::GetSize
- ATLMEM/ATL::CWin32Heap::Reallocate
- ATLMEM/ATL::CWin32Heap::m_bOwnHeap
- ATLMEM/ATL::CWin32Heap::m_hHeap
dev_langs:
- C++
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cc725907c93955777cd09b5745651855892e4cd
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "42573251"
---
# <a name="cwin32heap-class"></a>CWin32Heap クラス
このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 ヒープ割り当て関数を使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CWin32Heap : public IAtlMemMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWin32Heap::CWin32Heap](#cwin32heap)|コンストラクターです。|  
|[CWin32Heap:: ~ CWin32Heap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Cwin32heap::allocate](#allocate)|ヒープ オブジェクトからメモリ ブロックを割り当てます。|  
|[Cwin32heap::attach](#attach)|既存のヒープには、ヒープのオブジェクトをアタッチします。|  
|[CWin32Heap::Detach](#detach)|既存のヒープからヒープ オブジェクトをデタッチします。|  
|[Cwin32heap::free](#free)|以前は、ヒープから割り当てられたメモリを解放します。|  
|[CWin32Heap::GetSize](#getsize)|ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。|  
|[Cwin32heap::reallocate](#reallocate)|ヒープ オブジェクトからメモリ ブロックを再割り当てします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|ヒープ ハンドルの現在の所有権を決定するために使用するフラグ。|  
|[CWin32Heap::m_hHeap](#m_hheap)|ヒープのオブジェクトへのハンドルします。|  
  
## <a name="remarks"></a>Remarks  
 `CWin32Heap` 含む、Win32 ヒープ割り当て関数を使用してメモリの割り当て方法を実装する[HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597)と[選択肢](http://msdn.microsoft.com/library/windows/desktop/aa366701)します。 その他のヒープ クラスとは異なり`CWin32Heap`メモリを割り当てる前に指定する有効なヒープ ハンドルが必要です: プロセス ヒープを使用するその他のクラスの既定です。 コンス トラクターまたはハンドルを指定することができます、 [cwin32heap::attach](#attach)メソッド。 参照してください、 [CWin32Heap::CWin32Heap](#cwin32heap)メソッドの詳細。  
  
## <a name="example"></a>例  
 例をご覧ください[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlmem.h  
  
##  <a name="allocate"></a>  Cwin32heap::allocate  
 ヒープ オブジェクトからメモリ ブロックを割り当てます。  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nBytes*  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す[cwin32heap::free](#free)または[cwin32heap::reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597)します。  
  
##  <a name="attach"></a>  Cwin32heap::attach  
 既存のヒープには、ヒープのオブジェクトをアタッチします。  
  
```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *hHeap*  
 既存のヒープ ハンドル。  
  
 *bTakeOwnership*  
 フラグのどうかを示す、`CWin32Heap`オブジェクトが、ヒープのリソースに対する所有権を取得します。  
  
### <a name="remarks"></a>Remarks  
 場合*bTakeOwnership* true で、`CWin32Heap`オブジェクトがヒープ ハンドルを削除する責任を負います。  
  
##  <a name="cwin32heap"></a>  CWin32Heap::CWin32Heap  
 コンストラクターです。  
  
```
CWin32Heap() throw();
CWin32Heap( HANDLE  hHeap) throw();
CWin32Heap(
    DWORD  dwFlags,
    size_t nInitialSize,
    size_t nMaxSize = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *hHeap*  
 既存のヒープ オブジェクト。  
  
 *dwFlags*  
 ヒープの作成に使用されるフラグ。  
  
 *nInitialSize*  
 ヒープの初期サイズ。  
  
 *nMaxSize*  
 ヒープの最大サイズ。  
  
### <a name="remarks"></a>Remarks  
 メモリを割り当てる前に、`CWin32Heap` オブジェクトに有効なヒープ ハンドルを提供する必要があります。 これを実現する最も簡単な方法は、プロセス ヒープを使用することです。  
  
 [!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]  
  
 また、コンストラクターに既存のヒープ ハンドルを提供できますが、その場合には新しいオブジェクトはヒープの所有権を引き継ぎません。 `CWin32Heap` オブジェクトが削除されても、元のヒープ ハンドルは依然として有効です。  
  
 既存のヒープを新しいに添付することもできます。 オブジェクトを使用して[cwin32heap::attach](#attach)します。  
  
 すべての処理がシングル スレッドから行われるときに、ヒープが必要な場合、最適な方法は次のようにオブジェクトを作成することです。  
  
 [!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]  
  
 HEAP_NO_SERIALIZE パラメーターは、ヒープ関数の割り当てし、パフォーマンスの向上が使用して、メモリを解放するときに相互排他を使用しないを指定します。  
  
 第 3 のパラメーターの既定値は 0 であり、この場合には必要に応じてヒープを拡大できます。 参照してください[HeapCreate](/windows/desktop/api/heapapi/nf-heapapi-heapcreate)メモリ サイズおよびフラグの詳細についてはします。  
  
##  <a name="dtor"></a>  CWin32Heap:: ~ CWin32Heap  
 デストラクターです。  
  
```
~CWin32Heap() throw();
```  
  
### <a name="remarks"></a>Remarks  
 場合、ヒープのハンドルを破棄、`CWin32Heap`オブジェクトが、ヒープの所有権を保持します。  
  
##  <a name="detach"></a>  CWin32Heap::Detach  
 既存のヒープからヒープ オブジェクトをデタッチします。  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが関連付けられていたをヒープにハンドルを返します。  
  
##  <a name="free"></a>  Cwin32heap::free  
 以前は別にヒープから割り当てられたメモリを解放[cwin32heap::allocate](#allocate)または[cwin32heap::reallocate](#reallocate)します。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 解放するメモリ ブロックへのポインター。 NULL は有効な値を何も行われません。  
  
##  <a name="getsize"></a>  CWin32Heap::GetSize  
 ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 サイズを取得するメモリ ブロックへのポインター。 これは、によって返されるポインター [cwin32heap::allocate](#allocate)または[cwin32heap::reallocate](#reallocate)します。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックのバイト単位のサイズを返します。  
  
##  <a name="m_bownheap"></a>  CWin32Heap::m_bOwnHeap  
 格納されているヒープ ハンドルの現在の所有権を決定するために使用フラグ[m_hHeap](#m_hheap)します。  
  
```
bool m_bOwnHeap;
```  
  
##  <a name="m_hheap"></a>  CWin32Heap::m_hHeap  
 ヒープのオブジェクトへのハンドルします。  
  
```
HANDLE m_hHeap;
```  
  
### <a name="remarks"></a>Remarks  
 ヒープ オブジェクトを識別するハンドルを格納するために使用する変数です。  
  
##  <a name="reallocate"></a>  Cwin32heap::reallocate  
 ヒープ オブジェクトからメモリ ブロックを再割り当てします。  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *p*  
 再割り当てするメモリ ブロックへのポインター。  
  
 *nBytes*  
 割り当てられるブロックの新しいサイズ (バイト単位)。 ブロックは大きくすることも小さくすることもできます。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
### <a name="remarks"></a>Remarks  
 場合*p*が null の場合、メモリ ブロックがまだ割り当てられていないことと見なされますと[cwin32heap::allocate](#allocate)の引数を指定して呼び出されます*nBytes*します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)
