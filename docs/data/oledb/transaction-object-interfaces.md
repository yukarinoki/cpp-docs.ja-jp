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
ms.openlocfilehash: b2d84d9a072d3eeaa84246a6692487be5c71679c
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42575516"
---
# <a name="transaction-object-interfaces"></a>トランザクション オブジェクト インターフェイス
トランザクション オブジェクトは、データ ソース上の作業のアトミック単位を定義し、それらの作業単位が相互に関連付ける方法を決定します。 このオブジェクトは、OLE DB プロバイダー テンプレートによって直接サポートされていません (つまり、独自のオブジェクトを作成する必要があります)。  
  
 次の表では、トランザクション オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|  
|---------------|---------------|--------------------------------------|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|必須|いいえ|  
|[ITransaction](/previous-versions/windows/desktop/ms723053\(v=vs.85\))|必須|いいえ|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816\(v=vs.85\))|Optional|いいえ|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)