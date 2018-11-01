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
ms.openlocfilehash: af67edca97cbfd644668ed48b3145cdbc38636a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564321"
---
# <a name="transaction-object-interfaces"></a>トランザクション オブジェクト インターフェイス

トランザクション オブジェクトは、データ ソース上の作業のアトミック単位を定義し、それらの作業単位が相互に関連付ける方法を決定します。 このオブジェクトは、OLE DB プロバイダー テンプレートによって直接サポートされていません (つまり、独自のオブジェクトを作成する必要があります)。

次の表では、トランザクション オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。

|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|必須|いいえ|
|[ITransaction](/previous-versions/windows/desktop/ms723053)|必須|いいえ|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|いいえ|

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
