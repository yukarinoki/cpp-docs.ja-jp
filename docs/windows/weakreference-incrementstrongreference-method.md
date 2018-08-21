---
title: Weakreference::incrementstrongreference メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
dev_langs:
- C++
helpviewer_keywords:
- IncrementStrongReference method
ms.assetid: d0232426-a8cb-48b4-99d4-165de2d66cb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 764a47fe03a2ad9f4e4d3d64a5627acc9c72d1b5
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018872"
---
# <a name="weakreferenceincrementstrongreference-method"></a>WeakReference::IncrementStrongReference メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
ULONG IncrementStrongReference();  
```  
  
## <a name="return-value"></a>戻り値  
 インクリメントされた強い参照数。  
  
## <a name="remarks"></a>Remarks  
 現在の強い参照カウントをインクリメント**WeakReference**オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [WeakReference クラス](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)