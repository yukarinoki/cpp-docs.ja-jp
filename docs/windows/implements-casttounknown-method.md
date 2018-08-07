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
ms.openlocfilehash: a490e3b8dc620cb3f0f440b2e28cce1f2e69c76d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607249"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown メソッド
基になるポインターを取得します。`IUnknown`インターフェイス。  
  
## <a name="syntax"></a>構文  
  
```  
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