---
title: Hstringreference::operator&lt;演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs:
- C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 489d97252dcb4d20b7ef2f8557991a4e6016743d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605533"
---
# <a name="hstringreferenceoperatorlt-operator"></a>Hstringreference::operator&lt;演算子
最初のパラメーターがかどうかが 2 番目のパラメーターを未満を示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
### <a name="parameters"></a>パラメーター  
 *lhs*  
 比較する最初のパラメーター。 *lhs*への参照を指定できます、 **HStringReference**します。  
  
 *rhs*  
 比較する 2 番目のパラメーター。  *rhs*への参照を指定できます、 **HStringReference**します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合、 *lhs*パラメーターより小さい*rhs*パラメーター、それ以外の**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HStringReference クラス](../windows/hstringreference-class.md)