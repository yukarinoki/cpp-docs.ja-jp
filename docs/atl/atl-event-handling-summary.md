---
title: ATL イベントの処理の概要 |Microsoft Docs
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
ms.openlocfilehash: 743939683d212de529816a165907e12063df03be
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027194"
---
# <a name="atl-event-handling-summary"></a>ATL イベント処理の概要
一般に、COM イベントの処理は、比較的単純なプロセスです。 次の 3 つの主な手順があります。  
  
-   オブジェクトには、イベント インターフェイスを実装します。  
  
-   オブジェクトがイベントを受信することは、イベント ソースにお勧めします。  
  
-   オブジェクトが不要になったイベントを受信する必要がある場合は、イベント ソースをアドバイズです。  
  
## <a name="implementing-the-interface"></a>インターフェイスの実装  
 ATL を使用してインターフェイスを実装するには、主に 4 つの方法があります。  
  
|を派生します。|インターフェイスの種類に適した|すべてのメソッド * を実装する必要があります。|実行時にタイプ ライブラリが必要です。|  
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|  
|インターフェイス|Vtable|[はい]|いいえ|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|デュアル|[はい]|[はい]|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|ディスパッチ インターフェイス|いいえ|[はい]|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|ディスパッチ インターフェイス|いいえ|いいえ|  
  
 \* 実装に必要なことはありません ATL サポート クラスを使用する場合、`IUnknown`または`IDispatch`メソッド手動でします。  
  
## <a name="advising-and-unadvising-the-event-source"></a>通知のイベント ソースをアドバイズと  
 ATL を使用してイベント ソースをアドバイズと 3 つの主な方法はあります。  
  
|アドバイズ関数|アドバイズ関数|使用するために最も適した|クッキーを追跡する必要があります。|コメント|  
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise)、 [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable またはデュアル インターフェイス|[はい]|`AtlAdvise` グローバル ATL 関数です。 `CComPtrBase::Advise` 使って[CComPtr](../atl/reference/ccomptr-class.md)と[CComQIPtr](../atl/reference/ccomqiptr-class.md)します。|  
|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)または[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|いいえ|少ないパラメーター`AtlAdvise`のためより多くの作業には、基本クラス。|  
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|複合コントロールの ActiveX コントロール|いいえ|`CComCompositeControl::AdviseSinkMap` すべてのエントリは、イベント シンク マップが表示されます。 同じ関数では、エントリをアドバイズです。 このメソッドはによって自動的に呼び出されます、`CComCompositeControl`クラス。|  
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|ダイアログ ボックスでの ActiveX コントロール|いいえ|`CAxDialogImpl::AdviseSinkMap` アドバイスし、アドバイズ ダイアログ リソース内のすべての ActiveX コントロール。 これが自動的に実行されます。|  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)   
 [IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)

