---
description: '詳細情報: CHeapPtr クラス'
title: CHeapPtr クラス
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
ms.openlocfilehash: dc795c199562fa423a160b053c96983651d0812d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141649"
---
# <a name="cheapptr-class"></a>CHeapPtr クラス

ヒープポインターを管理するためのスマートポインタークラス。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ヒープに格納されるオブジェクトの種類。

*アロケーター*<br/>
使用するメモリ割り当てクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHeapPtr:: Allocate](#allocate)|オブジェクトを格納するためにヒープにメモリを割り当てるには、このメソッドを呼び出します。|
|[CHeapPtr:: 再割り当て](#reallocate)|ヒープ上のメモリを再割り当てするには、このメソッドを呼び出します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CHeapPtr:: operator =](#operator_eq)|代入演算子。|

## <a name="remarks"></a>解説

`CHeapPtr` は [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) から派生し、既定では CRT ルーチン ( [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) を使用してメモリの割り当てと解放を行います。 クラスは、ヒープポインターのリストを構築するために [使用できます](../../atl/reference/cheapptrlist-class.md) 。 COM メモリ割り当てルーチンを使用する「 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md)」も参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>要件

**ヘッダー:** atlcore .h

## <a name="cheapptrallocate"></a><a name="allocate"></a> CHeapPtr:: Allocate

オブジェクトを格納するためにヒープにメモリを割り当てるには、このメソッドを呼び出します。

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>パラメーター

*nElements*<br/>
割り当てるメモリの量を計算するために使用される要素の数。 既定値は 1 です。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、失敗した場合は false を返します。

### <a name="remarks"></a>解説

アロケータールーチンは、コンストラクターで定義されている型の *nElement* オブジェクトを格納するために、ヒープに十分なメモリを確保するために使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a> CHeapPtr::CHeapPtr

コンストラクターです。

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
既存のヒープポインターまたは `CHeapPtr` 。

### <a name="remarks"></a>解説

ヒープポインターは、必要に応じて、既存のポインターまたはオブジェクトを使用して作成でき `CHeapPtr` ます。 その場合、新しいオブジェクトは、 `CHeapPtr` 新しいポインターとリソースを管理する役割を担います。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a> CHeapPtr:: operator =

代入演算子。

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
既存の `CHeapPtr` オブジェクトです。

### <a name="return-value"></a>戻り値

更新されたへの参照を返し `CHeapPtr` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a> CHeapPtr:: 再割り当て

ヒープ上のメモリを再割り当てするには、このメソッドを呼び出します。

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>パラメーター

*nElements*<br/>
割り当てるメモリの量を計算するために使用される新しい要素の数。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、失敗した場合は false を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>関連項目

[CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTAllocator クラス](../../atl/reference/ccrtallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
