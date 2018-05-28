---
title: Semaphoretraits::unlock メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 0914c6ff83e881f92963fc8a548ddeff587db75e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="semaphoretraitsunlock-method"></a>SemaphoreTraits::Unlock メソッド
共有リソースのリリースのコントロールです。  
  
## <a name="syntax"></a>構文  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 セマフォ オブジェクトへのハンドルします。  
  
## <a name="remarks"></a>コメント  
 ロック解除の操作が成功しなかった場合、Unlock() は、エラーの原因を示すエラーを出力します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [SemaphoreTraits 構造体](../windows/semaphoretraits-structure.md)