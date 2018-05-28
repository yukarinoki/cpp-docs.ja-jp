---
title: CompareStringOrdinal メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3abf87340671d1ac4851b055a57896e340d0c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline INT32 CompareStringOrdinal(  
   HSTRING lhs,   
   HSTRING rhs)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lhs`  
 比較する最初の HSTRING です。  
  
 `rhs`  
 比較する 2 番目の HSTRING です。  
  
## <a name="return-value"></a>戻り値  
  
|[値]|条件|  
|-----------|---------------|  
|-1|`lhs` は `rhs` より小さい値です。|  
|0|`lhs` と `rhs` は等しい。|  
|1|`lhs` が `rhs` より大きくなっています。|  
  
## <a name="remarks"></a>コメント  
 2 つの指定した HSTRING オブジェクトを比較し、並べ替え順序におけるそれらの相対位置を示す整数を返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)