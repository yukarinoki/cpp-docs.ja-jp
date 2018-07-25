---
title: Hstringreference::operator = 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73ec71526d340aafb16ddf2af274dce7ad0e9cbd
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875540"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= 演算子
別の HStringReference オブジェクトの値を現在の HStringReference オブジェクトに移動します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### <a name="parameters"></a>パラメーター  
 `other`  
 既存の HStringReference オブジェクト。  
  
## <a name="remarks"></a>コメント  
 既存の値`other`オブジェクトが現在の HStringReference オブジェクトにコピーし、`other`オブジェクトは破棄されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HStringReference クラス](../windows/hstringreference-class.md)