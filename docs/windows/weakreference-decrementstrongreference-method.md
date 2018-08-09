---
title: Weakreference::decrementstrongreference メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- DecrementStrongReference method
ms.assetid: 97d70d9f-41b8-4f8d-a6fa-4137cc4f9029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19dcb3e90faef86fd291381a7082e8b5bfa89069
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013458"
---
# <a name="weakreferencedecrementstrongreference-method"></a>WeakReference::DecrementStrongReference メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
ULONG DecrementStrongReference();  
```  
  
## <a name="remarks"></a>Remarks  
 強い参照が現在のカウントをデクリメント**WeakReference**オブジェクト。  
  
 強い参照に設定されている強力な参照カウントがゼロになったら、 **nullptr**します。  
  
## <a name="return-value"></a>戻り値  
 デクリメントされた強い参照数。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [WeakReference クラス](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)