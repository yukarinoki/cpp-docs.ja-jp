---
title: データ ソース オブジェクト インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e1e64d5f41950492c3c7076160e6d134f7eb62cf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099650"
---
# <a name="data-source-object-interfaces"></a>データ ソース オブジェクト インターフェイス

次の表では、データ ソース オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|必須|はい|  
|`IDBInitialize`|必須|はい|  
|`IDBProperties`|必須|はい|  
|[IPersist](/windows/desktop/api/objidl/nn-objidl-ipersist)|必須|はい|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|いいえ|  
|`IDBDataSourceAdmin`|Optional|いいえ|  
|`IDBInfo`|Optional|いいえ|  
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Optional|いいえ|  
|`ISupportErrorInfo`|Optional|いいえ|  
  
データ ソース オブジェクトの実装、 `IDBProperties`、 `IDBInitialize`、および`IDBCreateSession`インターフェイス継承を使用します。 継承するか、これらの実装クラスのいずれかから継承せず、追加の機能をサポートするために選択できます。 サポートする場合、`IDBDataSourceAdmin`インターフェイスから継承する必要があります、`IDBDataSourceAdminImpl`クラス。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)