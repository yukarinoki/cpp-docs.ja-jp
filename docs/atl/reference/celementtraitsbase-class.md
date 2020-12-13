---
description: '詳細情報: CElementTraitsBase クラス'
title: CElementTraitsBase クラス
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: a200517e378cc3c3ca854ff60e9a49ac8e43d215
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141779"
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase クラス

このクラスは、コレクションクラスの既定のコピーおよび移動メソッドを提供します。

## <a name="syntax"></a>構文

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CElementTraitsBase:: INARGTYPE](#inargtype)|コレクションクラスオブジェクトに要素を追加するために使用するデータ型。|
|[CElementTraitsBase:: OUTARGTYPE](#outargtype)|コレクションクラスオブジェクトから要素を取得するために使用するデータ型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CElementTraitsBase:: CopyElements](#copyelements)|コレクションクラスオブジェクトに格納されている要素をコピーするには、このメソッドを呼び出します。|
|[CElementTraitsBase::RelocateElements](#relocateelements)|コレクションクラスオブジェクトに格納されている要素を再配置するには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

この基本クラスは、コレクションクラスの要素をコピーおよび再配置するためのメソッドを定義します。 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)、 [cstringrefelementtraits](../../atl/reference/cstringrefelementtraits-class.md)、および[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)クラスによって使用されます。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a> CElementTraitsBase:: CopyElements

コレクションクラスオブジェクトに格納されている要素をコピーするには、このメソッドを呼び出します。

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
コピーされたデータを受け取る最初の要素へのポインター。

*.Psrc*<br/>
コピーする最初の要素へのポインター。

*nElements*<br/>
コピーする要素の数。

### <a name="remarks"></a>解説

コピー元とコピー先の要素を重複させることはできません。

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a> CElementTraitsBase:: INARGTYPE

コレクションに要素を追加するために使用するデータ型。

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a> CElementTraitsBase:: OUTARGTYPE

コレクションから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a> CElementTraitsBase::RelocateElements

コレクションクラスオブジェクトに格納されている要素を再配置するには、このメソッドを呼び出します。

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
再配置されたデータを受け取る最初の要素へのポインター。

*.Psrc*<br/>
再配置する最初の要素へのポインター。

*nElements*<br/>
再配置する要素の数。

### <a name="remarks"></a>解説

このメソッドは、ほとんどのデータ型に対して十分な [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)を呼び出します。 移動するオブジェクトに独自のメンバーへのポインターが含まれている場合は、このメソッドをオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
