---
title: CStringRefElementTraits クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8746bf216be417fb569aae58421b272c983914b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360688"
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits クラス
このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 文字列オブジェクトが参照として処理します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|2 つの文字列要素が等しいかどうかを比較する、この静的関数を呼び出します。|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|2 つの文字列要素を比較する、この静的関数を呼び出します。|  
|[CStringRefElementTraits::Hash](#hash)|指定した文字列の要素のハッシュ値を計算する、この静的関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、文字列を比較し、ハッシュ値を作成するために、静的関数を提供します。 これらの関数は、文字列ベースのデータを格納するコレクション クラスを使用する場合に便利です。 異なり[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)と[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)、`CStringRefElementTraits`により、`CString`として渡される引数を**const CString &** 参照します。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="compareelements"></a>  CStringRefElementTraits::CompareElements  
 2 つの文字列要素が等しいかどうかを比較する、この静的関数を呼び出します。  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `element1`  
 最初の要素を文字列します。  
  
 `element2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 要素が等しい場合は false それ以外の場合は true を返します。  
  
##  <a name="compareelementsordered"></a>  CStringRefElementTraits::CompareElementsOrdered  
 2 つの文字列要素を比較する、この静的関数を呼び出します。  
  
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
  
##  <a name="hash"></a>  CStringRefElementTraits::Hash  
 指定した文字列の要素のハッシュ値を計算する、この静的関数を呼び出します。  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 文字列の要素。  
  
### <a name="return-value"></a>戻り値  
 文字列の内容を使用して計算されたハッシュ値を返します。  
  
## <a name="see-also"></a>関連項目  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
