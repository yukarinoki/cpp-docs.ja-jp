---
title: イベント処理の原則 (ATL) |Microsoft ドキュメント
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
ms.openlocfilehash: cb7577dc7d9fb58f43ee67d5e5b8f00393dca1bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355449"
---
# <a name="event-handling-principles"></a>イベント処理の原則
3 つの手順はすべてのイベント処理に共通です。 する必要があります。  
  
-   オブジェクトのイベント インターフェイスを実装します。  
  
-   オブジェクトがイベントを受信することは、イベント ソースにお勧めします。  
  
-   オブジェクトが不要になったイベントを受信する必要がある場合は、イベント ソースをアドバイズです。  
  
 イベント インターフェイスを実装する方法は、その型によって異なります。 イベント インターフェイスには、vtable、デュアルまたはディスパッチ インターフェイスを指定できます。 インターフェイスを定義するイベント ソースのデザイナーには設定すると、そのインターフェイスを実装します。  
  
> [!NOTE]
>  イベント インターフェイスをデュアルにすることはできません技術的な理由はありませんが、デュアルの使用を回避する適切な設計上の理由の数があります。 ただし、この設定は、イベントのデザイナー/インプリメンタによって行われた*ソース*です。 イベントの観点から作業しているため`sink`、デュアルのイベント インターフェイスを実装するが、任意の選択肢がなくても発生する可能性を許可する必要があります。 デュアル インターフェイスの詳細については、次を参照してください。[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)です。  
  
 イベント ソースを通知するのに分けることが 3 つの手順。  
  
-   ソース オブジェクトをクエリ[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)です。  
  
-   呼び出す[IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476)興味イベント インターフェイスの IID を渡します。 かどうか、正常に返されます、 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)接続ポイント オブジェクトのインターフェイスです。  
  
-   呼び出す[iconnectionpoint::advise](http://msdn.microsoft.com/library/windows/desktop/ms678815)渡す、 **IUnknown**イベント シンクのです。 かどうか、正常に返されます、`DWORD`の接続を表すクッキー。  
  
 イベントの受信にご興味を正常に登録した後は、ソース オブジェクトによって発生したイベントに従ってオブジェクトのイベント インターフェイスのメソッドが呼び出されます。 不要になったイベントを受信する必要がある場合は、経由で接続ポイントに cookie を渡すことができます[IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608)です。 これにより、ソースとシンク間の接続が切断されます。  
  
 参照を回避するように注意するイベントを処理するときのサイクルです。  
  
## <a name="see-also"></a>関連項目  
 [イベント処理](../atl/event-handling-and-atl.md)

