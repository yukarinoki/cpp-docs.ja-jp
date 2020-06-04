---
title: クラスの比較
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: 8262800ef613424c37c53931d97dd4b1b1a71321
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327075"
---
# <a name="cdefaultcomparetraits-class"></a>クラスの比較

このクラスには、既定の要素比較関数が用意されています。

## <a name="syntax"></a>構文

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[要素の比較](#compareelements)|(静的)2 つの要素が等しいかどうかを比較します。|
|[並べ替え要素数::比較要素](#compareelementsordered)|(静的)この関数を呼び出して、大きくて小さい要素を決定します。|

## <a name="remarks"></a>解説

このクラスには、コレクション クラス オブジェクトに格納されている要素を比較するための 2 つの静的関数が含まれています。 このクラスは、[クラスによって使用されます](../../atl/reference/cdefaultelementtraits-class.md)。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a>要素の比較

2 つの要素が等しいかどうかを比較します。

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>パラメーター

*要素1*<br/>
1 番目の要素。

*要素2*<br/>
2 番目の要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、そうでない場合は false を返します。

### <a name="remarks"></a>解説

この関数の既定の実装は、等値**==**( ) 演算子です。 単純データ型以外のオブジェクトの場合、この関数をオーバーライドする必要があります。

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a>並べ替え要素数::比較要素

この関数を呼び出して、大きくて小さい要素を決定します。

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>パラメーター

*要素1*<br/>
1 番目の要素。

*要素2*<br/>
2 番目の要素。

### <a name="return-value"></a>戻り値

次の表に基づいて整数を返します。

|条件|戻り値|
|---------------|------------------|
|*要素1* < *要素2*|<0|
|*要素1* == *要素2*|0|
|*要素1* > *要素2*|>0|

### <a name="remarks"></a>解説

この関数の既定の実装では、 **==** **\<**、 **>** 、および 演算子が使用されます。 単純データ型以外のオブジェクトの場合、この関数をオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
