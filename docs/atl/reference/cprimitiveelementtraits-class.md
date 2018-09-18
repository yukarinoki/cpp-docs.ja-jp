---
title: CPrimitiveElementTraits クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa5f96b8937168126509025735d20fab7b35c2b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019200"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits クラス

このクラスは既定のメソッドとプリミティブ データ型のコレクション クラスの関数で構成されます。

## <a name="syntax"></a>構文

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクション クラスのオブジェクトに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>Remarks

このクラスは、既定の静的関数および移動、コピー、比較、およびコレクション クラスのオブジェクトに格納されているプリミティブ データ型の要素をハッシュするためのメソッドを提供します。

詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll.h

##  <a name="inargtype"></a>  CPrimitiveElementTraits::INARGTYPE

コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。

```
typedef T INARGTYPE;
```

##  <a name="outargtype"></a>  CPrimitiveElementTraits::OUTARGTYPE

コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
