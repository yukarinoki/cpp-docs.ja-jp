---
title: COLUMN_ENTRY |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY macro
ms.assetid: a10aef29-6d70-49ec-b572-5b5c4abe1b46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d2f1466b660d3235f3fffe5b7eed9aa80696d7c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="columnentry"></a>COLUMN_ENTRY
行セットの特定の列を行セットのバインドを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
COLUMN_ENTRY(nOrdinal, data)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 `nOrdinal`  
 [in]列番号。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
## <a name="remarks"></a>コメント  
 `COLUMN_ENTRY`マクロは、次の場所で使用します。  
  
-   間、 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)と[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロです。  
  
-   間、 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)と[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロです。  
  
-   間、 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)と[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロです。  
  
## <a name="example"></a>例  
 マクロのトピックで例を参照して[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)と[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [COLUMN_ENTRY_TYPE](../../data/oledb/column-entry-type.md)   
 [COLUMN_ENTRY_TYPE_SIZE](../../data/oledb/column-entry-type-size.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)