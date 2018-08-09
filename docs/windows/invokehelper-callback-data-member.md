---
title: Invokehelper::callback _ データ メンバー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::callback_
dev_langs:
- C++
helpviewer_keywords:
- callback_ data member
ms.assetid: 6f0cbf6d-0448-46f8-ba71-bd6fd8702e3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0d6d767a77b68ad8585da711861d942abbe6b686
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013494"
---
# <a name="invokehelpercallback-data-member"></a>InvokeHelper::callback_ データ メンバー
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
TCallback callback_;  
```  
  
## <a name="remarks"></a>Remarks  
 イベントが発生したときに呼び出すイベント ハンドラーを表します。  
  
 `TCallback`テンプレート パラメーターは、イベント ハンドラーの種類を指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [InvokeHelper 構造体](../windows/invokehelper-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)