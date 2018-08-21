---
title: Asyncbase::onclose メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnClose
dev_langs:
- C++
helpviewer_keywords:
- OnClose method
ms.assetid: 96766450-c262-4611-8534-7d190b799142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c1b888b9d3e3f3c80c3aff40f5fd545ece9cca6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650639"
---
# <a name="asyncbaseonclose-method"></a>AsyncBase::OnClose メソッド
派生クラスでオーバーライドされると、非同期操作を終了します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)   
 [AsyncBase::Close メソッド](../windows/asyncbase-close-method.md)