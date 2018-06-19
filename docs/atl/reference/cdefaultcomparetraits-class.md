---
title: CDefaultCompareTraits クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5b06bf475c60c0190fc6ab78f4357e1b247f1d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361640"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits クラス
このクラスは、既定の要素の比較関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(静的)2 つの要素が等しいかどうかを比較するには、この関数を呼び出します。|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(静的)この関数では、大小の要素を決定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスには、コレクション クラスのオブジェクトに格納されている要素を比較する 2 つの静的関数が含まれています。 このクラスは、によって使用されて、 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="compareelements"></a>  CDefaultCompareTraits::CompareElements  
 2 つの要素が等しいかどうかを比較するには、この関数を呼び出します。  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>パラメーター  
 `element1`  
 1 番目の要素。  
  
 `element2`  
 2 番目の要素。  
  
### <a name="return-value"></a>戻り値  
 要素が等しい場合は false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、等しいかどうか ( `==`) 演算子。 単純なデータ型以外のオブジェクト、この関数は、オーバーライドする必要があります。  
  
##  <a name="compareelementsordered"></a>  CDefaultCompareTraits::CompareElementsOrdered  
 この関数では、大小の要素を決定します。  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>パラメーター  
 `element1`  
 1 番目の要素。  
  
 `element2`  
 2 番目の要素。  
  
### <a name="return-value"></a>戻り値  
 次の表に基づいて整数が返されます。  
  
|条件|戻り値|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を使用して、 `==`、 **\<**、および**>** 演算子。 単純なデータ型以外のオブジェクト、この関数は、オーバーライドする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
