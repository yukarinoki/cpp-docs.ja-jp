---
title: Irowsetimpl::getdbstatus |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- GetDBStatus method
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ebebbc2d1392e4f3c863ce366e8d19cfad3b7162
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplgetdbstatus"></a>IRowsetImpl::GetDBStatus
返します、`DBSTATUS`指定したフィールドの状態フラグ。  
  
## <a name="syntax"></a>構文  
  
```cpp
      virtual DBSTATUS GetDBStatus(RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `currentRow`  
 現在の行。  
  
 [入力] `columnNames`  
 状態が要求されて列です。  
  
## <a name="return-value"></a>戻り値  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx)列のフラグ。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)