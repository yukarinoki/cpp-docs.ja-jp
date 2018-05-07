---
title: Cdynamicaccessor::getbookmark |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
dev_langs:
- C++
helpviewer_keywords:
- GetBookmark method
ms.assetid: 6d0a2970-0c62-4a34-bac7-149d8e990f81
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ac9ea217b987f7355757fc756acc0108fca0e4a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetbookmark"></a>CDynamicAccessor::GetBookmark
現在の行のブックマークを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pBookmark`  
 [out]ポインター、 [CBookmark](../../data/oledb/cbookmark-class.md)オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
## <a name="remarks"></a>コメント  
 設定する必要があります**DBPROP_IRowsetLocate**に`VARIANT_TRUE`ブックマークを取得します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)