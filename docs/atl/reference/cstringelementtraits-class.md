---
title: CStringElementTraits クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43581995e8979ec733d8c82374896009c843166b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766647"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits クラス

このクラスを格納するコレクション クラスで使用される静的関数を提供する`CString`オブジェクト。

## <a name="syntax"></a>構文

```
template <typename T>  
class CStringElementTraits
```

#### <a name="parameters"></a>パラメーター

*T*  
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|(静的)2 つの文字列要素が等しいかどうかを比較するには、この関数を呼び出します。|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(静的)2 つの文字列要素を比較するには、この関数を呼び出します。|
|[CStringElementTraits::CopyElements](#copyelements)|(静的)コピーするには、この関数を呼び出す`CString`コレクション クラスのオブジェクトに格納されている要素。|
|[CStringElementTraits::Hash](#hash)|(静的)指定した文字列の要素のハッシュ値を計算するには、この関数を呼び出します。|
|[CStringElementTraits::RelocateElements](#relocateelements)|(静的)再配置するには、この関数を呼び出す`CString`コレクション クラスのオブジェクトに格納されている要素。|

## <a name="remarks"></a>Remarks

このクラスは、コピー、移動、および文字列を比較して、ハッシュ値を作成するための静的関数を提供します。 これらの関数は、文字列ベースのデータを格納するコレクション クラスを使用する場合に便利です。 使用[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)小文字の比較が必要な場合。 使用[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)文字列オブジェクトの参照として処理する場合。

詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** cstringt.h

##  <a name="compareelements"></a>  CStringElementTraits::CompareElements

2 つの文字列要素が等しいかどうかを比較する、この静的関数を呼び出します。

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>パラメーター

*str1*  
最初の要素を文字列します。

*str2*  
2 番目の文字列要素。

### <a name="return-value"></a>戻り値

要素が false でそれ以外の場合、等しい場合は true を返します。

##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered

2 つの文字列要素を比較する、この静的関数を呼び出します。

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>パラメーター

*str1*  
最初の要素を文字列します。

*str2*  
2 番目の文字列要素。

### <a name="return-value"></a>戻り値

< 0、0 の文字列が一致している場合場合*str1*がより小さい*str2*、または > 0 場合*str1*がより大きい*str2*します。 [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)メソッドは、比較を実行するために使用します。  

##  <a name="copyelements"></a>  CStringElementTraits::CopyElements

この静的関数をコピーする`CString`コレクション クラスのオブジェクトに格納されている要素。

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*  
コピー元のデータを受信する最初の要素へのポインター。

*pSrc*  
コピーする最初の要素へのポインター。

*nElements*  
コピーする要素の数。

### <a name="remarks"></a>Remarks

ソースと変換先の要素は重複できません。

##  <a name="hash"></a>  CStringElementTraits::Hash

指定した文字列の要素のハッシュ値を計算する、この静的関数を呼び出します。

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>パラメーター

*str*  
文字列の要素。

### <a name="return-value"></a>戻り値

文字列の内容を使用して計算されたハッシュ値を返します。

##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE

コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE

コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements

配置する場合に、この静的関数を呼び出す`CString`コレクション クラスのオブジェクトに格納されている要素。

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*  
再配置されたデータを受信する最初の要素へのポインター。

*pSrc*  
配置する場合に、最初の要素へのポインター。

*nElements*  
配置する場合に要素の数。

### <a name="remarks"></a>Remarks

この静的関数を呼び出す[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)、これは、ほとんどのデータ型。 オブジェクトの移動中に、独自のメンバーへのポインターが含まれている場合は、この静的関数をオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
[CStringElementTraitsI クラス](../../atl/reference/cstringelementtraitsi-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
