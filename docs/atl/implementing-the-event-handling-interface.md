---
description: 詳細については、「イベント処理インターフェイスの実装」を参照してください。
title: イベント処理インターフェイスの実装
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: 109fbb1fbdd4f18d0eb4c295fbc08de2b7cc3a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152764"
---
# <a name="implementing-the-event-handling-interface"></a>イベント処理インターフェイスの実装

ATL を使用すると、イベントの処理に必要な3つの要素 (イベントインターフェイスの実装、イベントソースのアドバイズ、イベントソースの unadvising) をすべて使用できます。 実行する必要がある正確な手順は、イベントインターフェイスの種類と、アプリケーションのパフォーマンス要件によって異なります。

ATL を使用してインターフェイスを実装する最も一般的な方法は次のとおりです。

- カスタムインターフェイスから直接派生します。

- タイプライブラリに記述されているデュアルインターフェイスに対して [IDispatchImpl](../atl/reference/idispatchimpl-class.md) から派生します。

- タイプライブラリに記述されているディスパッチインターフェイスの [IDispEventImpl](../atl/reference/idispeventimpl-class.md) からの派生。

- タイプライブラリに記述されていないディスパッチインターフェイスの [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) からの派生、または実行時に型情報を読み込まないことによって効率を向上させる必要がある場合。

カスタムインターフェイスまたはデュアルインターフェイスを実装する場合は、 [AtlAdvise](reference/connection-point-global-functions.md#atladvise) または [CComPtrBase:: advise](../atl/reference/ccomptrbase-class.md#advise)を呼び出して、イベントソースをアドバイズする必要があります。 呼び出しによって返された cookie を自分で追跡する必要があります。 [Atlunadvise](reference/connection-point-global-functions.md#atlunadvise)を呼び出して、接続を切断します。

またはを使用してディスパッチインターフェイスを実装する場合は `IDispEventImpl` `IDispEventSimpleImpl` 、 [IDispEventSimpleImpl::D ispeventadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)を呼び出して、イベントソースをアドバイズする必要があります。 [IDispEventSimpleImpl::D ispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)を呼び出して接続を解除します。

を複合コントロールの基底クラスとして使用している場合は、 `IDispEventImpl` シンクマップに一覧表示されているイベントソースが、 [CComCompositeControl:: AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)を使用して自動的に通知されないようにします。

`IDispEventImpl`クラスと `IDispEventSimpleImpl` クラスは、cookie を管理します。

## <a name="see-also"></a>関連項目

[イベント処理](../atl/event-handling-and-atl.md)
