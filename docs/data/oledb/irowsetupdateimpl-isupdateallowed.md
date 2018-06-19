---
title: Irowsetupdateimpl::isupdateallowed |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs:
- C++
helpviewer_keywords:
- IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3d39c726e4131b17d1dbdd76418e6da7985e4404
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105349"
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
セキュリティ、更新後に、整合性を確認するには、このメソッドをオーバーライドします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *status*  
 [in]保留中の行の操作の状態。  
  
 *hRowUpdate*  
 [in]ユーザーが更新する行のハンドルです。  
  
 *pRowStatus*  
 [out]ユーザーに、状態が返されます。  
  
## <a name="remarks"></a>コメント  
 更新プログラムを許可する必要があると判断した場合を返します`S_OK`以外を返しますそれ以外の場合**E_FAIL**です。 設定する必要がある更新を許可する場合、 **DBROWSTATUS**で[irowsetupdateimpl::update](../../data/oledb/irowsetupdateimpl-update.md)に適切な[状態の行](https://msdn.microsoft.com/en-us/library/ms722752.aspx)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)