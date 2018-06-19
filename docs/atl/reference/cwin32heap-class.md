---
title: CWin32Heap クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 9b26d979ccb99d3d99bc91af03c4836603d31c01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363937"
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
|[Cwin32heap::attach](#attach)|既存のヒープにヒープのオブジェクトをアタッチします。|  
|[CWin32Heap::Detach](#detach)|既存のヒープからヒープのオブジェクトをデタッチします。|  
|[Cwin32heap::free](#free)|ヒープから割り当てられていたメモリを解放します。|  
|[CWin32Heap::GetSize](#getsize)|ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。|  
|[Cwin32heap::reallocate](#reallocate)|ヒープ オブジェクトからメモリ ブロックを再割り当てします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|ヒープのハンドルの現在の所有権を決定するために使用するフラグ。|  
|[CWin32Heap::m_hHeap](#m_hheap)|ヒープ オブジェクトへのハンドルします。|  
  
## <a name="remarks"></a>コメント  
 `CWin32Heap` など、Win32 ヒープ割り当て関数を使用してメモリ割り当てメソッドを実装する[HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597)と[HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701)です。 その他のヒープ クラスとは異なり`CWin32Heap`メモリを割り当てる前に指定する有効なヒープ ハンドルが必要です: プロセス ヒープを使用するその他のクラスの既定です。 コンス トラクターまたは、ハンドルを指定することができます、 [cwin32heap::attach](#attach)メソッドです。 参照してください、 [CWin32Heap::CWin32Heap](#cwin32heap)詳細についてはメソッドです。  
  
## <a name="example"></a>例  
 例を参照して[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)です。  
  
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
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[cwin32heap::free](#free)または[cwin32heap::reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597)です。  
  
##  <a name="attach"></a>  Cwin32heap::attach  
 既存のヒープにヒープのオブジェクトをアタッチします。  
  
```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hHeap`  
 既存のヒープのハンドル。  
  
 `bTakeOwnership`  
 フラグを示す場合は、`CWin32Heap`オブジェクトが、ヒープのリソースに対する所有権を取得します。  
  
### <a name="remarks"></a>コメント  
 場合`bTakeOwnership`true で、`CWin32Heap`オブジェクトがヒープのハンドルの削除を担当します。  
  
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
 `hHeap`  
 既存のヒープ オブジェクト。  
  
 `dwFlags`  
 ヒープの作成に使用されるフラグ。  
  
 *nInitialSize*  
 ヒープの初期サイズ。  
  
 `nMaxSize`  
 ヒープの最大サイズ。  
  
### <a name="remarks"></a>コメント  
 メモリを割り当てる前に、`CWin32Heap` オブジェクトに有効なヒープ ハンドルを提供する必要があります。 これを実現する最も簡単な方法は、プロセス ヒープを使用することです。  
  
 [!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]  
  
 また、コンストラクターに既存のヒープ ハンドルを提供できますが、その場合には新しいオブジェクトはヒープの所有権を引き継ぎません。 `CWin32Heap` オブジェクトが削除されても、元のヒープ ハンドルは依然として有効です。  
  
 既存のヒープを新しいに添付することもできます。 オブジェクトを使用して[cwin32heap::attach](#attach)です。  
  
 すべての処理がシングル スレッドから行われるときに、ヒープが必要な場合、最適な方法は次のようにオブジェクトを作成することです。  
  
 [!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]  
  
 パラメーター **HEAP_NO_SERIALIZE**ヒープ関数の割り当てし、パフォーマンスに応じて増やすことで、メモリを解放するときに相互排他を使用しないされますを指定します。  
  
 第 3 のパラメーターの既定値は 0 であり、この場合には必要に応じてヒープを拡大できます。 参照してください[HeapCreate](http://msdn.microsoft.com/library/windows/desktop/aa366599\(v=vs.85\).aspx)については、メモリのサイズとフラグです。  
  
##  <a name="dtor"></a>  CWin32Heap:: ~ CWin32Heap  
 デストラクターです。  
  
```
~CWin32Heap() throw();
```  
  
### <a name="remarks"></a>コメント  
 場合、ヒープのハンドルを破棄、`CWin32Heap`オブジェクトが、ヒープの所有権を保持します。  
  
##  <a name="detach"></a>  CWin32Heap::Detach  
 既存のヒープからヒープのオブジェクトをデタッチします。  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトをアタッチすると以前のヒープへのハンドルを返します。  
  
##  <a name="free"></a>  Cwin32heap::free  
 によって、ヒープから割り当てられていたメモリを解放[cwin32heap::allocate](#allocate)または[cwin32heap::reallocate](#reallocate)です。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 解放するメモリ ブロックへのポインター。 NULL は有効な値であり、何も行われません。  
  
##  <a name="getsize"></a>  CWin32Heap::GetSize  
 ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 メモリ ブロックのサイズを取得するへのポインター。 これは、によって返されるポインター [cwin32heap::allocate](#allocate)または[cwin32heap::reallocate](#reallocate)です。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックのバイト単位のサイズを返します。  
  
##  <a name="m_bownheap"></a>  CWin32Heap::m_bOwnHeap  
 格納されているヒープ ハンドルの現在の所有権を決定するために使用フラグ[m_hHeap](#m_hheap)です。  
  
```
bool m_bOwnHeap;
```  
  
##  <a name="m_hheap"></a>  CWin32Heap::m_hHeap  
 ヒープ オブジェクトへのハンドルします。  
  
```
HANDLE m_hHeap;
```  
  
### <a name="remarks"></a>コメント  
 ヒープのオブジェクトへのハンドルを格納するために使用する変数です。  
  
##  <a name="reallocate"></a>  Cwin32heap::reallocate  
 ヒープ オブジェクトからメモリ ブロックを再割り当てします。  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 再割り当てするメモリ ブロックへのポインター。  
  
 `nBytes`  
 割り当てられるブロックの新しいサイズ (バイト単位)。 ブロックは大きくすることも小さくすることもできます。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 場合`p`NULL の場合は、メモリ ブロックがまだ割り当てられていないことと見なされますと[cwin32heap::allocate](#allocate)が呼び出されると、引数は`nBytes`します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [クラス](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)
