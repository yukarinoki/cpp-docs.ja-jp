---
title: Synclockt::islocked メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
dev_langs:
- C++
helpviewer_keywords:
- IsLocked method
ms.assetid: a81fea43-f99a-4708-812a-7fd6af500d3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c4609866b25f574f34b620d81de3a21d6b608db6
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020324"
---
# <a name="synclocktislocked-method"></a>SyncLockT::IsLocked メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
bool IsLocked() const;  
```  
  
## <a name="return-value"></a>戻り値  
 **true**場合、 **SyncLockT**オブジェクトがロックされている場合はそれ以外の場合、 **false**します。  
  
## <a name="remarks"></a>Remarks  
 示すかどうか、現在**SyncLockT**リソースを所有するオブジェクトです。 つまり、 **SyncLockT**オブジェクトが*ロック*します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>関連項目  
 [SyncLockT クラス](../windows/synclockt-class.md)