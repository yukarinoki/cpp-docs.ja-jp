---
title: Asyncbase::onclose メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 95a0cce7f51ef7974d0520f0bdfd2f025a09ecaf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbaseonclose-method"></a>AsyncBase::OnClose メソッド
派生クラスでオーバーライドされると、非同期操作を閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
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