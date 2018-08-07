---
title: Isbaseofstrict::value 定数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- value constant
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d8e5cbbcbbdf3cefe5211eb4f2274ce3b2b79db
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608801"
---
# <a name="isbaseofstrictvalue-constant"></a>IsBaseOfStrict::value 定数
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
static const bool value = __is_base_of(Base, Derived);  
```  
  
## <a name="remarks"></a>Remarks  
 1 つの型が別のベースであるかどうかを示します。  
  
 `value` **true**場合型`Base`型の基本クラスは、 `Derived`、それ以外の場合は**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [IsBaseOfStrict 構造体](../windows/isbaseofstrict-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)