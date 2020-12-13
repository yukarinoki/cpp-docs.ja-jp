---
description: '詳細情報: CComHeapPtr クラス'
title: CComHeapPtr クラス
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 18865923e86a2392260ab1e6dedde2f37b9b4ea3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146628"
---
# <a name="ccomheapptr-class"></a>CComHeapPtr クラス

ヒープポインターを管理するためのスマートポインタークラス。

## <a name="syntax"></a>構文

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ヒープに格納されるオブジェクトの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|コンストラクターです。|

## <a name="remarks"></a>解説

`CComHeapPtr` はから派生 `CHeapPtr` しますが、 [CComAllocator](../../atl/reference/ccomallocator-class.md) を使用して COM ルーチンを使用してメモリを割り当てます。 使用できるメソッドについては、「 [CHeapPtr](../../atl/reference/cheapptr-class.md) and [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a> CComHeapPtr::CComHeapPtr

コンストラクターです。

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>パラメーター

*pData*<br/>
既存の `CComHeapPtr` オブジェクトです。

### <a name="remarks"></a>解説

必要に応じて、既存のオブジェクトを使用してヒープポインターを作成することもでき `CComHeapPtr` ます。 その場合、新しいオブジェクトは、 `CComHeapPtr` 新しいポインターとリソースを管理する役割を担います。

## <a name="see-also"></a>関連項目

[CHeapPtr クラス](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)<br/>
[CComAllocator クラス](../../atl/reference/ccomallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
