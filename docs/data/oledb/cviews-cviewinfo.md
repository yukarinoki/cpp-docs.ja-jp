---
title: CViews、CViewInfo |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szTableSchema
- m_bCheckOption
- CViews
- CHECK_OPTION
- CViewInfo
- m_szTableCatalog
- IS_UPDATABLE
- m_szDefinition
- m_szTableName
- m_bIsUpdatable
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- CHECK_OPTION
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- m_bCheckOption
- TABLE_SCHEMA
- m_szTableCatalog
- m_szDescription
- m_szDefinition
- m_szTableName
- CViewInfo parameter class
- m_bIsUpdatable
- IS_UPDATABLE
- CViews typedef class
ms.assetid: ad864181-4fab-4919-b0fd-45df5da230d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b17df30dac07222f026f23f778a201cc5824d72a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cviews-cviewinfo"></a>CViews、CViewInfo
Typedef クラスを呼び出す**CViews**そのパラメーター クラスを実装する**CViewInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、カタログで定義されているテーブルを表示し、特定のユーザーによって所有されているが依存しているにで、テーブルに識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[ビューの行セット](https://msdn.microsoft.com/en-us/library/ms723122.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szDefinition|VIEW_DEFINITION|  
|m_bCheckOption|CHECK_OPTION|  
|m_bIsUpdatable|IS_UPDATABLE|  
|m_szDescription|説明|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>関連項目  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)