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
ms.openlocfilehash: 5cba36256e6abe176c6f5785b49a105395a30ee7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014186"
---
# <a name="runtimeclassgetweakreference-method"></a>RuntimeClass::GetWeakReference メソッド
現在の弱い参照オブジェクトにポインターを取得します。 **RuntimeClass**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
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