---
title: Runtimeclass::getweakreference メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs:
- C++
helpviewer_keywords:
- GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb0d5e6ca19749a4647ec85311e1fce0e7561b59
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608535"
---
# <a name="runtimeclassgetweakreference-method"></a>RuntimeClass::GetWeakReference メソッド
現在の弱い参照オブジェクトにポインターを取得します。 **RuntimeClass**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
### <a name="parameters"></a>パラメーター  
 *weakReference*  
 この操作が完了時は、弱い参照オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 常に s_ok を返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)