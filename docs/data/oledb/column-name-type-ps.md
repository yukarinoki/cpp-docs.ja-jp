---
title: COLUMN_NAME_TYPE_PS |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_NAME_TYPE_PS
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME_TYPE_PS macro
ms.assetid: 99df7e33-47fc-48ec-ad03-5fd03a190aa9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 967a43d16de1914ad03b24bd83edf5233f5950b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="columnnametypeps"></a>COLUMN_NAME_TYPE_PS
行セットの特定の列を行セットのバインドを表します。 ような[COLUMN_NAME](../../data/oledb/column-name.md)ただし、このマクロは、データ型、有効桁数、およびスケールにも受け取ります。  
  
## <a name="syntax"></a>構文  
  
```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszName`  
 [in]列の名前へのポインター。 名前は、Unicode 文字列にする必要があります。 たとえば、名前の前に 'L' を設定することによってこれを実行できます:`L"MyColumn"`です。  
  
 `wType`  
 [in]データ型。  
  
 `nPrecision`  
 [in]データを取得するときに使用する最大有効桁数と`wType`は`DBTYPE_NUMERIC`します。 それ以外の場合、このパラメーターは無視されます。  
  
 `nScale`  
 [in]データを取得するときに使用する小数点以下桁数と`wType`は`DBTYPE_NUMERIC`または**DBTYPE_DECIMAL**です。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
## <a name="remarks"></a>コメント  
 参照してください[COLUMN_NAME](../../data/oledb/column-name.md)場所について、 **COLUMN_NAME_\*** マクロを使用します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)