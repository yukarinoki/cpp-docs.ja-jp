---
title: イベント処理インターフェイスを実装する |Microsoft Docs
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
ms.openlocfilehash: b2241080fda6aa58dc5e70f57c83afec69a57203
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757339"
---
# <a name="implementing-the-event-handling-interface"></a>イベント処理インターフェイスを実装します。

ATL イベントを処理するために必要なすべての 3 つの要素では、: イベント ソースのアドバイスを行って、イベント ソースをアドバイズ イベント インターフェイスを実装します。 実行する必要があります、正確な手順は、イベント インターフェイスと、アプリケーションのパフォーマンス要件の種類によって異なります。

ATL を使用してインターフェイスを実装する最も一般的な方法は次のとおりです。

- カスタム インターフェイスから直接派生します。

- 派生する[IDispatchImpl](../atl/reference/idispatchimpl-class.md)デュアル インターフェイスのタイプ ライブラリに記述します。

- 派生する[IDispEventImpl](../atl/reference/idispeventimpl-class.md)ディスパッチ インターフェイスのタイプ ライブラリで説明されている場合。

- 派生する[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)ディスパッチ インターフェイスの場合、タイプ ライブラリまたは実行時に型情報を読み込まないようにして効率を向上する場合に説明しません。

呼び出すことによって、イベント ソースをお勧めする必要があります、カスタムまたはデュアル インターフェイスを実装する場合[AtlAdvise](reference/connection-point-global-functions.md#atladvise)または[CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)します。 自分での呼び出しによって返されるクッキーを追跡する必要があります。 呼び出す[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)結合を解除します。  

使用してディスパッチ インターフェイスを実装している場合`IDispEventImpl`または`IDispEventSimpleImpl`、呼び出すことによって、イベント ソースを知らせるはず[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)します。 呼び出す[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)結合を解除します。

使用する場合`IDispEventImpl`伝えたとアドバイズを使用して自動的に複合コントロールの基底クラスとしてシンク マップの一覧にあるイベント ソースがなります[CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)します。

`IDispEventImpl`と`IDispEventSimpleImpl`クラスでは、cookie を管理できます。

## <a name="see-also"></a>関連項目

[イベント処理](../atl/event-handling-and-atl.md)

