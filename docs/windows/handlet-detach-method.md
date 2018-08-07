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
ms.openlocfilehash: cc11d6be992584adb1ce2075e73d080cc3a43f47
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569480"
---
# <a name="handletdetach-method"></a>HandleT::Detach メソッド
現在の関連付けを解除**HandleT**その基になるハンドルからオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
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