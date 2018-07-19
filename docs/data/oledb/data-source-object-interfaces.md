---
title: データ ソース オブジェクト インターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 1c8aaed0a9f50e20dba5938b9b37425f4caa2bb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101878"
---
# <a name="data-source-object-interfaces"></a>データ ソース オブジェクト インターフェイス
次の表は、データ ソース オブジェクトの OLE DB で定義されている必須およびオプションのインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるか。|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|必須|[はい]|  
|`IDBInitialize`|必須|[はい]|  
|`IDBProperties`|必須|[はい]|  
|[IPersist](http://msdn.microsoft.com/library/windows/desktop/ms688695)|必須|[はい]|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|×|  
|`IDBDataSourceAdmin`|Optional|×|  
|`IDBInfo`|Optional|×|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Optional|×|  
|`ISupportErrorInfo`|Optional|×|  
  
 データ ソース オブジェクトを実装して、 `IDBProperties`、 `IDBInitialize`、および`IDBCreateSession`継承によってインターフェイスです。 継承、またはそのいずれかのこれらの実装クラスから継承せず、追加の機能をサポートするために選択できます。 サポートする場合、`IDBDataSourceAdmin`インターフェイスから継承する必要があります、`IDBDataSourceAdminImpl`クラスです。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)