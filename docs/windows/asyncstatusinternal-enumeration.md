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
ms.openlocfilehash: a68189c461453dc72585ff4034df5ba69bb41bd5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464877"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 列挙型
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Remarks  
 非同期操作の状態の内部列挙値の間のマッピングを指定します、`Windows::Foundation::AsyncStatus`列挙体。  
  
## <a name="members"></a>メンバー  
 *_Created*  
 同じです:: Windows::Foundation::AsyncStatus:: 作成  
  
 *_Started*  
 同じです:: Windows::Foundation::AsyncStatus:: 開始  
  
 *_Completed*  
 同じです:: Windows::Foundation::AsyncStatus:: 完了  
  
 *_Cancelled*  
 同じです:: Windows::Foundation::AsyncStatus:: が取り消されました  
  
 *エラー (_e)*  
 同じです:: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)