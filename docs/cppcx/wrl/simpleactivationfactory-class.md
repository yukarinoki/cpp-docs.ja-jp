---
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
ms.openlocfilehash: 39e539c63e91b508f51656114ee8fbd68150991f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370938"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory クラス

Windows ランタイムまたはクラシック COM の基底クラスを作成するための基本的なメカニズムを提供します。

## <a name="syntax"></a>構文

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>パラメーター

*ベース*<br/>
基本クラス。

## <a name="remarks"></a>解説

基本クラスは、既定のコンストラクターを提供する必要があります。

次のコード例は、アクティブ化[クラスウィズファクトリーEx](activatableclass-macros.md)マクロで SimpleActivationFactory を使用する方法を示しています。

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance メソッド](#activateinstance)|指定したインターフェイスのインスタンスを作成します。|
|[SimpleActivationFactory::GetRuntimeClassName メソッド](#getruntimeclassname)|*Base*クラス テンプレート パラメーターで指定されたクラスのインスタンスのランタイム クラス名を取得します。|
|[SimpleActivationFactory::GetTrustLevel メソッド](#gettrustlevel)|*Base*クラス テンプレート パラメーターで指定されたクラスのインスタンスの信頼レベルを取得します。|

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

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a>メソッドをアクティブにします。

指定したインターフェイスのインスタンスを作成します。

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>パラメーター

*オブジェクト*<br/>
この操作が完了すると、クラス テンプレート パラメーターで指定されたオブジェクトの`Base`インスタンスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

定義`__WRL_STRICT__`されている場合、クラス テンプレート パラメーターで指定された基本クラスが[RuntimeClass](runtimeclass-class.md)から派生していない場合、または WinRt または WinRtClassicComMix[ランタイムクラスタイプ](runtimeclasstype-enumeration.md)の列挙値で構成されていない場合、アサート エラーが生成されます。

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a>メソッドを取得します。

クラス テンプレート パラメーターで指定されたクラスのインスタンスのランタイム`Base`クラス名を取得します。

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>パラメーター

*ランタイム名*<br/>
この操作が完了すると、ランタイム クラス名。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

定義`__WRL_STRICT__`されている場合、`Base`クラス テンプレート パラメーターで指定されたクラスが[RuntimeClass](runtimeclass-class.md)から派生していない場合、または WinRt または WinRtClassicComMix[ランタイムクラスタイプ](runtimeclasstype-enumeration.md)の列挙値で構成されていない場合、アサート エラーが生成されます。

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a>メソッドを取得します。

クラス テンプレート パラメーターで指定されたクラスのインスタンスの信頼`Base`レベルを取得します。

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>パラメーター

*トラストルヴル*<br/>
この操作が完了すると、現在のクラス オブジェクトの信頼レベル。

### <a name="return-value"></a>戻り値

常にS_OK。
