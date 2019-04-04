---
title: CDefaultElementTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: 0ee076af5fc4a1c2145162ac510b3a4460e251e0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298855"
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

*T*<br/>
コレクションに格納されるデータの型。

## <a name="remarks"></a>Remarks

このクラスは、移動、コピー、比較、およびコレクション クラスのオブジェクトに格納されているハッシュの要素の既定の静的関数およびメソッドを提供します。 その関数とメソッドをこのクラスの派生[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)、 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)、および[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)を使用していると[CElementTraits](../../atl/reference/celementtraits-class.md)、 [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)、および[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)します。

詳細については、[ATL コレクション クラス](../../atl/atl-collection-classes.md)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
