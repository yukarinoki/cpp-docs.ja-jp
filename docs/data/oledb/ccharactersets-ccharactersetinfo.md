---
title: CCharacterSets、CCharacterSetInfo |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szCollateName
- m_szCatalog
- DEFAULT_COLLATE_NAME
- m_szCollateSchema
- FORM_OF_USE
- DEFAULT_COLLATE_SCHEMA
- m_szCollateCatalog
- CCharacterSets
- CHARACTER_SET_NAME
- DEFAULT_COLLATE_CATALOG
- CHARACTER_SET_SCHEMA
- m_szFormOfUse
- NUMBER_OF_CHARACTERS
- m_szSchema
- CHARACTER_SET_CATALOG
- CCharacterSetInfo
- m_nNumCharacters
- m_szName
dev_langs:
- C++
helpviewer_keywords:
- DEFAULT_COLLATE_SCHEMA
- m_nNumCharacters
- m_szSchema
- NUMBER_OF_CHARACTERS
- m_szCollateCatalog
- CCharacterSetInfo parameter class
- m_szCatalog
- CCharacterSets typedef class
- m_szCollateName
- m_szName
- m_szCollateSchema
- FORM_OF_USE OLE DB column
- CHARACTER_SET_NAME
- DEFAULT_COLLATE_CATALOG
- DEFAULT_COLLATE_NAME
- m_szFormOfUse
- CHARACTER_SET_SCHEMA
- CHARACTER_SET_CATALOG
ms.assetid: 029d068c-8bb2-4fc0-8709-78ce7f74446e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e46c61df81a9a527fa637c96c37324319bbe5cf5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094444"
---
# <a name="ccharactersets-ccharactersetinfo"></a>CCharacterSets、CCharacterSetInfo
Typedef クラスを呼び出す**CCharacterSets**そのパラメーター クラスを実装する**CCharacterSetInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、特定のユーザーにアクセス可能である、カタログで定義されている文字セットを識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[CHARACTER_SETS 行セット](https://msdn.microsoft.com/en-us/library/ms722638.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szCatalog|CHARACTER_SET_CATALOG|  
|m_szSchema|CHARACTER_SET_SCHEMA|  
|m_szName|CHARACTER_SET_NAME|  
|m_szFormOfUse|FORM_OF_USE|  
|m_nNumCharacters|NUMBER_OF_CHARACTERS|  
|m_szCollateCatalog|DEFAULT_COLLATE_CATALOG|  
|m_szCollateSchema|DEFAULT_COLLATE_SCHEMA|  
|m_szCollateName|DEFAULT_COLLATE_NAME|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>関連項目  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)