---
title: クラスを使用します。
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
ms.openlocfilehash: fbdb77e7f52e858401c87e1cd8782b59cc6ebcea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330458"
---
# <a name="cwin32heap-class"></a>クラスを使用します。

このクラスは、Win32 ヒープ割り当て関数を使用して[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)を実装します。

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
|[CWin32ヒープ::CWin32ヒープ](#cwin32heap)|コンストラクターです。|
|[CWin32ヒープ::~CWin32ヒープ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWin32ヒープ::割り当て](#allocate)|ヒープ オブジェクトからメモリ ブロックを割り当てます。|
|[CWin32ヒープ::アタッチ](#attach)|ヒープ オブジェクトを既存のヒープにアタッチします。|
|[CWin32ヒープ::Dエタッハ](#detach)|ヒープ オブジェクトを既存のヒープからデタッチします。|
|[CWin32ヒープ::無料](#free)|以前にヒープから割り当てられたメモリを解放します。|
|[CWin32ヒープ::ゲットサイズ](#getsize)|ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。|
|[CWin32ヒープ::再割り当て](#reallocate)|ヒープ オブジェクトからメモリ ブロックを再割り当てします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CWin32ヒープ::m_bOwnHeap](#m_bownheap)|ヒープ ハンドルの現在の所有権を決定するために使用されるフラグ。|
|[CWin32ヒープ::m_hHeap](#m_hheap)|ヒープ オブジェクトへのハンドル。|

## <a name="remarks"></a>解説

`CWin32Heap`は、[ヒープアロック](/windows/win32/api/heapapi/nf-heapapi-heapalloc)や[ヒープフリー](/windows/win32/api/heapapi/nf-heapapi-heapfree)を含む Win32 ヒープ割り当て関数を使用してメモリ割り当てメソッドを実装します。 他の Heap`CWin32Heap`クラスとは異なり、メモリが割り当てられる前に、有効なヒープ ハンドルを指定する必要があります。 ハンドルは、コンストラクターまたは[CWin32Heap::Attach](#attach)メソッドに渡すことができます。 詳細については[、CWin32ヒープ::CWin32ヒープ](#cwin32heap)メソッドを参照してください。

## <a name="example"></a>例

[IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem.h

## <a name="cwin32heapallocate"></a><a name="allocate"></a>CWin32ヒープ::割り当て

ヒープ オブジェクトからメモリ ブロックを割り当てます。

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックへのポインターを返します。

### <a name="remarks"></a>解説

呼び出し[CWin32Heap::Free](#free)または[CWin32Heap::この](#reallocate)メソッドによって割り当てられたメモリを解放するために再割り当てします。

[を](/windows/win32/api/heapapi/nf-heapapi-heapalloc)使用して実装します。

## <a name="cwin32heapattach"></a><a name="attach"></a>CWin32ヒープ::アタッチ

ヒープ オブジェクトを既存のヒープにアタッチします。

```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>パラメーター

*hヒープ*<br/>
既存のヒープ ハンドル。

*オーナーシップ*<br/>
オブジェクトがヒープの`CWin32Heap`リソースに対して所有権を取得するかどうか示すフラグ。

### <a name="remarks"></a>解説

*bTakeOwnership*が TRUE`CWin32Heap`の場合、オブジェクトはヒープ ハンドルを削除します。

## <a name="cwin32heapcwin32heap"></a><a name="cwin32heap"></a>CWin32ヒープ::CWin32ヒープ

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

*hヒープ*<br/>
既存のヒープ オブジェクト。

*dwFlags*<br/>
ヒープの作成に使用されるフラグ。

*nInitialSize*<br/>
ヒープの初期サイズ。

*をクリックします。*<br/>
ヒープの最大サイズ。

### <a name="remarks"></a>解説

メモリを割り当てる前に、`CWin32Heap` オブジェクトに有効なヒープ ハンドルを提供する必要があります。 これを実現する最も簡単な方法は、プロセス ヒープを使用することです。

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

また、コンストラクターに既存のヒープ ハンドルを提供できますが、その場合には新しいオブジェクトはヒープの所有権を引き継ぎません。 `CWin32Heap` オブジェクトが削除されても、元のヒープ ハンドルは依然として有効です。

既存のヒープは[、CWin32Heap::Attach](#attach)を使用して、新しいオブジェクトにアタッチすることもできます。

すべての処理がシングル スレッドから行われるときに、ヒープが必要な場合、最適な方法は次のようにオブジェクトを作成することです。

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

HEAP_NO_SERIALIZE パラメーターでは、ヒープ関数でメモリの割り当ておよび解放を行うときに相互排他を使用しないことを指定します。これによって、相応のパフォーマンスの向上が得られます。

第 3 のパラメーターの既定値は 0 であり、この場合には必要に応じてヒープを拡大できます。 メモリサイズとフラグの説明については[、HeapCreate](/windows/win32/api/heapapi/nf-heapapi-heapcreate)を参照してください。

## <a name="cwin32heapcwin32heap"></a><a name="dtor"></a>CWin32ヒープ::~CWin32ヒープ

デストラクターです。

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>解説

オブジェクトがヒープの所有権を持`CWin32Heap`つ場合、ヒープ ハンドルを破棄します。

## <a name="cwin32heapdetach"></a><a name="detach"></a>CWin32ヒープ::Dエタッハ

ヒープ オブジェクトを既存のヒープからデタッチします。

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが以前にアタッチされていたヒープへのハンドルを返します。

## <a name="cwin32heapfree"></a><a name="free"></a>CWin32ヒープ::無料

以前にヒープから割り当てられたメモリを[CWin32Heap::Allocate](#allocate)または[CWin32Heap::再割り当て](#reallocate)によって解放します。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
解放するメモリ ブロックへのポインター。 NULL は有効な値であり、何も実行しません。

## <a name="cwin32heapgetsize"></a><a name="getsize"></a>CWin32ヒープ::ゲットサイズ

ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
メソッドが取得するサイズのメモリ ブロックへのポインター。 これは[、CWin32Heap::割り当て](#allocate)または[CWin32Heap::再割り当て](#reallocate)によって返されるポインタです。

### <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックのサイズ (バイト単位) を返します。

## <a name="cwin32heapm_bownheap"></a><a name="m_bownheap"></a>CWin32ヒープ::m_bOwnHeap

[m_hHeap](#m_hheap)に格納されているヒープ ハンドルの現在の所有権を決定するために使用されるフラグ。

```
bool m_bOwnHeap;
```

## <a name="cwin32heapm_hheap"></a><a name="m_hheap"></a>CWin32ヒープ::m_hHeap

ヒープ オブジェクトへのハンドル。

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>解説

ヒープ オブジェクトへのハンドルを格納するために使用される変数。

## <a name="cwin32heapreallocate"></a><a name="reallocate"></a>CWin32ヒープ::再割り当て

ヒープ オブジェクトからメモリ ブロックを再割り当てします。

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
再割り当てするメモリ ブロックへのポインター。

*Nbytes*<br/>
割り当てられるブロックの新しいサイズ (バイト単位)。 ブロックは大きくすることも小さくすることもできます。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックへのポインターを返します。

### <a name="remarks"></a>解説

*p が*NULL の場合は、メモリ ブロックがまだ割り当てられていないと見なされ、引数*nBytes*を指定して[CWin32Heap::Allocate](#allocate)が呼び出されます。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[イアトルメムグラムクラス](../../atl/reference/iatlmemmgr-class.md)<br/>
[クラス](../../atl/reference/clocalheap-class.md)<br/>
[クラス](../../atl/reference/cglobalheap-class.md)<br/>
[クラス](../../atl/reference/ccrtheap-class.md)<br/>
[クラス](../../atl/reference/ccomheap-class.md)
