---
title: Asyncbase::fireprogress メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c2c5aab609b597c3a9ff464b868ba831889deed
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863583"
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress メソッド
現在の進行状況イベント ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `arg`  
 イベント ハンドラー メソッドを呼び出します。  
  
## <a name="remarks"></a>コメント  
 `ProgressTraits` 派生した[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)