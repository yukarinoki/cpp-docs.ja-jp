---
title: トランザクション オブジェクト インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 758208de2ee27dba64808c60b1d94bed5bdeafa4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194575"
---
# <a name="transaction-object-interfaces"></a>トランザクション オブジェクト インターフェイス
トランザクション オブジェクトは、データ ソース上の作業のアトミック単位を定義し、それらの作業単位が相互に関連付ける方法を決定します。 このオブジェクトは、OLE DB プロバイダー テンプレートによって直接サポートされていません (つまり、独自のオブジェクトを作成する必要があります)。  
  
 次の表では、トランザクション オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|必須|いいえ|  
|[ITransaction](/previous-versions/windows/desktop/ms723053\(v=vs.85\))|必須|いいえ|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816\(v=vs.85\))|Optional|いいえ|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)