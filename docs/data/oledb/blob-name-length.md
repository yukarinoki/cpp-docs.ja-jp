---
title: BLOB_NAME_LENGTH |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BLOB_NAME_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- BLOB_NAME_LENGTH macro
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a05c9539994827efb427eeb5b76645ac08f4e810
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092061"
---
# <a name="blobnamelength"></a>BLOB_NAME_LENGTH
と共に使用`BEGIN_COLUMN_MAP`と`END_COLUMN_MAP`バイナリ ラージ オブジェクトをバインドする ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx))。 ような[BLOB_NAME](../../data/oledb/blob-name.md)も、このマクロは、BLOB データの列のバイトの長さを取得する点を除いて、します。  
  
## <a name="syntax"></a>構文  
  
```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszName`  
 [in]列の名前へのポインター。 名前は、Unicode 文字列にする必要があります。 たとえば、名前の前に 'L' を設定することによってこれを実行できます:`L"MyColumn"`です。  
  
 *IID*  
 [in]インターフェイスの GUID、よう**IDD_ISequentialStream**BLOB を取得するために使用します。  
  
 `flags`  
 [in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグを設定 (たとえば、 **STGM_READ**)。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
 *length*  
 [out]BLOB 列の (実際) の長さ (バイト単位)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_NAME](../../data/oledb/blob-name.md)   
 [BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)