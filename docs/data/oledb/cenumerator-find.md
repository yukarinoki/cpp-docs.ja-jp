---
title: Cenumerator::find |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs:
- C++
helpviewer_keywords:
- Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2466127dab53fa6646a4f149400e4318aed59970
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
使用可能なプロバイダーの中から指定した名前を検索します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      bool Find(TCHAR* szSearchName) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *szSearchName*  
 [in]検索する名前です。  
  
## <a name="return-value"></a>戻り値  
 **true**名前が見つからない場合。 それ以外の場合、 **false**です。  
  
## <a name="remarks"></a>コメント  
 この名前にマップ、 **SOURCES_NAME**のメンバー、 [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx)インターフェイスです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CEnumerator クラス](../../data/oledb/cenumerator-class.md)