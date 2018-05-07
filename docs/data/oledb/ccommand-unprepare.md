---
title: Ccommand::unprepare |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- Unprepare
- CCommand.Unprepare
- CCommand::Unprepare
dev_langs:
- C++
helpviewer_keywords:
- Unprepare method
ms.assetid: 4fe59988-fe51-4c7c-a156-72b68e3d642b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab5fdd595e646e181aa3815d6385595f3fee21a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ccommandunprepare"></a>CCommand::Unprepare
現在のコマンドの実行プランを破棄します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT CCommandBase::Unprepare() throw();  
  
```  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、OLE DB メソッドをラップ[ICommandPrepare::Unprepare](https://msdn.microsoft.com/en-us/library/ms719635.aspx)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CCommand クラス](../../data/oledb/ccommand-class.md)