---
title: CElementTraits クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61cbd301d01d62c0d24f232703b53cebf411a082
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021071"
---
# <a name="celementtraits-class"></a>CElementTraits クラス

このクラスは、移動、コピー、比較、およびハッシュ演算のメソッドや関数を提供するコレクション クラスによって使用されます。

## <a name="syntax"></a>構文

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="remarks"></a>Remarks

このクラスは、移動、コピー、比較、およびコレクション クラスのオブジェクトに格納されているハッシュの要素の既定の静的関数およびメソッドを提供します。 `CElementTraits` コレクション クラスでこれらの操作の既定のプロバイダーとして指定された[CAtlArray](../../atl/reference/catlarray-class.md)、 [CAtlList](../../atl/reference/catllist-class.md)、 [CRBMap](../../atl/reference/crbmap-class.md)、 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)、および[CRBTree](../../atl/reference/crbtree-class.md)します。

単純なデータ型の場合は、既定の実装で十分ですが、関数およびメソッドをユーザーが指定した実装でオーバーライドする必要がありますより複雑なオブジェクトを格納するコレクション クラスを使用する場合。

詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll.h

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
