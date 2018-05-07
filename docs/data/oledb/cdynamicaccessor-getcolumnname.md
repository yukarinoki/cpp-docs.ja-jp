---
title: Cdynamicaccessor::getcolumnname |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
dev_langs:
- C++
helpviewer_keywords:
- GetColumnName method
ms.assetid: 96a7452a-1f5b-41e9-ab37-88dac026f961
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a3ad9a1830be94a2c0d3649bf72a6d25af1fb4e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetcolumnname"></a>CDynamicAccessor::GetColumnName
指定された列の名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
## <a name="return-value"></a>戻り値  
 指定された列の名前。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)