---
title: Cdbpropset::setguid |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 140bc76968780efff826ccc42343f27b2cd2eae6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094001"
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
セット、**コンス トラクターは**フィールドで、 **DBPROPSET**構造体。  
  
## <a name="syntax"></a>構文  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]設定に使用される GUID、**コンス トラクターは**のフィールド、 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)構造体。  
  
## <a name="remarks"></a>コメント  
 このフィールドを設定することができます、[コンス トラクター](../../data/oledb/cdbpropset-cdbpropset.md)もします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDBPropSet クラス](../../data/oledb/cdbpropset-class.md)