---
title: Asyncbase::cancel メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0559f32315265a7db5543e8559097177c2a670fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859853"
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel メソッド
非同期操作をキャンセルします。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>戻り値  
 既定では、常に S_OK を返します。  
  
## <a name="remarks"></a>コメント  
 Cancel() は、IAsyncInfo::Cancel の既定の実装は、実際の作業は行われません。 実際には、非同期操作をキャンセルするには、OnCancel() 純粋仮想メソッドをオーバーライドします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)