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
ms.openlocfilehash: a54b61902c8994397c7bd6effa74a90d43c7e512
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568642"
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose メソッド
現在の終了**HandleT**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
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