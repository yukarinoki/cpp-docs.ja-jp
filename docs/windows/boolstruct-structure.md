---
title: BoolStruct 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
dev_langs:
- C++
helpviewer_keywords:
- BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14e3d81ca273bf96b4812f08a46904c9d521c5cf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650483"
---
# <a name="boolstruct-structure"></a>BoolStruct 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>Remarks  
 **BoolStruct**構造体を定義するかどうかを`ComPtr`インターフェイスのオブジェクトの有効期間を管理します。 **BoolStruct**内部で使用される、 [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)演算子。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[BoolStruct::Member データ メンバー](../windows/boolstruct-member-data-member.md)|指定します、 [ComPtr](../windows/comptr-class.md)またはインターフェイスのオブジェクトの有効期間の管理ではないです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BoolStruct`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtr::operator Microsoft::WRL::Details::BoolType 演算子](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)