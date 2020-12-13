---
description: '詳細情報: CElementTraits クラス'
title: CElementTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 1bcb6c9da2bca733efe68b634eebd7f379ba0d10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141805"
---
# <a name="celementtraits-class"></a>CElementTraits クラス

このクラスは、移動、コピー、比較、およびハッシュ操作のためのメソッドと関数を提供するために、コレクションクラスによって使用されます。

## <a name="syntax"></a>構文

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="remarks"></a>解説

このクラスには、コレクションクラスオブジェクトに格納されている要素の移動、コピー、比較、およびハッシュを行うための既定の静的関数とメソッドが用意されています。 `CElementTraits` は、コレクションクラス [CAtlArray](../../atl/reference/catlarray-class.md)、 [CAtlList](../../atl/reference/catllist-class.md)、 [CRBMap](../../atl/reference/crbmap-class.md)、 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)、および [CRBTree](../../atl/reference/crbtree-class.md)によってこれらの操作の既定のプロバイダーとして指定されます。

既定の実装では、単純なデータ型には十分ですが、コレクションクラスを使用してより複雑なオブジェクトを格納する場合は、ユーザー指定の実装によって関数とメソッドをオーバーライドする必要があります。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
