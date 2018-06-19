---
title: COLUMN_ENTRY_EX |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_EX
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_EX macro
ms.assetid: dfad1b67-51c3-4289-b89a-da42d7e8bb88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 843bb017bc575275c74f06f9bfc24973021f280b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098564"
---
# <a name="columnentryex"></a>COLUMN_ENTRY_EX
データベースの特定の列を行セットのバインドを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 `nOrdinal`  
 [in]列番号。  
  
 `wType`  
 [in]データ型。  
  
 `nLength`  
 [in]バイト単位でデータのサイズ。  
  
 `nPrecision`  
 [in]データを取得するときに使用する最大有効桁数と`wType`は`DBTYPE_NUMERIC`します。 それ以外の場合、このパラメーターは無視されます。  
  
 `nScale`  
 [in]データを取得するときに使用する小数点以下桁数と`wType`は`DBTYPE_NUMERIC`または**DBTYPE_DECIMAL**です。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
 *length*  
 [in]列の長さをバインドする変数です。  
  
 *status*  
 [in]列の状態にバインドする変数です。  
  
## <a name="remarks"></a>コメント  
 `COLUMN_ENTRY_EX`マクロは、次の場所で使用します。  
  
-   間、 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)と[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロです。  
  
-   間、 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)と[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロです。  
  
-   間、 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)と[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロです。  
  
## <a name="example"></a>例  
 参照してください[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)