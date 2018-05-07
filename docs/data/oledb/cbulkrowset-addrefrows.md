---
title: Cbulkrowset::addrefrows |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset::AddRefRows
- AddRefRows
- CBulkRowset.AddRefRows
- ATL.CBulkRowset<TAccessor>.AddRefRows
- ATL::CBulkRowset::AddRefRows
- CBulkRowset<TAccessor>::AddRefRows
- ATL.CBulkRowset.AddRefRows
- ATL::CBulkRowset<TAccessor>::AddRefRows
dev_langs:
- C++
helpviewer_keywords:
- AddRefRows method
ms.assetid: 014be991-50f8-4377-ba16-fec80b54b406
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3b173bc037bd1fa5f74e59950e093457b381570c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cbulkrowsetaddrefrows"></a>CBulkRowset::AddRefRows
呼び出し[IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) bulk 行セットから取得した現在のすべての行の参照カウントをインクリメントします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddRefRows() throw();  
  
```  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CBulkRowset クラス](../../data/oledb/cbulkrowset-class.md)   
 [CBulkRowset::ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)