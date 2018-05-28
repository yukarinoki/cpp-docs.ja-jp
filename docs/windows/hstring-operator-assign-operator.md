---
title: Hstring::operator = 演算子 |Microsoft ドキュメント
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
ms.openlocfilehash: 6fd1082beb6d84c5dded008e20683f7292cbc1e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="hstringoperator-operator"></a>HString::Operator= 演算子
別の HString オブジェクトの値を現在の HString オブジェクトに移動します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
#### <a name="parameters"></a>パラメーター  
 `other`  
 既存の HString オブジェクト。  
  
## <a name="remarks"></a>コメント  
 既存の値`other`オブジェクトが現在の HString オブジェクトにコピーし、`other`オブジェクトは破棄されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)