---
title: Runtimeclass::gettrustlevel メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: bc588950cc8752a7c2b8e1ddf00b2193aaf0f395
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892632"
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel メソッド

RuntimeClass、現在の信頼レベルを取得します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>パラメーター

*trustLvl*  
この操作の完了時、RuntimeClass、現在の信頼レベル。

## <a name="return-value"></a>戻り値

常に S_OK です。

## <a name="remarks"></a>コメント

場合、アサーション エラーが発生&#95; &#95;WRL_STRICT&#95; &#95;または&#95; &#95;WRL_FORCE_INSPECTABLE_CLASS_MACRO&#95; &#95;が定義されていません。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[RuntimeClass クラス](../windows/runtimeclass-class.md)