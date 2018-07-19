---
title: Irowsetupdateimpl::isupdateallowed |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/25/2018
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
ms.openlocfilehash: 363626cedddea3da57e829a43c21c63b5c2b05cd
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122005"
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
セキュリティ、更新後に、整合性を確認するには、このメソッドをオーバーライドします。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *status*  
 [in]保留中の行の操作の状態。  
  
 *hRowUpdate*  
 [in]ユーザーが更新する行のハンドルです。  
  
 *pRowStatus*  
 [out]ユーザーに、状態が返されます。  
  
## <a name="remarks"></a>Remarks  
 更新プログラムを許可する必要があると判断した場合を返します`S_OK`以外を返しますそれ以外の場合**E_FAIL**です。 設定する必要がある更新を許可する場合、 **DBROWSTATUS**で[irowsetupdateimpl::update](../../data/oledb/irowsetupdateimpl-update.md)に適切な[状態の行](https://msdn.microsoft.com/en-us/library/ms722752.aspx)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)