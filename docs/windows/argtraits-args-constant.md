---
title: Argtraits::args 定数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits::args
dev_langs:
- C++
helpviewer_keywords:
- args constant
ms.assetid: a68100ab-254b-4571-a0bc-946f1633a46b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b6f0059d167b04c9a4b177d1851ad88133ef5cd3
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466557"
---
# <a name="argtraitsargs-constant"></a>ArgTraits::args 定数
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
static const int args = -1; ;  
```  
  
## <a name="remarks"></a>Remarks  
 パラメーターの数のカウントを保持、`Invoke`デリゲート インターフェイスのメソッド。  
  
## <a name="remarks"></a>Remarks  
 ときに`args`が-1 のでは、必要がありますに一致することを示します、`Invoke`メソッド シグネチャ。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [ArgTraits 構造体](../windows/argtraits-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)