---
description: 詳細については、「ATL イベント処理の概要」を参照してください。
title: ATL イベント処理の概要
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
ms.openlocfilehash: c041de6cbd0e0852d5ce0e51d892c21c7d9a23d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148656"
---
# <a name="atl-event-handling-summary"></a>ATL イベント処理の概要

一般に、COM イベントの処理は比較的単純なプロセスです。 主な手順が 3 つあります。

- オブジェクトにイベントインターフェイスを実装します。

- オブジェクトがイベントを受け取る必要があることをイベントソースに通知します。

- オブジェクトがイベントを受け取る必要がなくなったときに、イベントソースのアドバイズを解除します。

## <a name="implementing-the-interface"></a>インターフェイスの実装

ATL を使用してインターフェイスを実装する主な方法は4つあります。

| から派生する|インターフェイス型に適しています|すべてのメソッドを実装する必要があります *|実行時にタイプライブラリが必要|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|インターフェイス|Vtable|はい|いいえ|
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|デュアル|はい|はい|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|ディスパッチ インターフェイス|いいえ|はい|
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|ディスパッチ インターフェイス|いいえ|いいえ|

\* ATL サポートクラスを使用する場合、 `IUnknown` メソッドまたはメソッドを手動で実装する必要はありません `IDispatch` 。

## <a name="advising-and-unadvising-the-event-source"></a>イベントソースのアドバイズと Unadvising

ATL を使用してイベントソースをアドバイズおよび unadvising するには、主に3つの方法があります。

|Advise 関数|アドバイズ中止関数|での使用に最も適しています。|Cookie を追跡する必要があります|説明|
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise)、 [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable またはデュアルインターフェイス|はい|`AtlAdvise` は、グローバル ATL 関数です。 `CComPtrBase::Advise`[CComPtr](../atl/reference/ccomptr-class.md)と[CComQIPtr](../atl/reference/ccomqiptr-class.md)によって使用されます。|
|[IDispEventSimpleImpl::D ispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::D ispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) または [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|いいえ|`AtlAdvise`基底クラスがより多くの作業を行うため、パラメーターが減少します。|
|[CComCompositeControl:: AdviseSinkMap (TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl:: AdviseSinkMap (FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|複合コントロールの ActiveX コントロール|いいえ|`CComCompositeControl::AdviseSinkMap` イベントシンクマップ内のすべてのエントリをアドバイズします。 同じ関数がエントリをアドバイズ解除します。 このメソッドは、クラスによって自動的に呼び出され `CComCompositeControl` ます。|
|[CAxDialogImpl:: AdviseSinkMap (TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl:: AdviseSinkMap (FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|ダイアログボックスの ActiveX コントロール|いいえ|`CAxDialogImpl::AdviseSinkMap` ダイアログリソース内のすべての ActiveX コントロールをアドバイズし、アドバイズを解除します。 これは自動的に行われます。|

## <a name="see-also"></a>関連項目

[イベント処理](../atl/event-handling-and-atl.md)<br/>
[IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)
