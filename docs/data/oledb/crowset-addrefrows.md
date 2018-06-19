---
title: Crowset::addrefrows |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>.AddRefRows
- CRowset.AddRefRows
- ATL.CRowset.AddRefRows
- AddRefRows
- CRowset::AddRefRows
- CRowset<TAccessor>::AddRefRows
- ATL::CRowset::AddRefRows
- ATL.CRowset<TAccessor>.AddRefRows
- ATL::CRowset<TAccessor>::AddRefRows
dev_langs:
- C++
helpviewer_keywords:
- AddRefRows method
ms.assetid: 590b5a24-870f-4c42-b0c8-28491f368a82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f41a33523f30776109624982b9de1a57d4d9227b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096653"
---
# <a name="crowsetaddrefrows"></a>CRowset::AddRefRows
呼び出し[IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) (を 1 つ)、参照カウントをインクリメントする現在の行ハンドルに関連付けられています。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT AddRefRows() throw();  
  
```  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、現在の行ハンドルの参照カウントをインクリメントします。 呼び出す[ReleaseRows](../../data/oledb/crowset-releaserows.md)カウントをデクリメントします。 Move メソッドによって返される行では、1 つの参照カウントがあります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [CRowset::ReleaseRows](../../data/oledb/crowset-releaserows.md)