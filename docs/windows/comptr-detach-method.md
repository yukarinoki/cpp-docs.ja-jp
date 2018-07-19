---
title: Comptr::detach メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afa5976d26351ed3022c58fa8226b6038fa816c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883594"
---
# <a name="comptrdetach-method"></a>ComPtr::Detach メソッド
この関連付けを解除`ComPtr`オブジェクトが表すインターフェイスからです。  
  
## <a name="syntax"></a>構文  
  
```  
T* Detach();  
```  
  
## <a name="return-value"></a>戻り値  
 これによって表されるインターフェイスへのポインター`ComPtr`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)