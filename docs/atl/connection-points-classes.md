---
title: コネクション ポイント クラス (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
ms.openlocfilehash: 8e1ee67f75af1fa38693f7ddb487580ab733cc58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250815"
---
# <a name="connection-points-classes"></a>コネクション ポイント クラス

次のクラスは、接続ポイントのサポート。

- [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md)接続ポイント コンテナーを実装します。

- [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)接続ポイントを実装します。

- [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)を表す接続ポイントを実装して、 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイス。

- [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md)接続ポイントとそのシンクの間の無制限の接続を管理します。

- [CComUnkArray](../atl/reference/ccomunkarray-class.md)固定数の接続ポイントとそのシンク間の接続を管理します。

- [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md)オブジェクトのプロパティが変更されたかを変更するには、クライアントのシンクに通知します。

- [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL COM オブジェクトの接続ポイントのサポートを提供します。 これらの接続ポイントは、COM オブジェクトによって提供されているイベント シンク マップにマップされます。

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)イベント シンクと連動させるが、適切なハンドラー関数にイベントをルーティングするクラスにマップします。

## <a name="related-articles"></a>関連トピック

[接続ポイント](../atl/atl-connection-points.md)

[イベント処理と ATL](../atl/event-handling-and-atl.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)<br/>
[接続ポイントに関するマクロ](../atl/reference/connection-point-macros.md)<br/>
[コネクション ポイントに関するグローバル関数](../atl/reference/connection-point-global-functions.md)
