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
ms.openlocfilehash: fe1342c3927183ae5eec30c8dd0a40ee95f37277
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646563"
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

場合&#95; &#95;WRL_STRICT&#95; &#95;は定義されている、アサート エラーが生成クラス テンプレート パラメーターで指定された基本クラスから派生していない場合[RuntimeClass](../windows/runtimeclass-class.md)、WinRt で構成されていないか、またはWinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
 [SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)