---
title: Asyncbase::start メソッド |Microsoft Docs
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
ms.openlocfilehash: 32c59c00180b26a2856b1fc210302ffff0e72f0c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641305"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start メソッド
非同期操作を開始します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>戻り値  
 S_OK 場合は、操作の開始またはが既に開始します。それ以外の場合、E_ILLEGAL_STATE_CHANGE します。  
  
## <a name="remarks"></a>Remarks  
 **Start()** の既定の実装は、 `IAsyncInfo::Start`、実際の作業を行いません。 実際には、非同期操作を開始するには、オーバーライド、`OnStart()`純粋仮想メソッド。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)