---
title: Simpleactivationfactory::getruntimeclassname メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
dev_langs:
- C++
ms.assetid: 3aa07487-9a42-46f8-8893-37ba6315e50b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e66c6791a55debeb411fd6058d4bbe44cb6637e7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575873"
---
# <a name="simpleactivationfactorygetruntimeclassname-method"></a>SimpleActivationFactory::GetRuntimeClassName メソッド

指定されたクラスのインスタンスのランタイム クラス名を取得、`Base`クラス テンプレート パラメーター。

## <a name="syntax"></a>構文

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>パラメーター

*runtimeName*  
この操作の完了時、ランタイム クラス名。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>Remarks

場合`__WRL_STRICT__`は、定義されている、assert エラーが発生して、クラスが指定されている場合、`Base`クラス テンプレート パラメーターはありませんから派生した[RuntimeClass](../windows/runtimeclass-class.md)、WinRt または WinRtClassicComMixで構成されていないまたは[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)