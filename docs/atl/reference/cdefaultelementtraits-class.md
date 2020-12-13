---
description: '詳細情報: CDefaultElementTraits クラス'
title: CDefaultElementTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: f4dd1bae67ef626ef793ecee946d88879a07f194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141896"
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits クラス

このクラスは、コレクションクラスの既定のメソッドと関数を提供します。

## <a name="syntax"></a>構文

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="remarks"></a>解説

このクラスには、コレクションクラスオブジェクトに格納されている要素の移動、コピー、比較、およびハッシュを行うための既定の静的関数とメソッドが用意されています。 このクラスは、 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)、 [cdefaulthashtraits](../../atl/reference/cdefaulthashtraits-class.md)、および [cdefaultcompare特徴](../../atl/reference/cdefaultcomparetraits-class.md)から派生した関数とメソッドを派生し、 [Celementtraits](../../atl/reference/celementtraits-class.md)、 [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)、および [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)によって使用されます。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
