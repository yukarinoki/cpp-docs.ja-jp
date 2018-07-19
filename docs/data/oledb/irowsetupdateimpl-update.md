---
title: Irowsetupdateimpl::update |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
dev_langs:
- C++
helpviewer_keywords:
- Update method
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c47ee5bf8c8ddc3436414e89b7d365c06158f195
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104244"
---
# <a name="irowsetupdateimplupdate"></a>IRowsetUpdateImpl::Update
最後のフェッチまたは更新以降、行に加えられた変更を送信します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hReserved`  
 [in]対応する、`hChapter`パラメーター [irowsetupdate::update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)です。  
  
 その他のパラメーターを参照してください。 [irowsetupdate::update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 呼び出して変更を転送する[irowsetchangeimpl::flushdata](../../data/oledb/irowsetchangeimpl-flushdata.md)です。 コンシューマーは、呼び出す必要があります[crowset::update](../../data/oledb/crowset-update.md)変更を有効にするためにします。 設定*prgRowstatus* 」の説明に従って適切な値に[行状態](https://msdn.microsoft.com/en-us/library/ms722752.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)