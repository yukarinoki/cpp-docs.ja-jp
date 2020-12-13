---
description: '詳細情報: CHeapPtrElementTraits クラス'
title: CHeapPtrElementTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: 7ca3d194a284f06e6b5baa0530cb49bc93d8510a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141610"
---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits クラス

このクラスは、ヒープポインターのコレクションを作成するときに便利なメソッド、静的関数、および typedef を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits :
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションクラスに格納されるオブジェクトの型。

*アロケーター*<br/>
使用するメモリ割り当てクラス。 既定値は [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CHeapPtrElementTraits:: INARGTYPE](#inargtype)|コレクションクラスオブジェクトに要素を追加するために使用するデータ型。|
|[CHeapPtrElementTraits:: OUTARGTYPE](#outargtype)|コレクションクラスオブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスには、ヒープポインターを含むコレクションクラスオブジェクトの作成を支援するためのメソッド、静的関数、および typedef が用意されています。 クラスは `CHeapPtrList` から派生 `CHeapPtrElementTraits` します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cheapptrelementtraitsinargtype"></a><a name="inargtype"></a> CHeapPtrElementTraits:: INARGTYPE

コレクションクラスオブジェクトに要素を追加するために使用するデータ型。

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

## <a name="cheapptrelementtraitsoutargtype"></a><a name="outargtype"></a> CHeapPtrElementTraits:: OUTARGTYPE

コレクションクラスオブジェクトから要素を取得するために使用するデータ型。

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
