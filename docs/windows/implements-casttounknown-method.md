---
title: Implements::casttounknown メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: efaf7b51da1e4a4e744133884b92ac78db3b3f66
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017771"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown メソッド
基になるポインターを取得します。`IUnknown`インターフェイス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>戻り値  
 この操作は、常に成功し、返された、`IUnknown`ポインター。  
  
## <a name="remarks"></a>Remarks  
 内部のヘルパー関数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Implements 構造体](../windows/implements-structure.md)