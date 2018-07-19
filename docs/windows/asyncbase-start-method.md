---
title: Asyncbase::start メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0acc6f62530daf641a2e4d568ed511d6fd831c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860919"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start メソッド
非同期操作を開始します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>戻り値  
 S_OK 場合は、操作の開始または既に開始です。それ以外の場合、E_ILLEGAL_STATE_CHANGE です。  
  
## <a name="remarks"></a>コメント  
 Start() は、IAsyncInfo::Start の既定の実装は、実際の作業は行われません。 実際には、非同期操作を開始するには、OnStart() 純粋仮想メソッドをオーバーライドします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)