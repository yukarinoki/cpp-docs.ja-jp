---
title: AsyncStatusInternal 列挙型 |Microsoft ドキュメント
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
ms.openlocfilehash: 150169442aa68395b4dc8a4f4c74951e877f18f5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863726"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal 列挙型
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>コメント  
 非同期操作の状態の内部列挙値の間のマッピングを指定し、 **Windows::Foundation::AsyncStatus**列挙します。  
  
## <a name="members"></a>メンバー  
 `_Created`  
 等価:: Windows::Foundation::AsyncStatus:: を作成  
  
 `_Started`  
 等価:: Windows::Foundation::AsyncStatus:: 開始  
  
 `_Completed`  
 等価:: Windows::Foundation::AsyncStatus:: 完了  
  
 `_Cancelled`  
 等価:: Windows::Foundation::AsyncStatus:: 取り消されました  
  
 `_Error`  
 等価:: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)