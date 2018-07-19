---
title: AsyncResultType 列挙型 |Microsoft ドキュメント
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
ms.openlocfilehash: de4a8465dd61e52425a0335e171cf516591ae589
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863310"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 列挙型
GetResults() メソッドによって返される結果の型を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`MultipleResults`|開始状態の間で、Close() を呼び出す前に、段階的に記載されている複数の結果のセット。|  
|`SingleResult`|1 つの結果、完全なイベントの発生後に表示されます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)