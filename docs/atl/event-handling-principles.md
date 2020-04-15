---
title: イベント処理の原則 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
- event handling, advising event sources
- interfaces, event and event sink
- dual interfaces, event interfaces
- event handling, dual event interfaces
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
ms.openlocfilehash: 2e810853e7c81f279039e0b3dfda5199d38deee2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319566"
---
# <a name="event-handling-principles"></a>イベント処理の原則

すべてのイベント処理に共通する 3 つの手順があります。 次のことを行う必要があります。

- オブジェクトにイベント インターフェイスを実装します。

- オブジェクトがイベントを受信することをイベント ソースに通知します。

- オブジェクトがイベントを受信する必要がなくなった場合は、イベント ソースのアドバイスを解除します。

イベント インターフェイスを実装する方法は、その型によって異なります。 イベント インターフェイスは、vtable、デュアル、またはディスプ インターフェイスです。 インターフェイスを定義するのは、イベント ソースのデザイナーによって行われます。そのインターフェイスを実装するのはあなた次第です。

> [!NOTE]
> イベント インターフェイスがデュアルにできない技術的な理由はありませんが、デュアルを使用しないように設計上の優れた理由が多数あります。 ただし、これはイベント ソースのデザイナ/実装者による決定*です*。 イベント`sink`の観点から作業を行う場合は、デュアル イベント インターフェイスを実装する以外に選択肢がない可能性を考慮する必要があります。 デュアル インターフェイスの詳細については、[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)を参照してください。

イベント ソースへのアドバイスは、次の 3 つの手順に分けることができます。

- ソース オブジェクトに対[してクエリを実行します](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)。

- 興味[のある](/windows/win32/api/ocidl/nf-ocidl-iconnectionpointcontainer-findconnectionpoint)イベント インターフェイスの IID を渡して、次の値を呼び出します。 成功した場合、接続ポイント オブジェクトの[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)インターフェイスが返されます。

- イベント[IConnectionPoint::Advise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise)シンクのを渡す`IUnknown`アドバイスを呼び出します。 成功した場合、接続を`DWORD`表すクッキーが返されます。

イベントの受信に関心を登録すると、ソースオブジェクトによって発生したイベントに従って、オブジェクトのイベントインターフェイスのメソッドが呼び出されます。 イベントを受信する必要がなくなったら[、IConnectionPoint::Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise)を使用して、この Cookie をコネクション ポイントに戻すことができます。 これにより、ソースとシンクの間の接続が切断されます。

イベントを処理する際は、参照サイクルを避けるように注意してください。

## <a name="see-also"></a>関連項目

[イベント処理](../atl/event-handling-and-atl.md)
