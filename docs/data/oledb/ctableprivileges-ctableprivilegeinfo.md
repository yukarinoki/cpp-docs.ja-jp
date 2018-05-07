---
title: CTablePrivileges、CTablePrivilegeInfo |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szCatalog
- m_bIsGrantable
- IS_GRANTABLE
- m_szType
- m_szSchema
- m_szGrantor
- GRANTOR
- GRANTEE
- CTablePrivileges
- CTablePrivilegeInfo
- m_szName
- m_szGrantee
dev_langs:
- C++
helpviewer_keywords:
- GRANTOR
- CTablePrivilegeInfo parameter class
- m_szSchema
- TABLE_CATALOG
- m_szType
- m_szCatalog
- TABLE_NAME
- IS_GRANTABLE
- TABLE_SCHEMA
- m_szName
- m_szGrantee
- CTablePrivileges typedef class
- m_szGrantor
- GRANTEE
- m_bIsGrantable
ms.assetid: ffcd6f73-022e-452a-8342-f2b9362d256b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3500bb764596410ca1540e69743e1e608936ac3c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ctableprivileges-ctableprivilegeinfo"></a>CTablePrivileges、CTablePrivilegeInfo
Typedef クラスを呼び出す**CTablePrivileges**そのパラメーター クラスを実装する**CTablePrivilegeInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、特定のユーザーにアクセス可能である、カタログで定義されているテーブルを識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[TABLE_PRIVILEGES 行セット](https://msdn.microsoft.com/en-us/library/ms725428.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szGrantor|GRANTOR|  
|m_szGrantee|GRANTEE|  
|m_szCatalog|TABLE_CATALOG|  
|m_szSchema|TABLE_SCHEMA|  
|m_szName|TABLE_NAME|  
|m_szType|PRIVILEGE_TYPE|  
|m_bIsGrantable|IS_GRANTABLE|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>関連項目  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)