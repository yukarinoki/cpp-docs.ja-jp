---
title: CDefaultElementTraits クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16574857f4f5bd4566fcef551fa5e56290b7ce6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360963"
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits クラス
このクラスは、コレクション クラスの既定のメソッドおよび関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="remarks"></a>コメント  
 このクラスは、移動、コピー、比較、およびコレクション クラスのオブジェクトに格納されているハッシュ要素の既定の静的な関数とメソッドを提供します。 このクラスは、その関数やメソッドから派生している[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)、 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)、および[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)、によって使用されて、 [CElementTraits](../../atl/reference/celementtraits-class.md)、 [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)、および[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
