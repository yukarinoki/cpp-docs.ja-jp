---
description: '詳細情報: IUnknown 実装クラス'
title: IUnknown 実装クラス (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
ms.openlocfilehash: a28bd14be86501fd6566b8038b73a51efcc1c18d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147655"
---
# <a name="iunknown-implementation-classes"></a>IUnknown 実装クラス

次のクラスは、 `IUnknown` および関連するメソッドを実装します。

- [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 集計オブジェクトと非集計オブジェクトの両方の参照カウントを管理します。 スレッドモデルを指定できます。

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 集計オブジェクトと非集計オブジェクトの両方の参照カウントを管理します。 では、サーバーの既定のスレッドモデルが使用されます。

- [CComAggObject](../atl/reference/ccomaggobject-class.md)`IUnknown`集計されたオブジェクトに対してを実装します。

- [CComObject](../atl/reference/ccomobject-class.md)`IUnknown`非集計オブジェクトに対してを実装します。

- [CComPolyObject](../atl/reference/ccompolyobject-class.md)`IUnknown`集計オブジェクトと非集計オブジェクトに対してを実装します。 を使用する `CComPolyObject` `CComAggObject` と、モジュールにとの両方を持つことが回避さ `CComObject` れます。 1つのオブジェクトは、 `CComPolyObject` 集計されたケースと非集計ケースの両方を処理します。

- [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md)`IUnknown`モジュールのロック数を変更せずに、非集計オブジェクトのを実装します。

- [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md)`IUnknown`ティアオフインターフェイス用にを実装します。

- [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md)`IUnknown`"キャッシュされた" ティアオフインターフェイス用にを実装します。

- [CComContainedObject](../atl/reference/ccomcontainedobject-class.md)`IUnknown`集計またはティアオフインターフェイスの内部オブジェクトに対してを実装します。

- [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) オブジェクトが削除されないように、モジュールの参照カウントを管理します。

- [CComObjectStack](../atl/reference/ccomobjectstack-class.md) のスケルトン実装を使用して、一時 COM オブジェクトを作成し `IUnknown` ます。

## <a name="related-articles"></a>関連記事

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)<br/>
[集計およびクラスファクトリマクロ](../atl/reference/aggregation-and-class-factory-macros.md)<br/>
[COM マップマクロ](../atl/reference/com-map-macros.md)<br/>
[COM マップのグローバル関数](../atl/reference/com-map-global-functions.md)
