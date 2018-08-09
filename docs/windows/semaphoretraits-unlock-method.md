---
title: Semaphoretraits::unlock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98e210ad99a333b6abf68f574916d4f9da5ab67e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650428"
---
# <a name="semaphoretraitsunlock-method"></a>SemaphoreTraits::Unlock メソッド
共有リソースのコントロールをリリースします。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *h*  
 ハンドルを**セマフォ**オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 場合は、ロック解除操作が成功すると、 **Unlock()** エラーの原因を示すエラーを出力します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [SemaphoreTraits 構造体](../windows/semaphoretraits-structure.md)