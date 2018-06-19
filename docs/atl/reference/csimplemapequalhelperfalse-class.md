---
title: CSimpleMapEqualHelperFalse クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bebd9c6628924b5927fb48518925bdd665b0ee14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360019"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse クラス
このクラスは、のヘルパー、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(静的)2 つのキーの等価性をテストします。|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(静的)False を返します。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補足するため、`CSimpleMap`クラスです。 含まれる 2 つの要素を比較するためのメソッドを提供、`CSimpleMap`オブジェクト、値の要素を具体的には 2 つまたは 2 つの主要な要素です。  
  
 値の比較は常に false を返しますと、さらが呼び出されます`ATLASSERT`引数はこれまで参照されている場合は false。 等値テストが適切に定義されていない場合、このクラスは、ほとんどのメソッドを正常に動作などの比較に依存しているメソッドに対して適切に定義された方法で失敗する可能性がキー/値ペアを含むマップ[CSimpleMap:。FindVal](../../atl/reference/csimplemap-class.md#findval)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey  
 2 つのキーの等価性をテストします。  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>パラメーター  
 `k1`  
 最初のキー。  
  
 `k2`  
 2 番目のキー。  
  
### <a name="return-value"></a>戻り値  
 キーが等しい場合は false それ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)です。  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue  
 false を返します。  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>戻り値  
 false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは常に false を返し、呼び出されます`ATLASSERT`引数はこれまで参照されている場合は false。 目的は、`CSimpleMapEqualHelperFalse::IsEqualValue`等値テストが適切に定義されていないときに、適切に定義された方法で失敗する比較を使用する方法を強制することです。  
  
## <a name="see-also"></a>関連項目  
 [CSimpleMapEqualHelper クラス](../../atl/reference/csimplemapequalhelper-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
