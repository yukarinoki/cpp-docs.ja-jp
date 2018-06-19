---
title: Asyncbase::firecompletion メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 0cd18d340a11575ed9f6f52d92a5910dcee1faec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859736"
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion メソッド
完了イベント ハンドラーが呼び出されます。 または内部の進行状況のデリゲートをリセットします。  
  
## <a name="syntax"></a>構文  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>コメント  
 FireCompletion() の最初のバージョンでは、内部の進行状況デリゲート変数をリセットします。 2 番目のバージョンは、非同期操作が完了している場合、完了イベント ハンドラーを呼び出します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)