---
title: イベント処理インターフェイスを実装する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea37aa4c84cb0824d11f0081e38d9e8157b77ed1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356309"
---
# <a name="implementing-the-event-handling-interface"></a>イベント処理インターフェイスを実装します。
ATL を支援するイベントを処理するために必要なすべての 3 つの要素: イベント インターフェイスを実装する、イベント ソースのことを通知するイベント ソースをアドバイズとします。 実行する必要があります具体的な手順は、イベント インターフェイスと、アプリケーションのパフォーマンス要件の種類によって異なります。  
  
 ATL を使用してインターフェイスを実装する最も一般的な方法は次のとおりです。  
  
-   カスタム インターフェイスから直接派生します。  
  
-   派生する[IDispatchImpl](../atl/reference/idispatchimpl-class.md)デュアル インターフェイスのタイプ ライブラリに記述します。  
  
-   派生する[IDispEventImpl](../atl/reference/idispeventimpl-class.md)ディスパッチ インターフェイスのタイプ ライブラリに記述します。  
  
-   派生する[されます](../atl/reference/idispeventsimpleimpl-class.md)ディスパッチ インターフェイスの場合、タイプ ライブラリまたは実行時に型情報を読み込まないようにして効率を向上する場合に説明しません。  
  

 イベント ソースに呼び出すことによってお知らせくださいカスタムまたはデュアル インターフェイスを実装している場合[AtlAdvise](reference/connection-point-global-functions.md#atladvise)または[CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)です。 自分での呼び出しによって返されるクッキーを追跡する必要があります。 呼び出す[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)への接続を切断します。  

  
 使用して、ディスパッチ インターフェイスを実装する場合は`IDispEventImpl`または`IDispEventSimpleImpl`、イベント ソースに呼び出すことによってお知らせください[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)です。 呼び出す[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)への接続を切断します。  
  
 使用している場合`IDispEventImpl`複合コントロールの基底クラスとシンク マップに一覧表示するイベント ソースはされ、推奨を使用して自動的にアドバイズ[CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)です。  
  
 `IDispEventImpl`と`IDispEventSimpleImpl`クラスでは、cookie を管理します。  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)

