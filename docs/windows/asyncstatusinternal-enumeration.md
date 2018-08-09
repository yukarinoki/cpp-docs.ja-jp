---
title: AsyncStatusInternal 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eeaef23178829163725b78685b3460913f53f2c2
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652800"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 列挙型
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Remarks  
 非同期操作の状態の内部列挙値の間のマッピングを指定します、`Windows::Foundation::AsyncStatus`列挙体。  
  
## <a name="members"></a>メンバー  
 `_Created`  
 `::Windows::Foundation::AsyncStatus::Created` と同じ意味です。  
  
 `_Started`  
 `::Windows::Foundation::AsyncStatus::Started` と同じ意味です。  
  
 `_Completed`  
 `::Windows::Foundation::AsyncStatus::Completed` と同じ意味です。  
  
 `_Cancelled`  
 `::Windows::Foundation::AsyncStatus::Cancelled` と同じ意味です。  
  
 `_Error`  
 `::Windows::Foundation::AsyncStatus::Error` と同じ意味です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)