---
title: BEGIN_PROVIDER_COLUMN_MAP |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_PROVIDER_COLUMN_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_PROVIDER_COLUMN_MAP macro
ms.assetid: 506b8c0f-6be9-4c97-ba81-c4b7f7d428fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eff2aa003f81ed3fcf5ba9152bc17002be0a4db2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091947"
---
# <a name="beginprovidercolumnmap"></a>BEGIN_PROVIDER_COLUMN_MAP
プロバイダーの列マップ エントリの先頭をマークします。  
  
## <a name="syntax"></a>構文  
  
```cpp
BEGIN_PROVIDER_COLUMN_MAP(theClass)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]このマップが属するクラスの名前。  
  
## <a name="example"></a>例  
 プロバイダーの列マップのコード例を次に示します。  
  
 [!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)