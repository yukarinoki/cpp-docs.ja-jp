---
description: '詳細情報: SimpleActivationFactory クラス'
title: SimpleActivationFactory クラス
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 83643c69977b887e58e430bbd500fcf7c2e81ca6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135214"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory クラス

Windows ランタイムまたはクラシック COM の基底クラスを作成するための基本的なメカニズムを提供します。

## <a name="syntax"></a>構文

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>パラメーター

*常用*<br/>
基本クラス。

## <a name="remarks"></a>解説

基本クラスは、既定のコンストラクターを提供する必要があります。

次のコード例は、 [ActivatableClassWithFactoryEx](activatableclass-macros.md) マクロで SimpleActivationFactory を使用する方法を示しています。

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance メソッド](#activateinstance)|指定したインターフェイスのインスタンスを作成します。|
|[SimpleActivationFactory::GetRuntimeClassName メソッド](#getruntimeclassname)|*基本* クラステンプレートパラメーターによって指定されたクラスのインスタンスのランタイムクラス名を取得します。|
|[SimpleActivationFactory::GetTrustLevel メソッド](#gettrustlevel)|*基本* クラステンプレートパラメーターによって指定されたクラスのインスタンスの信頼レベルを取得します。|

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

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a> SimpleActivationFactory:: メソッド

指定したインターフェイスのインスタンスを作成します。

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>パラメーター

*ppvObject*<br/>
この操作が完了したら、クラステンプレートパラメーターによって指定されたオブジェクトのインスタンスへのポインター `Base` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

が定義されている場合 `__WRL_STRICT__` 、クラステンプレートパラメーターに指定された基本クラスが [RuntimeClass](runtimeclass-class.md)から派生していないか、または WinRt または WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) 列挙値で構成されていない場合、アサートエラーが生成されます。

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a> SimpleActivationFactory:: GetRuntimeClassName メソッド

クラステンプレートパラメーターによって指定されたクラスのインスタンスのランタイムクラス名を取得し `Base` ます。

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>パラメーター

*runtimeName*<br/>
この操作が完了すると、ランタイムクラス名が指定されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

が定義されている場合 `__WRL_STRICT__` 、クラステンプレートパラメーターによって指定されたクラスが `Base` [RuntimeClass](runtimeclass-class.md)から派生していないか、WinRt または WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) 列挙値で構成されていない場合、assert エラーが生成されます。

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a> SimpleActivationFactory:: GetTrustLevel メソッド

クラステンプレートパラメーターによって指定されたクラスのインスタンスの信頼レベルを取得し `Base` ます。

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>パラメーター

*trustLvl*<br/>
この操作が完了すると、現在のクラスオブジェクトの信頼レベル。

### <a name="return-value"></a>戻り値

常に S_OK します。
