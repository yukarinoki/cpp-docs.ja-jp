---
title: Hstringreference::operator&lt;演算子 |Microsoft ドキュメント
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
ms.openlocfilehash: 5b486157fb42883af724f2356e7f85701e405035
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877294"
---
# <a name="hstringreferenceoperatorlt-operator"></a>Hstringreference::operator&lt;演算子
最初のパラメーターがあるか、2 番目のパラメーターより小さいことを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lhs`  
 比較する最初のパラメーター。 `lhs` HStringReference への参照ができます。  
  
 `rhs`  
 比較する 2 番目のパラメーターです。  `rhs` HStringReference への参照ができます。  
  
## <a name="return-value"></a>戻り値  
 `true` 場合、`lhs`パラメーターより小さい`rhs`パラメーターです。 それ以外の場合、`false`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HStringReference クラス](../windows/hstringreference-class.md)