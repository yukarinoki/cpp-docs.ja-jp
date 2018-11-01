---
title: IUnknown 実装クラス (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.Iunknown
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
ms.openlocfilehash: 0a15a256f961d35f5153c11da6690f6908e08a52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484124"
---
# <a name="iunknown-implementation-classes"></a>IUnknown 実装クラス

実装クラスの次`IUnknown`および関連するメソッド。

- [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)非集計と集計の両方のオブジェクトに対する参照カウントを管理します。 スレッド処理モデルを指定することができます。

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md)非集計と集計の両方のオブジェクトに対する参照カウントを管理します。 既定のサーバーのモデルのスレッドを使用します。

- [CComAggObject](../atl/reference/ccomaggobject-class.md)実装`IUnknown`集約オブジェクト。

- [CComObject](../atl/reference/ccomobject-class.md)実装`IUnknown`非集約オブジェクト。

- [CComPolyObject](../atl/reference/ccompolyobject-class.md)実装`IUnknown`集計および非集計オブジェクト。 使用して`CComPolyObject`両方が回避されます`CComAggObject`と`CComObject`モジュールでします。 1 つ`CComPolyObject`オブジェクトが非集計と集計の両方のケースを処理します。

- [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md)実装`IUnknown`モジュールのロック数を変更することがなく、非集約オブジェクト。

- [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md)実装`IUnknown`ティアオフ インターフェイス。

- [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md)実装`IUnknown`「キャッシュされた」ティアオフ インターフェイス。

- [CComContainedObject](../atl/reference/ccomcontainedobject-class.md)実装`IUnknown`の集計またはティアオフ インターフェイスの内部オブジェクト。

- [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md)管理オブジェクトを確実には、モジュールの参照カウントは削除されません。

- [CComObjectStack](../atl/reference/ccomobjectstack-class.md)のスケルトンの実装を使用して、一時的な COM オブジェクトを作成します。`IUnknown`します。

## <a name="related-articles"></a>関連トピック

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)<br/>
[集計とクラス ファクトリに関するマクロ](../atl/reference/aggregation-and-class-factory-macros.md)<br/>
[COM マップに関するマクロ](../atl/reference/com-map-macros.md)<br/>
[COM マップに関するグローバル関数](../atl/reference/com-map-global-functions.md)

