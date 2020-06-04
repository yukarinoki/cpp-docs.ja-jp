---
title: クラス
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
ms.openlocfilehash: 5a29e8778cf2f3400df25b55574950a005bad995
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327001"
---
# <a name="celementtraitsbase-class"></a>クラス

このクラスは、コレクション クラスの既定のコピーおよび移動メソッドを提供します。

## <a name="syntax"></a>構文

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[C要素トレイトベース::イナルグタイプ](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|
|[ベース:アウトアルプタイプ](#outargtype)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[要素トレイトベース::コピー要素](#copyelements)|コレクション クラス オブジェクトに格納されている要素をコピーします。|
|[要素トレイトベース::再配置要素](#relocateelements)|コレクション クラス オブジェクトに格納されている要素を再配置します。|

## <a name="remarks"></a>解説

この基本クラスは、コレクション クラス内の要素をコピーおよび再配置するためのメソッドを定義します。 クラスによって利用されます。 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md) [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a>要素トレイトベース::コピー要素

コレクション クラス オブジェクトに格納されている要素をコピーします。

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
コピーされたデータを受け取る最初の要素へのポインター。

*pSrc*<br/>
コピーする最初の要素へのポインター。

*n要素*<br/>
コピーする要素の数。

### <a name="remarks"></a>解説

ソース要素とコピー先要素は重複しないようにします。

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a>C要素トレイトベース::イナルグタイプ

コレクションに要素を追加するために使用するデータ型。

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a>ベース:アウトアルプタイプ

コレクションから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a>要素トレイトベース::再配置要素

コレクション クラス オブジェクトに格納されている要素を再配置します。

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
再配置されたデータを受け取る最初の要素へのポインター。

*pSrc*<br/>
再配置する最初の要素へのポインター。

*n要素*<br/>
再配置する要素の数。

### <a name="remarks"></a>解説

このメソッドは、ほとんどのデータ型に対して十分な[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)を呼び出します。 移動するオブジェクトに自身のメンバーへのポインターが含まれている場合、このメソッドをオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
