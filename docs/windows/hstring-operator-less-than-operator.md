---
title: Hstring::operator&lt;演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs:
- C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1bdc6d54a6c9b60036d7434edec960715db304e2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017683"
---
# <a name="hstringoperatorlt-operator"></a>Hstring::operator&lt;演算子
最初のパラメーターがかどうかが 2 番目のパラメーターを未満を示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
```  
  
### <a name="parameters"></a>パラメーター  
 *lhs*  
 比較する最初のパラメーター。 *lhs*への参照を指定できます、 **HString**します。  
  
 *rhs*  
 比較する 2 番目のパラメーター。 *rhs*への参照を指定できます、 **HString**します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合、 *lhs*パラメーターより小さい*rhs*パラメーター、それ以外の**false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)