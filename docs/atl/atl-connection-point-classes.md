---
title: ATL コネクション ポイント クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CFirePropNotifyEvent class, connection point classes
- connection points [C++], ATL classes
- ATL, connection points
- CComDynamicUnkArray class, connection point classes
- CFirePropNotifyEvent class
- CComUnkArray class, connection point classes
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 289ff7ae7db1abd6a0a19577a2c567b462a2910e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201401"
---
# <a name="atl-connection-point-classes"></a>ATL 接続ポイント クラス
ATL 接続ポイントをサポートするために、次のクラスを使用します。  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)接続ポイントを実装します。 表すアウトゴーイング インターフェイスの IID は、テンプレート パラメーターとして渡されます。  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md)接続ポイント コンテナーを実装およびの一覧を管理`IConnectionPointImpl`オブジェクト。  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md)を表す接続ポイントを実装して、 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイス。  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md)任意の数の接続ポイントとそのシンク間の接続を管理します。  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md)テンプレート パラメーターで指定された接続の定義済みの数を管理します。  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md)オブジェクトのプロパティが変更されたかを変更するには、クライアントのシンクに通知します。  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL COM オブジェクトの接続ポイントのサポートを提供します。 これらの接続ポイントは、COM オブジェクトによって提供されているイベント シンク マップにマップされます。  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)適切なハンドラー関数にイベントをルーティングするクラスでイベント シンク マップと連携します。  
  
## <a name="see-also"></a>関連項目  
 [接続ポイント](../atl/atl-connection-points.md)

