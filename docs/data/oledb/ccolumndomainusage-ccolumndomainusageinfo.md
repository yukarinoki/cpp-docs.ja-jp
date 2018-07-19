---
title: CColumnDomainUsage、CColumnDomainUsageInfo |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_szCatalog
- m_nColumnPropID
- CColumnDomainUsageInfo
- COLUMN_GUID
- DOMAIN_NAME
- m_szColumnName
- DOMAIN_SCHEMA
- DOMAIN_CATALOG
- m_szTableCatalog
- m_szSchema
- COLUMN_PROPID
- m_guidColumn
- CColumnDomainUsage
- m_szTableName
- m_szName
- COLUMN_DOMAIN_USAGE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szSchema
- DOMAIN_NAME
- DOMAIN_SCHEMA
- m_szTableSchema
- TABLE_CATALOG
- m_szCatalog
- TABLE_NAME
- m_nColumnPropID
- CColumnDomainUsageInfo parameter class
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szName
- m_szTableCatalog
- m_szTableName
- COLUMN_DOMAIN_USAGE
- COLUMN_GUID
- CColumnDomainUsage typedef class
- m_guidColumn
- DOMAIN_CATALOG
ms.assetid: 5ff331f1-b99c-4002-9e04-367708c5759f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0ca95cadf5ac3502ba8de034fad91a75ba123f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095272"
---
# <a name="ccolumndomainusage-ccolumndomainusageinfo"></a>CColumnDomainUsage、CColumnDomainUsageInfo
Typedef クラスを呼び出す**CColumnDomainUsage**そのパラメーター クラスを実装する**CColumnDomainUsageInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、カタログで定義されているし、特定のユーザーが所有するドメインに依存する列、カタログで定義されているを識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[COLUMN_DOMAIN_USAGE 行セット](https://msdn.microsoft.com/en-us/library/ms711240.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szCatalog|DOMAIN_CATALOG|  
|m_szSchema|DOMAIN_SCHEMA|  
|m_szName|DOMAIN_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>関連項目  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)