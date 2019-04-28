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
ms.openlocfilehash: f3794b5c9e4f6297cca6611929c75d0b0133557e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252231"
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
