---
description: '詳細情報: CDefaultCompareTraits クラス'
title: CDefaultCompareTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: dcb366cdcd99a6eed2b641be290ccc4913a81476
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141909"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits クラス

このクラスには、既定の要素比較関数が用意されています。

## <a name="syntax"></a>構文

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDefaultCompareTraits:: CompareElements](#compareelements)|雑音2つの要素が等しいかどうかを比較するには、この関数を呼び出します。|
|[CDefaultCompareTraits:: CompareElementsOrdered](#compareelementsordered)|雑音この関数を呼び出して、より大きい要素と小さい要素を決定します。|

## <a name="remarks"></a>解説

このクラスには、コレクションクラスオブジェクトに格納されている要素を比較するための2つの静的関数が含まれています。 このクラスは、 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)によって使用されます。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a> CDefaultCompareTraits:: CompareElements

2つの要素が等しいかどうかを比較するには、この関数を呼び出します。

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>パラメーター

*element1*<br/>
1 番目の要素。

*element2*<br/>
2番目の要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

この関数の既定の実装は、等値 ( **==** ) 演算子です。 単純なデータ型以外のオブジェクトの場合、この関数をオーバーライドする必要がある場合があります。

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a> CDefaultCompareTraits:: CompareElementsOrdered

この関数を呼び出して、より大きい要素と小さい要素を決定します。

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>パラメーター

*element1*<br/>
1 番目の要素。

*element2*<br/>
2番目の要素。

### <a name="return-value"></a>戻り値

次の表に基づく整数を返します。

|条件|戻り値|
|---------------|------------------|
|*element1*  < *element2*|<0|
|*element1*  == *element2*|0|
|*element1*  > *element2*|>0|

### <a name="remarks"></a>解説

この関数の既定の実装では **==** 、演算子を使用し **\<**, and **>** ます。 単純なデータ型以外のオブジェクトの場合、この関数をオーバーライドする必要がある場合があります。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
