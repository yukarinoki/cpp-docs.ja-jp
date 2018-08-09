---
title: Synclockwithstatust::islocked メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80c744431fe7df32be705fcf91eef0a8691b8fa4
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015799"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>Remarks  
 示すかどうか、現在**SyncLockWithStatusT**リソースを所有するオブジェクトです。 つまり、 **SyncLockWithStatusT**オブジェクトが*ロック*します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合、 **SyncLockWithStatusT**オブジェクトがロックされている場合はそれ以外の場合、 **false**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)