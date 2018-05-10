---
title: Irowsetupdateimpl::undo |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
dev_langs:
- C++
helpviewer_keywords:
- Undo method
ms.assetid: f3dc7764-050c-4322-9b2f-9ca772a0fb88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d98465d396084c157c40bdca41c3daac46bc4ad7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetupdateimplundo"></a>IRowsetUpdateImpl::Undo
最後のフェッチまたは更新以降、行への変更を元に戻します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (Undo )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hReserved`  
 [in]対応する、`hChapter`パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)です。  
  
 *pcRowsUndone*  
 [out]対応する、`pcRows`パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)です。  
  
 *prgRowsUndone*  
 [in]対応する、 *prgRows*パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)です。  
  
 その他のパラメーターを参照してください。 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)