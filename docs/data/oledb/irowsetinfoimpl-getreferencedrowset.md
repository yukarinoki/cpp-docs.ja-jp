---
title: Irowsetinfoimpl::getreferencedrowset |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetInfoImpl::GetReferencedRowset
- GetReferencedRowset
- ATL.IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl.GetReferencedRowset
- IRowsetInfoImpl::GetReferencedRowset
dev_langs:
- C++
helpviewer_keywords:
- GetReferencedRowset method
ms.assetid: 94d2155c-9da0-4c19-a37c-bc35716359fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ca538822acdc9493e89639715588db35d5cee686
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetinfoimplgetreferencedrowset"></a>IRowsetInfoImpl::GetReferencedRowset
ブックマークが適用される行セットにインターフェイス ポインターを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (GetReferencedRowset )(DBORDINAL iOrdinal,  
   REFIID riid,  
   IUnknown** ppReferencedRowset);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetInfo::GetReferencedRowset](https://msdn.microsoft.com/en-us/library/ms721145.aspx)で、 *OLE DB プログラマーズ リファレンス*です。 *IOrdinal*パラメーターは、ブックマーク列をする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetInfoImpl クラス](../../data/oledb/irowsetinfoimpl-class.md)   
 [Irowsetinfoimpl::getspecification](../../data/oledb/irowsetinfoimpl-getspecification.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)