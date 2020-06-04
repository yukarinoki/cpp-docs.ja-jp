---
title: トランザクション オブジェクト インターフェイス
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
ms.openlocfilehash: b86064c162dcacfbbc5877614c63d92d0f2bd347
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544532"
---
# <a name="transaction-object-interfaces"></a>トランザクション オブジェクト インターフェイス

トランザクションオブジェクトは、データソースのアトミックな作業単位を定義し、それらの作業単位が相互にどのように関連しているかを決定します。 このオブジェクトは、OLE DB プロバイダーテンプレートによって直接サポートされていません (つまり、独自のオブジェクトを作成する必要があります)。

次の表は、トランザクションオブジェクトの OLE DB によって定義される必須のインターフェイスと省略可能なインターフェイスを示しています。

|インターフェイス|必須|OLE DB テンプレートによって実装されますか?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Mandatory|いいえ|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Mandatory|いいえ|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|［オプション］|いいえ|

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
