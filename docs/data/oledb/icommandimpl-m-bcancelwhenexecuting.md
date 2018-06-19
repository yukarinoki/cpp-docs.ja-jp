---
title: Icommandimpl::m_bcancelwhenexecuting |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::m_bCancelWhenExecuting
- ICommandImpl.m_bCancelWhenExecuting
- ATL::ICommandImpl::m_bCancelWhenExecuting
- m_bCancelWhenExecuting
- ATL.ICommandImpl.m_bCancelWhenExecuting
dev_langs:
- C++
helpviewer_keywords:
- m_bCancelWhenExecuting
ms.assetid: d7d33e4c-a862-4e6d-a9a1-4400bfe45b88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc76547be05976e21db7dd7207945608415ee620
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099512"
---
# <a name="icommandimplmbcancelwhenexecuting"></a>ICommandImpl::m_bCancelWhenExecuting
実行するときに、コマンドを取り消すことができるかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp
unsigned m_bCancelWhenExecuting:1;  
  
```  
  
## <a name="remarks"></a>コメント  
 既定値は**true** (キャンセルできます)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [ICommandImpl クラス](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::m_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)