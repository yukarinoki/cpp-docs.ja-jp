---
description: '詳細情報: CWin32Heap クラス'
title: CWin32Heap クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
ms.openlocfilehash: a19c7f01a572bad46dbbab2925104d4dfcf569be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140206"
---
# <a name="cwin32heap-class"></a>CWin32Heap クラス

このクラスは、Win32 ヒープ割り当て関数を使用して [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWin32Heap:: CWin32Heap](#cwin32heap)|コンストラクターです。|
|[CWin32Heap:: ~ CWin32Heap](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWin32Heap:: Allocate](#allocate)|ヒープ オブジェクトからメモリ ブロックを割り当てます。|
|[CWin32Heap:: Attach](#attach)|ヒープオブジェクトを既存のヒープにアタッチします。|
|[CWin32Heap::D etach](#detach)|ヒープオブジェクトを既存のヒープからデタッチします。|
|[CWin32Heap:: Free](#free)|以前にヒープから割り当てられたメモリを解放します。|
|[CWin32Heap:: GetSize](#getsize)|ヒープオブジェクトから割り当てられたメモリブロックのサイズを返します。|
|[CWin32Heap:: 再割り当て](#reallocate)|ヒープ オブジェクトからメモリ ブロックを再割り当てします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CWin32Heap:: m_bOwnHeap](#m_bownheap)|ヒープハンドルの現在の所有権を確認するために使用されるフラグ。|
|[CWin32Heap:: m_hHeap](#m_hheap)|ヒープオブジェクトへのハンドル。|

## <a name="remarks"></a>解説

`CWin32Heap` Win32 ヒープ割り当て関数 ( [HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc) および [heapfree](/windows/win32/api/heapapi/nf-heapapi-heapfree)を含む) を使用して、メモリ割り当てメソッドを実装します。 他のヒープクラスとは異なり、では、 `CWin32Heap` メモリが割り当てられる前に有効なヒープハンドルを提供する必要があります。他のクラスは、既定でプロセスヒープを使用します。 ハンドルは、コンストラクターまたは [CWin32Heap:: Attach](#attach) メソッドに渡すことができます。 詳細については、 [CWin32Heap:: CWin32Heap](#cwin32heap) メソッドを参照してください。

## <a name="example"></a>例

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>要件

**ヘッダー:** atlmem. h

## <a name="cwin32heapallocate"></a><a name="allocate"></a> CWin32Heap:: Allocate

ヒープ オブジェクトからメモリ ブロックを割り当てます。

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックへのポインターを返します。

### <a name="remarks"></a>解説

[CWin32Heap:: Free](#free)または[CWin32Heap::](#reallocate)の再割り当てを呼び出して、このメソッドによって割り当てられたメモリを解放します。

[HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc)を使用して実装されます。

## <a name="cwin32heapattach"></a><a name="attach"></a> CWin32Heap:: Attach

ヒープオブジェクトを既存のヒープにアタッチします。

```cpp
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>パラメーター

*hHeap*<br/>
既存のヒープハンドル。

*所有権*<br/>
`CWin32Heap`オブジェクトがヒープのリソースに対して所有権を取得するかどうかを示すフラグ。

### <a name="remarks"></a>解説

*Bの所有権* が TRUE の場合、 `CWin32Heap` オブジェクトはヒープハンドルを削除します。

## <a name="cwin32heapcwin32heap"></a><a name="cwin32heap"></a> CWin32Heap:: CWin32Heap

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

*hHeap*<br/>
既存のヒープ オブジェクト。

*dwFlags*<br/>
ヒープの作成に使用されるフラグ。

*nInitialSize*<br/>
ヒープの初期サイズ。

*nMaxSize*<br/>
ヒープの最大サイズ。

### <a name="remarks"></a>解説

メモリを割り当てる前に、`CWin32Heap` オブジェクトに有効なヒープ ハンドルを提供する必要があります。 これを実現する最も簡単な方法は、プロセス ヒープを使用することです。

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

また、コンストラクターに既存のヒープ ハンドルを提供できますが、その場合には新しいオブジェクトはヒープの所有権を引き継ぎません。 `CWin32Heap` オブジェクトが削除されても、元のヒープ ハンドルは依然として有効です。

[CWin32Heap:: Attach](#attach)を使用して、既存のヒープを新しいオブジェクトにアタッチすることもできます。

すべての処理がシングル スレッドから行われるときに、ヒープが必要な場合、最適な方法は次のようにオブジェクトを作成することです。

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

HEAP_NO_SERIALIZE パラメーターでは、ヒープ関数でメモリの割り当ておよび解放を行うときに相互排他を使用しないことを指定します。これによって、相応のパフォーマンスの向上が得られます。

第 3 のパラメーターの既定値は 0 であり、この場合には必要に応じてヒープを拡大できます。 メモリサイズとフラグの詳細については、「 [heapcreate 関数](/windows/win32/api/heapapi/nf-heapapi-heapcreate) 」を参照してください。

## <a name="cwin32heapcwin32heap"></a><a name="dtor"></a> CWin32Heap:: ~ CWin32Heap

デストラクターです。

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>解説

`CWin32Heap`オブジェクトにヒープの所有権がある場合は、ヒープハンドルを破棄します。

## <a name="cwin32heapdetach"></a><a name="detach"></a> CWin32Heap::D etach

ヒープオブジェクトを既存のヒープからデタッチします。

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが既にアタッチされていたヒープへのハンドルを返します。

## <a name="cwin32heapfree"></a><a name="free"></a> CWin32Heap:: Free

[CWin32Heap:: Allocate](#allocate)または[CWin32Heap:: 再割り当て](#reallocate)によって以前にヒープから割り当てられたメモリを解放します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
解放するメモリブロックへのポインター。 NULL は有効な値であり、何も行いません。

## <a name="cwin32heapgetsize"></a><a name="getsize"></a> CWin32Heap:: GetSize

ヒープオブジェクトから割り当てられたメモリブロックのサイズを返します。

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
メソッドによって取得されるサイズを持つメモリブロックへのポインター。 これは、 [CWin32Heap:: Allocate](#allocate) または [CWin32Heap:: 再割り当て](#reallocate)によって返されるポインターです。

### <a name="return-value"></a>戻り値

割り当てられたメモリブロックのサイズ (バイト単位) を返します。

## <a name="cwin32heapm_bownheap"></a><a name="m_bownheap"></a> CWin32Heap:: m_bOwnHeap

[M_hHeap](#m_hheap)に格納されているヒープハンドルの現在の所有権を確認するために使用されるフラグ。

```
bool m_bOwnHeap;
```

## <a name="cwin32heapm_hheap"></a><a name="m_hheap"></a> CWin32Heap:: m_hHeap

ヒープオブジェクトへのハンドル。

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>解説

ヒープオブジェクトへのハンドルを格納するために使用される変数。

## <a name="cwin32heapreallocate"></a><a name="reallocate"></a> CWin32Heap:: 再割り当て

ヒープ オブジェクトからメモリ ブロックを再割り当てします。

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
再割り当てするメモリ ブロックへのポインター。

*nBytes*<br/>
割り当てられるブロックの新しいサイズ (バイト単位)。 ブロックは大きくすることも小さくすることもできます。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックへのポインターを返します。

### <a name="remarks"></a>解説

*P* が NULL の場合は、メモリブロックがまだ割り当てられておらず、 [CWin32Heap:: Allocate](#allocate)が呼び出されます。引数は *nbytes* です。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)<br/>
[CLocalHeap クラス](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)<br/>
[CComHeap クラス](../../atl/reference/ccomheap-class.md)
