---
title: Handlet::detach メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7bf4a6fab735708295a0ae229e7b47101ecc115b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648393"
---
# <a name="handletdetach-method"></a>HandleT::Detach メソッド
現在の関連付けを解除**HandleT**その基になるハンドルからオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>戻り値  
 基になるハンドル。  
  
## <a name="remarks"></a>Remarks  
 ときにこの操作が完了すると、現在**HandleT**が無効な状態に設定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)