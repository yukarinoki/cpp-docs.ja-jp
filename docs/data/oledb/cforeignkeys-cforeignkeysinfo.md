---
title: CForeignKeys、CForeignKeysInfo |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_nOrdinal
- m_szPKColumnName
- FK_TABLE_NAME
- m_guidFKColumn
- FK_COLUMN_NAME
- m_guidPKColumn
- DELETE_RULE
- m_szPKTableSchema
- FK_COLUMN_PROPID
- m_nFKColumnPropID
- m_szFKTableCatalog
- CForeignKeysInfo
- FK_TABLE_SCHEMA
- m_szPKTableCatalog
- m_szDeleteRule
- m_szUpdateRule
- m_szPKTableName
- m_szFKTableSchema
- ORDINAL
- m_nPKColumnPropID
- m_szFKColumnName
- FK_TABLE_CATALOG
- FK_COLUMN_GUID
- m_szFKTableName
- CForeignKeys
dev_langs:
- C++
helpviewer_keywords:
- m_szPKTableCatalog
- FK_COLUMN_GUID
- m_szPKColumnName
- m_szFKTableName
- ORDINAL data member
- m_nPKColumnPropID
- m_szDeleteRule
- DELETE_RULE
- m_guidFKColumn
- FK_COLUMN_PROPID
- m_szPKTableSchema
- m_szFKTableCatalog
- CForeignKeysInfo parameter class
- m_szFKTableSchema
- FK_TABLE_SCHEMA
- FK_COLUMN_NAME
- m_szUpdateRule
- m_szFKColumnName
- FK_TABLE_CATALOG
- m_nOrdinal
- m_szPKTableName
- CForeignKeys typedef class
- m_nFKColumnPropID
- m_guidPKColumn
- FK_TABLE_NAME
ms.assetid: 1c401a4a-0827-4255-9214-bc893e1cd79d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e15b4a855375161f15ff9fa872a700f93b817a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098334"
---
# <a name="cforeignkeys-cforeignkeysinfo"></a>CForeignKeys、CForeignKeysInfo
Typedef クラスを呼び出す**CForeignKeys**そのパラメーター クラスを実装する**CForeignKeysInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、特定のユーザーによってカタログで定義されている外部キー列を識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[FOREIGN_KEYS 行セット](https://msdn.microsoft.com/en-us/library/ms711276.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szPKTableCatalog|PK_TABLE_CATALOG|  
|m_szPKTableSchema|PK_TABLE_SCHEMA|  
|m_szPKTableName|PK_TABLE_NAME|  
|m_szPKColumnName|PK_COLUMN_NAME|  
|m_guidPKColumn|PK_COLUMN_GUID|  
|m_nPKColumnPropID|PK_COLUMN_PROPID|  
|m_szFKTableCatalog|FK_TABLE_CATALOG|  
|m_szFKTableSchema|FK_TABLE_SCHEMA|  
|m_szFKTableName|FK_TABLE_NAME|  
|m_szFKColumnName|FK_COLUMN_NAME|  
|m_guidFKColumn|FK_COLUMN_GUID|  
|m_nFKColumnPropID|FK_COLUMN_PROPID|  
|m_nOrdinal|序数|  
|m_szUpdateRule|UPDATE_RULE|  
|m_szDeleteRule|DELETE_RULE|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>関連項目  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)