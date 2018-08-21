---
title: Simpleactivationfactory::activateinstance メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 260d7e2993bd92297167c23458d37ba80919306f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013386"
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance メソッド

指定したインターフェイスのインスタンスを作成します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>パラメーター
*ppvObject*  
ときにこの操作が完了したらで指定されたオブジェクトのインスタンスへのポインター、`Base`クラス テンプレート パラメーター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>Remarks

場合`__WRL_STRICT__`が定義されている、アサート エラーが生成クラス テンプレート パラメーターで指定された基本クラスから派生していない場合[RuntimeClass](../windows/runtimeclass-class.md)、WinRt または WinRtClassicComMix で構成されていないまたは[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
 [SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)