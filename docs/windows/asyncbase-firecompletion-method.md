---
title: Asyncbase::firecompletion メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs:
- C++
helpviewer_keywords:
- FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 199d84afe198c4fc41808144105ea704822aa00a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646608"
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion メソッド
完了イベント ハンドラーを呼び出します。 または内部の進行状況のデリゲートをリセットします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>Remarks  
 最初のバージョンの**FireCompletion()** 内部の進行状況のデリゲート変数をリセットします。 2 番目のバージョンは、非同期操作が完了した場合、完了イベント ハンドラーを呼び出します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)