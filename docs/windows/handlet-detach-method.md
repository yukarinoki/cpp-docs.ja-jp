---
title: Handlet::detach メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 100d215099494c9b2714fd2c42dee69644a5006c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878464"
---
# <a name="handletdetach-method"></a>HandleT::Detach メソッド
基になるハンドルから現在 HandleT オブジェクトの関連付けを解除します。  
  
## <a name="syntax"></a>構文  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>戻り値  
 基になるハンドルです。  
  
## <a name="remarks"></a>コメント  
 この操作が完了すると、現在の HandleT に設定されている状態が無効です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)