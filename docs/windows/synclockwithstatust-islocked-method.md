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
ms.openlocfilehash: ebe723811efe62efa85a1cc2fa35736689306c7e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645634"
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
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