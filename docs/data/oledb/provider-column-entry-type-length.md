---
title: PROVIDER_COLUMN_ENTRY_TYPE_LENGTH |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_TYPE_LENGTH macro
ms.assetid: a60b1a8b-0903-4ff4-91ec-ed62126449fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ef9af591bff5a13a5780cc27ef169a8447c64cc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106610"
---
# <a name="providercolumnentrytypelength"></a>PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
プロバイダーでサポートされている特定の列を表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(name  
, ordinal, dbtype, size, member )  
```  
  
#### <a name="parameters"></a>パラメーター  
 *name*  
  
 [in]列の名前。  
  
 `ordinal`  
 [in]列番号。 列は、ブックマーク列でない限り、列番号は 0 をできません。  
  
 `dbtype`  
 [in]データ型[DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx)です。  
  
 `size`  
 [in]列のサイズ (バイト単位)。  
  
 `member`  
 [in]データを格納するデータ クラスにメンバー変数です。  
  
## <a name="remarks"></a>コメント  
 ような[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md)列のデータ型とサイズを指定することもできます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)