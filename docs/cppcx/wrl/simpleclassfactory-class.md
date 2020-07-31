---
title: SimpleClassFactory クラス
ms.date: 09/7/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
helpviewer_keywords:
- Microsoft::WRL::SimpleClassFactory class
- Microsoft::WRL::SimpleClassFactory::CreateInstance method
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
ms.openlocfilehash: 66794789e51a2635fae646cca49e4fae8385dfe0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211152"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory クラス

基底クラスを作成するための基本的なメカニズムを提供します。

## <a name="syntax"></a>構文

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>パラメーター

*常用*<br/>
基本クラス。

## <a name="remarks"></a>解説

基本クラスは、既定のコンストラクターを提供する必要があります。

次のコード例は、ActivatableClassWithFactoryEx マクロでを使用する方法を示して `SimpleClassFactory` います。 [ActivatableClassWithFactoryEx](activatableclass-macros.md)

`ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[SimpleClassFactory::CreateInstance メソッド](#createinstance)|指定したインターフェイスのインスタンスを作成します。|

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

`ClassFactory`

`SimpleClassFactory`

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="simpleclassfactorycreateinstance-method"></a><a name="createinstance"></a>SimpleClassFactory:: CreateInstance メソッド

指定したインターフェイスのインスタンスを作成します。

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

#### <a name="parameters"></a>パラメーター

*pUnkOuter*<br/>
はである必要があります。 **`nullptr`** それ以外の場合、戻り値は CLASS_E_NOAGGREGATION になります。

SimpleClassFactory では集計はサポートされていません。 集計がサポートされており、作成されるオブジェクトが集計の一部であった場合、 *pUnkOuter*は、集計の制御インターフェイスへのポインターになり `IUnknown` ます。

*riid*<br/>
作成するオブジェクトのインターフェイス ID。

*ppvObject*<br/>
この操作が完了したら、 *riid*パラメーターによって指定されたオブジェクトのインスタンスへのポインターを指定します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

が定義されている場合 `__WRL_STRICT__` 、クラステンプレートパラメーターに指定された基本クラスが[RuntimeClass](runtimeclass-class.md)から派生していないか、Classiccom または WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md)列挙値で構成されていない場合、アサートエラーが生成されます。
