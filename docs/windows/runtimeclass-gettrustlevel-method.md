---
title: Runtimeclass::gettrustlevel メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: adcec3f4a531a6c48e0995468994900124746e4b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015132"
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel メソッド

現在の信頼レベルを取得**RuntimeClass**オブジェクト。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>パラメーター
*trustLvl*  
ときにこの操作が完了すると、現在の信頼レベル**RuntimeClass**オブジェクト。

## <a name="return-value"></a>戻り値

常に s_ok を返します。

## <a name="remarks"></a>Remarks

場合は、アサート エラーが出力`__WRL_STRICT__`または`__WRL_FORCE_INSPECTABLE_CLASS_MACRO__`が定義されていません。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
 [RuntimeClass クラス](../windows/runtimeclass-class.md)