---
title: CSimpleArrayEqualHelperFalse クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e22d67634f29b60bdc983c892c5fe266df61d08
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358206"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse クラス
このクラスは、のヘルパー、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生クラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(静的)False を返します。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補完する、`CSimpleArray`クラスです。 False の場合とさらを返しますの呼び出しは常に it`ATLASSERT`引数はこれまで参照されている場合は false。 等値テストが適切に定義されていない場合、このクラスは、ほとんどのメソッドを正常に動作などの比較に依存しているメソッドに対して適切に定義された方法で失敗する可能性が要素を含む配列[CSimpleArray:。検索](../../atl/reference/csimplearray-class.md#find)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="isequal"></a>  CSimpleArrayEqualHelperFalse::IsEqual  
 false を返します。  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>戻り値  
 false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは常に false を返し、呼び出されます`ATLASSERT`引数は参照されている場合は false。 目的は、`CSimpleArrayEqualHelperFalse::IsEqual`等値テストが適切に定義されていないときに、適切に定義された方法で失敗する比較を使用する方法を強制することです。  
  
## <a name="see-also"></a>関連項目  
 [CSimpleArrayEqualHelper クラス](../../atl/reference/csimplearrayequalhelper-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
