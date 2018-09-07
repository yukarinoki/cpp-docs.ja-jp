---
title: CDefaultElementTraits クラス |Microsoft Docs
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
ms.openlocfilehash: de61165ecac24e9c892dd5e95b1bb4e042a34fa1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763784"
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

*T*  
コレクションに格納されるデータの型。

## <a name="remarks"></a>Remarks

このクラスは、移動、コピー、比較、およびコレクション クラスのオブジェクトに格納されているハッシュの要素の既定の静的関数およびメソッドを提供します。 その関数とメソッドをこのクラスの派生[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)、 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)、および[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)を使用していると[CElementTraits](../../atl/reference/celementtraits-class.md)、 [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)、および[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)します。

詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll.h

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
