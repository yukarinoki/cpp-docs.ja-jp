---
title: RuntimeClassBaseT 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3ea147ebddff03401f6151bcdc44d96efb233f90
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888995"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 構造体
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `RuntimeClassTypeT`  
 1 つ以上を指定するフラグのフィールド[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙子。  
  
## <a name="remarks"></a>コメント  
 用にヘルパー メソッドを提供`QueryInterface`操作とインターフェイスの Id を取得します。  
  
## <a name="members"></a>メンバー  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `RuntimeClassBaseT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [参照 (Windows ランタイム ライブラリ)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)