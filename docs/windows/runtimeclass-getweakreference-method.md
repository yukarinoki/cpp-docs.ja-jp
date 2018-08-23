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
ms.openlocfilehash: cc4d2e542afcd72426cb3b0aba57b7d7cbabad06
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583645"
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