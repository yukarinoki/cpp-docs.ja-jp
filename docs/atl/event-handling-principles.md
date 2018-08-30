---
title: イベント処理の原則 (ATL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 065c7296982bc715d35431a441be5b0e8506e1fd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197304"
---
# <a name="event-handling-principles"></a>イベント処理の原則
3 つの手順はすべてのイベント処理に共通します。 必要があります。  
  
-   オブジェクトには、イベント インターフェイスを実装します。  
  
-   オブジェクトがイベントを受信することは、イベント ソースにお勧めします。  
  
-   オブジェクトが不要になったイベントを受信する必要がある場合は、イベント ソースをアドバイズです。  
  
 イベント インターフェイスを実装することをする方法は、その型によって異なります。 イベント インターフェイス vtable、デュアルまたはディスパッチ インターフェイスを使用できます。 インターフェイスを定義するイベント ソースのデザイナーにはそのインターフェイスを実装するためです。  
  
> [!NOTE]
>  イベント インターフェイスを二重にすることはできませんが、技術的な理由はありませんは、さまざまなデュアルの使用を回避するために適切な設計上の理由があります。 ただし、これは、イベントのデザイナー/実装者によって行われた決定*ソース*します。 イベントの観点から作業しているため`sink`、デュアル イベント インターフェイスを実装するが、任意の選択肢がないことの可能性を考慮する必要があります。 デュアル インターフェイスの詳細については、次を参照してください。[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)します。  
  
 イベント ソースを通知するのに分けることが 3 つの手順。  
  
-   クエリのソース オブジェクトは[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)します。  
  
-   呼び出す[IConnectionPointContainer::FindConnectionPoint](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint)興味イベント インターフェイスの IID を渡します。 かどうか、正常に返されます、 [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint)コネクション ポイント オブジェクトのインターフェイス。  
  
-   呼び出す[iconnectionpoint::advise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-advise)を渡す、`IUnknown`イベント シンクの。 かどうか、正常に返されます、`DWORD`接続を表すクッキー。  
  
 イベントの受信にご関心を正常に登録した後は、ソース オブジェクトによって発生したイベントに従ってオブジェクトのイベント インターフェイスでメソッドが呼び出されます。 イベントを受信するが不要になったときに経由で接続ポイントに cookie を渡すことができます[:unadvise](/windows/desktop/api/ocidl/nf-ocidl-iconnectionpoint-unadvise)します。 これにより、ソースとシンク間の接続が中断されます。  
  
 参照しないように注意するイベントを処理するときのサイクルです。  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)

