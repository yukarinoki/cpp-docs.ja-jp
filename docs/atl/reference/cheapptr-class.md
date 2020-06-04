---
title: Cヒーププタークラス
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: a512aa974cb57072915f887f0c2a20ed1263ffa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326913"
---
# <a name="cheapptr-class"></a>Cヒーププタークラス

ヒープ ポインターを管理するためのスマート ポインター クラス。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ヒープに格納されるオブジェクト型。

*アロケーター*<br/>
使用するメモリ割り当てクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cヒーププター::Cヒーププター](#cheapptr)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cヒーププター::割り当て](#allocate)|オブジェクトを格納するヒープにメモリを割り当てます。|
|[Cヒーププター::再割り当て](#reallocate)|ヒープ上のメモリを再割り当てします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cヒーププター::演算子 =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

`CHeapPtr`は[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)から派生し、デフォルトでは CRT ルーチン[(CCRTAllocator)](../../atl/reference/ccrtallocator-class.md)を使用して、メモリの割り当てと解放を行います。 [CHeapPtrList](../../atl/reference/cheapptrlist-class.md)クラスを使用して、ヒープ ポインターのリストを作成できます。 COM メモリ割り当てルーチンを使用する[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)も参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ヒーププターベース](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="cheapptrallocate"></a><a name="allocate"></a>Cヒーププター::割り当て

オブジェクトを格納するヒープにメモリを割り当てます。

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>パラメーター

*n要素*<br/>
割り当てるメモリの量を計算するために使用される要素の数。 既定値は 1 です。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、失敗した場合は false を返します。

### <a name="remarks"></a>解説

アロケーター ルーチンは、コンストラクターで定義された型の*nElement*オブジェクトを格納するためにヒープに十分なメモリを予約するために使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a>Cヒーププター::Cヒーププター

コンストラクターです。

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
既存のヒープ ポインタ`CHeapPtr`または .

### <a name="remarks"></a>解説

ヒープ ポインターは、既存のポインターまたはオブジェクトを使用して、オプション`CHeapPtr`で作成できます。 その場合、新しい`CHeapPtr`オブジェクトは、新しいポインターとリソースを管理する責任を負います。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a>Cヒーププター::演算子 =

代入演算子。

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
既存の `CHeapPtr` オブジェクトです。

### <a name="return-value"></a>戻り値

更新された`CHeapPtr`への参照を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a>Cヒーププター::再割り当て

ヒープ上のメモリを再割り当てします。

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>パラメーター

*n要素*<br/>
割り当てるメモリの量を計算するために使用される新しい要素数。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、失敗した場合は false を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTアロケータークラス](../../atl/reference/ccrtallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
