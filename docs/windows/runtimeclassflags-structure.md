---
title: RuntimeClassFlags 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 823244b54513e4f6b2901bc29984604f65eb9a11
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018037"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 構造体
インスタンスの型が含まれています、 [RuntimeClass](../windows/runtimeclass-class.md)します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
### <a name="parameters"></a>パラメーター  
 *flags*  
 A [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)値。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constants"></a>パブリック定数  
  
|name|説明|  
|----------|-----------------|  
|[RuntimeClassFlags::value 定数](../windows/runtimeclassflags-value-constant.md)|含まれています、 [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)値。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `RuntimeClassFlags`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)