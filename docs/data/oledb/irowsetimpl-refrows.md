---
title: Irowsetimpl::refrows |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
dev_langs:
- C++
helpviewer_keywords:
- RefRows method
ms.assetid: 1c048a2a-65dc-4bba-9c81-a23c0dc249c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9aa841444f9cfa2758e8d5a8d8d4ec831a531d6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101553"
---
# <a name="irowsetimplrefrows"></a>IRowsetImpl::RefRows
によって呼び出されます[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)と[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)をインクリメントするか、参照カウントを既存の行ハンドルを解放します。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT RefRows(DBCOUNTITEM cRows,  
   const HROWrghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)   
 [CSimpleRow クラス](../../data/oledb/csimplerow-class.md)