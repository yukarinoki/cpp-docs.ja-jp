---
description: '詳細情報: CComObjectRoot クラス'
title: CComObjectRoot クラス
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 924b85ee7ed6e17eb44e753ad16f57251bb189ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142468"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot クラス

この [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) の typedef は、サーバーの既定のスレッドモデルでテンプレート化されています。

## <a name="syntax"></a>構文

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>解説

`CComObjectRoot` は、 **`typedef`** サーバーの既定のスレッドモデルの [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) テンプレート化のです。 したがって、 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) は [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) または [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を参照します。

`CComObjectRootEx` 非集計と集計されたオブジェクトの両方のオブジェクト参照カウント管理を処理します。 オブジェクトが集計されていない場合、オブジェクト参照カウントを保持し、オブジェクトが集計されている場合は、外側の unknown へのポインターを保持します。 集計オブジェクトの場合、 `CComObjectRootEx` メソッドを使用して、構築する内部オブジェクトのエラーを処理したり、内部インターフェイスが解放されたとき、または内部オブジェクトが削除されたときに外部オブジェクトを削除から保護したりできます。

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="see-also"></a>関連項目

[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
