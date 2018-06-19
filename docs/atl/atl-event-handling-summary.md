---
title: ATL イベント処理の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a938bd072ea8df30e64cce28fbf0709f08547d28
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356523"
---
# <a name="atl-event-handling-summary"></a>ATL イベント処理の概要
一般に、COM イベントの処理は、比較的単純なプロセスです。 次の 3 つの主要なステップがあります。  
  
-   オブジェクトのイベント インターフェイスを実装します。  
  
-   オブジェクトがイベントを受信することは、イベント ソースにお勧めします。  
  
-   オブジェクトが不要になったイベントを受信する必要がある場合は、イベント ソースをアドバイズです。  
  
## <a name="implementing-the-interface"></a>インターフェイスの実装  
 ATL を使用してインターフェイスを実装するには、主に 4 つの方法があります。  
  
|を派生します。|インターフェイスの種類に適した|すべてのメソッド * を実装する必要があります。|実行時にタイプ ライブラリが必要です。|  
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|  
|インターフェイス|Vtable|[はい]|×|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|デュアル|[はい]|[はい]|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|ディスパッチ インターフェイス|×|[はい]|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|ディスパッチ インターフェイス|×|×|  
  
 \* 実装に必要なことはありません ATL サポート クラスを使用する場合、 **IUnknown**または`IDispatch`メソッド手動でします。  
  
## <a name="advising-and-unadvising-the-event-source"></a>通知のイベント ソースをアドバイズと  
 ATL を使用してイベント ソースをアドバイズと 3 つの主な方法します。  
  
|アドバイズ関数|アドバイズ関数|使用する場合に最も適して|クッキーを追跡する必要があります。|コメント|  
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|  

|[AtlAdvise](reference/connection-point-global-functions.md#atladvise)、 [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable またはデュアル インターフェイス |[はい] |`AtlAdvise`グローバル ATL 関数です。 `CComPtrBase::Advise` によって使用される[CComPtr](../atl/reference/ccomptr-class.md)と[CComQIPtr](../atl/reference/ccomqiptr-class.md)|。  

|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)または[されます](../atl/reference/idispeventsimpleimpl-class.md)|いいえ |少ないパラメーター`AtlAdvise`のでより多くの作業は、基本クラスです |。  
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|複合コントロールでの ActiveX コントロール |いいえ |`CComCompositeControl::AdviseSinkMap`イベント シンク マップのすべてのエントリが示されます。 同じ関数では、エントリをアドバイズです。 このメソッドはによって自動的に、`CComCompositeControl`クラスです |。  
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|ダイアログ ボックスでの ActiveX コントロール |いいえ |`CAxDialogImpl::AdviseSinkMap`アドバイスを提供し、ダイアログ リソース内のすべての ActiveX コントロールをアドバイズです。 これは、自動的にする |。  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)   
 [IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)

