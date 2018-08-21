---
title: Handlet::internalclose メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2190a8e85f81062cc1167aa844fccf4afc819bc9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648803"
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose メソッド
現在の終了**HandleT**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>戻り値  
 **true**場合、現在**HandleT**正常。 それ以外の終了**false**します。  
  
## <a name="remarks"></a>Remarks  
 **InternalClose()** は**保護**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)