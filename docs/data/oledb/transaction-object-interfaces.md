---
description: 詳細については、「トランザクションオブジェクトインターフェイス」を参照してください。
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
ms.openlocfilehash: bc8eec6ca5a962e825eafa12255d8a47a8a463f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272644"
---
# <a name="transaction-object-interfaces"></a>トランザクション オブジェクト インターフェイス

トランザクションオブジェクトは、データソースのアトミックな作業単位を定義し、それらの作業単位が相互にどのように関連しているかを決定します。 このオブジェクトは、OLE DB プロバイダーテンプレートによって直接サポートされていません (つまり、独自のオブジェクトを作成する必要があります)。

次の表は、トランザクションオブジェクトの OLE DB によって定義される必須のインターフェイスと省略可能なインターフェイスを示しています。

|インターフェイス|必須|OLE DB テンプレートによって実装されますか?|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Mandatory|いいえ|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Mandatory|いいえ|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|省略可能|いいえ|

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
