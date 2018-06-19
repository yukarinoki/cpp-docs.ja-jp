---
title: CStringElementTraits クラス |Microsoft ドキュメント
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
ms.openlocfilehash: ddce07ed7f79c167d4cf819b85de1484346bba93
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363986"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits クラス
このクラスに格納するコレクション クラスで使用する静的関数が用意されています`CString`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するのに使用するデータ型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(静的)2 つの文字列要素が等しいかどうかを比較するには、この関数を呼び出します。|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(静的)2 つの文字列要素を比較するには、この関数を呼び出します。|  
|[CStringElementTraits::CopyElements](#copyelements)|(静的)コピーするには、この関数を呼び出す`CString`コレクション クラスのオブジェクトに格納されている要素です。|  
|[CStringElementTraits::Hash](#hash)|(静的)この関数では、指定された文字列の要素のハッシュ値を計算します。|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(静的)再配置するには、この関数を呼び出す`CString`コレクション クラスのオブジェクトに格納されている要素です。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コピー、移動、および文字列を比較して、ハッシュ値を作成するための静的関数を提供します。 これらの関数は、文字列ベースのデータを格納するコレクション クラスを使用する場合に便利です。 使用して[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)小文字の比較が必要な場合です。 使用して[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)文字列オブジェクトの参照として処理するときにします。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** cstringt.h  
  
##  <a name="compareelements"></a>  CStringElementTraits::CompareElements  
 2 つの文字列要素が等しいかどうかを比較する、この静的関数を呼び出します。  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 要素が等しい場合は false それ以外の場合は true を返します。  
  
##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered  
 2 つの文字列要素を比較する、この静的関数を呼び出します。  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 ゼロの文字列が同一の場合、< 0 場合`str1`はより小さい`str2`、または > 0 場合`str1`がより大きい`str2`です。 [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)比較を実行するメソッドを使用します。  

  
##  <a name="copyelements"></a>  CStringElementTraits::CopyElements  
 この静的関数をコピーする`CString`コレクション クラスのオブジェクトに格納されている要素です。  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 コピーしたデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 コピーする最初の要素へのポインター。  
  
 `nElements`  
 コピーする要素の数。  
  
### <a name="remarks"></a>コメント  
 ソースと移行先の要素が重ならないようにします。  
  
##  <a name="hash"></a>  CStringElementTraits::Hash  
 指定した文字列の要素のハッシュ値を計算する、この静的関数を呼び出します。  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 文字列の要素。  
  
### <a name="return-value"></a>戻り値  
 文字列の内容を使用して計算されたハッシュ値を返します。  
  
##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE  
 コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE  
 コレクション クラスのオブジェクトから要素を取得するのに使用するデータ型。  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements  
 この静的関数を再配置する`CString`コレクション クラスのオブジェクトに格納されている要素です。  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 再配置されたデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 再配置する最初の要素へのポインター。  
  
 `nElements`  
 再配置する要素の数。  
  
### <a name="remarks"></a>コメント  
 この静的関数を呼び出す[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)、これは、ほとんどのデータ型。 オブジェクトの移動中に、独自のメンバーへのポインターが含まれている場合は、この静的関数をオーバーライドする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI クラス](../../atl/reference/cstringelementtraitsi-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
