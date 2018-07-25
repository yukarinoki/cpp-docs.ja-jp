---
title: Handlet::internalclose メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b0aef97645d515a03dcf2cab90eedc06f07971c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874146"
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose メソッド
現在の HandleT オブジェクトを閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>戻り値  
 `true` 現在の HandleT が正常にクローズする場合それ以外の場合、`false`です。  
  
## <a name="remarks"></a>コメント  
 InternalClose() が保護されています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)