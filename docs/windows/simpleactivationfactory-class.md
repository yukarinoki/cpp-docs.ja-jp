---
title: SimpleActivationFactory クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0820012c8c22de1287fcb09037212b870a4ff7bf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594799"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory クラス

Windows ランタイムまたはクラシック COM の基底クラスを作成するための基本的なメカニズムを提供します。

## <a name="syntax"></a>構文

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>パラメーター

*ベース*  
基本クラスです。

## <a name="remarks"></a>Remarks

基底クラスには、既定のコンス トラクターを提供する必要があります。

次のコード例で SimpleActivationFactory を使用する方法を示します、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロ。

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance メソッド](../windows/simpleactivationfactory-activateinstance-method.md)|指定したインターフェイスのインスタンスを作成します。|
|[SimpleActivationFactory::GetRuntimeClassName メソッド](../windows/simpleactivationfactory-getruntimeclassname-method.md)|指定されたクラスのインスタンスのランタイム クラス名を取得、*ベース*クラス テンプレート パラメーター。|
|[SimpleActivationFactory::GetTrustLevel メソッド](../windows/simpleactivationfactory-gettrustlevel-method.md)|指定されたクラスのインスタンスの信頼レベルを取得、*ベース*クラス テンプレート パラメーター。|

## <a name="inheritance-hierarchy"></a>継承階層

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

`SimpleActivationFactory`

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)