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
ms.openlocfilehash: ab47405f81cf6fb92af215f1868d8ad7c42bffa7
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463731"
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
 S_OK 場合は、操作の開始またはが既に開始します。それ以外の場合、E_ILLEGAL_STATE_CHANGE します。  
  
## <a name="remarks"></a>Remarks  
 **Start()** の既定の実装は、 `IAsyncInfo::Start`、実際の作業を行いません。 実際には、非同期操作を開始するには、オーバーライド、`OnStart()`純粋仮想メソッド。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)