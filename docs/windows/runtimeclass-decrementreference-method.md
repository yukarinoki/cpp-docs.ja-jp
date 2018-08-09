---
title: Runtimeclass::decrementreference メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
dev_langs:
- C++
ms.assetid: f5ecfeaa-2865-455b-9208-94a0685fd2c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9577427ed5a63b99d372226f8e7416a21cb6b1e
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010861"
---
# <a name="runtimeclassdecrementreference-method"></a>RuntimeClass::DecrementReference メソッド
参照が現在のカウントをデクリメント**RuntimeClass**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
ULONG DecrementReference();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)