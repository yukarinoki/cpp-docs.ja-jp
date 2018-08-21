---
title: Comptrref::comptrref コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef, constructor
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 621f852728cb40ea88a916b37147c28d8bb0db38
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644463"
---
# <a name="comptrrefcomptrref-constructor"></a>ComPtrRef::ComPtrRef コンストラクター
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *ptr*  
 別の基になる値**ComPtrRef**オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 新しいインスタンスを初期化、 **ComPtrRef**クラス、指定されたポインター **ComPtrRef**オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [ComPtrRef クラス](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)