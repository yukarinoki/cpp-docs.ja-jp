---
title: BEGIN_PROPSET_MAP |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BEGIN_PROPSET_MAP
dev_langs:
- C++
helpviewer_keywords:
- BEGIN_PROPSET_MAP macro
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5b1596797672c0fff92531ff90f67b94bfd6101e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="beginpropsetmap"></a>BEGIN_PROPSET_MAP
プロパティのセットのマップ エントリを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
BEGIN_PROPSET_MAP(Class)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *クラス*  
 [in]このプロパティが設定されているクラスを指定します。 プロパティ セットは、次の OLE DB オブジェクトに指定できます。  
  
-   [データ ソース オブジェクト](https://msdn.microsoft.com/en-us/library/ms721278.aspx)  
  
-   [セッション オブジェクト](https://msdn.microsoft.com/en-us/library/ms711572.aspx)  
  
-   [コマンド](https://msdn.microsoft.com/en-us/library/ms724608.aspx)  
  
## <a name="example"></a>例  
 プロパティ セット マップのコード例を次に示します。  
  
 [!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)