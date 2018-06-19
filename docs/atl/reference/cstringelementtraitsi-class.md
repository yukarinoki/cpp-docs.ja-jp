---
title: CStringElementTraitsI クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1544a2fec1c4567c301eb2c051f7455c8ca393c2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362106"
---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI クラス
このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 似ています[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)が小文字の比較を実行します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>  
class CStringElementTraitsI : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するのに使用するデータ型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraitsI::CompareElements](#compareelements)|ケースの相違を無視して、等しい 2 つの文字列要素を比較する、この静的関数を呼び出します。|  
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|ケースの相違を無視して、2 つの文字列要素を比較する、この静的関数を呼び出します。|  
|[CStringElementTraitsI::Hash](#hash)|指定した文字列の要素のハッシュ値を計算する、この静的関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、文字列を比較し、ハッシュ値を作成するために、静的関数を提供します。 これらの関数は、文字列ベースのデータを格納するコレクション クラスを使用する場合に便利です。 使用して[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)文字列オブジェクトに対処する参照として処理されます。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="compareelements"></a>  CStringElementTraitsI::CompareElements  
 ケースの相違を無視して、等しい 2 つの文字列要素を比較する、この静的関数を呼び出します。  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 要素が等しい場合は false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 比較では大文字小文字を区別します。  
  
##  <a name="compareelementsordered"></a>  CStringElementTraitsI::CompareElementsOrdered  
 ケースの相違を無視して、2 つの文字列要素を比較する、この静的関数を呼び出します。  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 ゼロの文字列が同一の場合、< 0 場合`str1`はより小さい`str2`、または > 0 場合`str1`がより大きい`str2`です。 [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)比較を実行するメソッドを使用します。  

  
### <a name="remarks"></a>コメント  
 比較では大文字小文字を区別します。  
  
##  <a name="hash"></a>  CStringElementTraitsI::Hash  
 指定した文字列の要素のハッシュ値を計算する、この静的関数を呼び出します。  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 文字列の要素。  
  
### <a name="return-value"></a>戻り値  
 文字列の内容を使用して計算されたハッシュ値を返します。  
  
##  <a name="inargtype"></a>  CStringElementTraitsI::INARGTYPE  
 コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CStringElementTraitsI::OUTARGTYPE  
 コレクション クラスのオブジェクトから要素を取得するのに使用するデータ型。  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>関連項目  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CStringElementTraits クラス](../../atl/reference/cstringelementtraits-class.md)
