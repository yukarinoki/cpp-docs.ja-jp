---
description: '詳細情報: CPrimitiveElementTraits クラス'
title: CPrimitiveElementTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
ms.openlocfilehash: a9a47d9e6268ee6cc858d85e9236b00c270e8841
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141077"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits クラス

このクラスは、プリミティブデータ型で構成されるコレクションクラスの既定のメソッドと関数を提供します。

## <a name="syntax"></a>構文

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションクラスオブジェクトに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CPrimitiveElementTraits:: INARGTYPE](#inargtype)|コレクションクラスオブジェクトに要素を追加するために使用するデータ型。|
|[CPrimitiveElementTraits:: OUTARGTYPE](#outargtype)|コレクションクラスオブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスには、コレクションクラスオブジェクトに格納されているプリミティブデータ型の要素の移動、コピー、比較、およびハッシュを行うための既定の静的関数とメソッドが用意されています。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cprimitiveelementtraitsinargtype"></a><a name="inargtype"></a> CPrimitiveElementTraits:: INARGTYPE

コレクションクラスオブジェクトに要素を追加するために使用するデータ型。

```
typedef T INARGTYPE;
```

## <a name="cprimitiveelementtraitsoutargtype"></a><a name="outargtype"></a> CPrimitiveElementTraits:: OUTARGTYPE

コレクションクラスオブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
