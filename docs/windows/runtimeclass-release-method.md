---
title: Runtimeclass::release メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method
ms.assetid: 0bd6f9e2-ad90-4de6-adef-a6286f458cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d07e941f3f8ee0d7df2df14216fa60ef3a2a706
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888797"
---
# <a name="runtimeclassrelease-method"></a>RuntimeClass::Release メソッド
現在の RuntimeClass オブジェクトに対して COM 解放操作を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 参照カウントがゼロになった場合、RuntimeClass オブジェクトは削除されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)