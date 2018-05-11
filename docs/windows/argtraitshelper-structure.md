---
title: ArgTraitsHelper 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
dev_langs:
- C++
helpviewer_keywords:
- ArgTraitsHelper structure
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6205d69962d70d9da76c932fdd8b3f66f491ebc9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename TDelegateInterface>  
struct ArgTraitsHelper;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TDelegateInterface`  
 デリゲートのインターフェイスです。  
  
## <a name="remarks"></a>コメント  
 支援は、デリゲート引数の共通の特性を定義します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`methodType`|`decltype(&TDelegateInterface::Invoke)` と同義。|  
|`Traits`|`ArgTraits<methodType>` と同義。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[ArgTraitsHelper::args 定数](../windows/argtraitshelper-args-constant.md)|により、 [argtraits::args](../windows/argtraits-args-constant.md)デリゲート インターフェイスの呼び出しメソッドのパラメーターの数のカウントを保持します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ArgTraitsHelper`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)