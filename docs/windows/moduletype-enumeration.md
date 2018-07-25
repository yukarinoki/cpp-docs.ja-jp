---
title: ModuleType 列挙型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d36355c9f64f9f5c827ef8c4d5b3cb6a77d17b65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876837"
---
# <a name="moduletype-enumeration"></a>ModuleType 列挙型
モジュールがインプロセス サーバーまたはアウトプロセス サーバーをサポートするかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`InProc`|・ インプロセス サーバーです。|  
|`OutOfProc`|アウト プロセス サーバーの場合。|  
|`DisableCaching`|モジュール上のキャッシュ メカニズムを無効にします。|  
|`InProcDisableCaching`|組み合わせ`InProc`と`DisableCaching`です。|  
|`OutOfProcDisableCaching`|組み合わせ`OutOfProc`と`DisableCaching`です。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)