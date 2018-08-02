---
title: Asyncbase::fireprogress メソッド |Microsoft Docs
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
ms.openlocfilehash: faa2e1af556f0184fa88055bcbf154eb783e24e5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463598"
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
 *arg*  
 呼び出すイベント ハンドラー メソッド。  
  
## <a name="remarks"></a>Remarks  
 `ProgressTraits` 派生[ArgTraitsHelper 構造体](../windows/argtraitshelper-structure.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)