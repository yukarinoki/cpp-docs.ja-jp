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
ms.openlocfilehash: 239ea94343652d379048bbeee87d2650d3f1ed72
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852537"
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
  
-   クエリのソース オブジェクトは[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)します。  
  
-   呼び出す[IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476)興味イベント インターフェイスの IID を渡します。 かどうか、正常に返されます、 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)コネクション ポイント オブジェクトのインターフェイス。  
  
-   呼び出す[iconnectionpoint::advise](http://msdn.microsoft.com/library/windows/desktop/ms678815)を渡す、`IUnknown`イベント シンクの。 かどうか、正常に返されます、`DWORD`接続を表すクッキー。  
  
 イベントの受信にご関心を正常に登録した後は、ソース オブジェクトによって発生したイベントに従ってオブジェクトのイベント インターフェイスでメソッドが呼び出されます。 イベントを受信するが不要になったときに経由で接続ポイントに cookie を渡すことができます[:unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608)します。 これにより、ソースとシンク間の接続が中断されます。  
  
 参照しないように注意するイベントを処理するときのサイクルです。  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)

