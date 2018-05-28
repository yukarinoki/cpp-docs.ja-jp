---
title: Asyncbase::oncancel メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs:
- C++
helpviewer_keywords:
- OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7c5fabc84d6abb44a904c951c39eaf54a5c16b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbaseoncancel-method"></a>AsyncBase::OnCancel メソッド
派生クラスでオーバーライドされると、非同期操作をキャンセルします。  
  
## <a name="syntax"></a>構文  
  
```  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)   
 [AsyncBase::Cancel メソッド](../windows/asyncbase-cancel-method.md)