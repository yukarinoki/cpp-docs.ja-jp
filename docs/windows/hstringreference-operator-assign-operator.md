---
title: Hstringreference::operator = 演算子 |Microsoft Docs
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
ms.openlocfilehash: fc8f919dcec994be5d4f0300e9c96dde95895e16
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608522"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= 演算子
別の値を移動**HStringReference**現在オブジェクト**HStringReference**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
### <a name="parameters"></a>パラメーター  
 *other*  
 既存の**HStringReference**オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 既存の値*他*現在にオブジェクトがコピーされます**HStringReference**オブジェクト、し、*他*オブジェクトが破棄されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HStringReference クラス](../windows/hstringreference-class.md)