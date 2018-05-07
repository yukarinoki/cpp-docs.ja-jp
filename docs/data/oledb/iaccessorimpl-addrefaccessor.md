---
title: Iaccessorimpl::addrefaccessor |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
dev_langs:
- C++
helpviewer_keywords:
- AddRefAccessor method
ms.assetid: 4c15392c-944b-4cbd-8cc7-2a5c2f308a70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 856148d718832fdb0f898dbbbe23958c9ba4f99a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="iaccessorimpladdrefaccessor"></a>IAccessorImpl::AddRefAccessor
既存のアクセサーには、参照カウントを追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,  
   DBREFCOUNT* pcRefCount);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IAccessor::AddRefAccessor](https://msdn.microsoft.com/en-us/library/ms714978.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IAccessorImpl クラス](../../data/oledb/iaccessorimpl-class.md)   
 [IAccessorImpl::CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)   
 [IAccessorImpl::ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)