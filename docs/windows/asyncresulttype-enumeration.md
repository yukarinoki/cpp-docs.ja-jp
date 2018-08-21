---
title: AsyncResultType 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
dev_langs:
- C++
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7989f28ae9c9e3af4c73ec454487d34dd7cff570
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644756"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 列挙型
によって返される結果の種類を指定します、`GetResults()`メソッド。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum AsyncResultType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`MultipleResults`|一連の間で段階的に表示されますが、複数の結果`Start`状態とする前に`Close()`が呼び出されます。|  
|`SingleResult`|後に示す 1 つの結果、`Complete`イベントが発生します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)