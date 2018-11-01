---
title: ATL 接続ポイント クラス
ms.date: 11/04/2016
helpviewer_keywords:
- CFirePropNotifyEvent class, connection point classes
- connection points [C++], ATL classes
- ATL, connection points
- CComDynamicUnkArray class, connection point classes
- CFirePropNotifyEvent class
- CComUnkArray class, connection point classes
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
ms.openlocfilehash: c4b2a9b295997c809acf9b037cd5f124f0752c3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439378"
---
# <a name="atl-connection-point-classes"></a>ATL 接続ポイント クラス

ATL 接続ポイントをサポートするために、次のクラスを使用します。

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)接続ポイントを実装します。 表すアウトゴーイング インターフェイスの IID は、テンプレート パラメーターとして渡されます。

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md)接続ポイント コンテナーを実装およびの一覧を管理`IConnectionPointImpl`オブジェクト。

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)を表す接続ポイントを実装して、 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイス。

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md)任意の数の接続ポイントとそのシンク間の接続を管理します。

- [CComUnkArray](../atl/reference/ccomunkarray-class.md)テンプレート パラメーターで指定された接続の定義済みの数を管理します。

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md)オブジェクトのプロパティが変更されたかを変更するには、クライアントのシンクに通知します。

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL COM オブジェクトの接続ポイントのサポートを提供します。 これらの接続ポイントは、COM オブジェクトによって提供されているイベント シンク マップにマップされます。

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)適切なハンドラー関数にイベントをルーティングするクラスでイベント シンク マップと連携します。

## <a name="see-also"></a>関連項目

[接続ポイント](../atl/atl-connection-points.md)

