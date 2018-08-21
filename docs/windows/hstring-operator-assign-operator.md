---
title: Hstring::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9cc496f4f1c23508b2ebba2788910ff9c9ca2066
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608600"
---
# <a name="hstringoperator-operator"></a>HString::Operator= 演算子
別の値を移動**HString**現在オブジェクト**HString**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
### <a name="parameters"></a>パラメーター  
 *other*  
 既存の**HString**オブジェクト。  
  
## <a name="remarks"></a>Remarks  
 既存の値*他*現在にオブジェクトがコピーされます**HString**オブジェクト、し、*他*オブジェクトが破棄されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)