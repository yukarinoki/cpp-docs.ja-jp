---
title: CComObjectRoot クラス
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 98868e67fd14899a75f86837034ba540d22039e3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224241"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot クラス

この[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)の typedef は、サーバーの既定のスレッドモデルでテンプレート化されています。

## <a name="syntax"></a>構文

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>解説

`CComObjectRoot`は、 **`typedef`** サーバーの既定のスレッドモデルの[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)テンプレート化のです。 したがって、 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)は[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)または[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)を参照します。

`CComObjectRootEx`非集計と集計されたオブジェクトの両方のオブジェクト参照カウント管理を処理します。 オブジェクトが集計されていない場合、オブジェクト参照カウントを保持し、オブジェクトが集計されている場合は、外側の unknown へのポインターを保持します。 集計オブジェクトの場合、 `CComObjectRootEx` メソッドを使用して、構築する内部オブジェクトのエラーを処理したり、内部インターフェイスが解放されたとき、または内部オブジェクトが削除されたときに外部オブジェクトを削除から保護したりできます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

## <a name="see-also"></a>関連項目

[CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject クラス](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject クラス](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject クラス](../../atl/reference/ccompolyobject-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
