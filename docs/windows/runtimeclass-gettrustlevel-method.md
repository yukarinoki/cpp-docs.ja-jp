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
ms.openlocfilehash: c714f37a53e111c90333352610fd73532ac86fe7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599833"
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