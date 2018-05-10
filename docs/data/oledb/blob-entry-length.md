---
title: BLOB_ENTRY_LENGTH |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BLOB_ENTRY_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY_LENGTH macro
ms.assetid: 832d21ab-5fdd-49ad-af6e-4fca5722ec93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5f76f88d319f0fe06cd109af2095cfe0a4bb7204
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="blobentrylength"></a>BLOB_ENTRY_LENGTH
と共に使用`BEGIN_COLUMN_MAP`と`END_COLUMN_MAP`バイナリ ラージ オブジェクトをバインドする ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx))。 ような[BLOB_ENTRY](../../data/oledb/blob-entry.md)も、このマクロは、BLOB 列のバイト単位の長さを取得する点を除いて、します。  
  
## <a name="syntax"></a>構文  
  
```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nOrdinal`  
 [in]列番号。  
  
 *IID*  
 [in]インターフェイスの GUID、よう**IDD_ISequentialStream**BLOB を取得するために使用します。  
  
 `flags`  
 [in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグを設定 (たとえば、 **STGM_READ**)。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
 *length*  
 [out]BLOB 列の (実際) の長さ (バイト単位)。  
  
## <a name="example"></a>例  
 参照してください[BLOB を取得する方法ですか?](../../data/oledb/retrieving-a-blob.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)