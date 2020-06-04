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
ms.openlocfilehash: 924b9d2c30f11e6f0444d9c647807f1c86dcc411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373557"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory クラス

基底クラスを作成するための基本的なメカニズムを提供します。

## <a name="syntax"></a>構文

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>パラメーター

*ベース*<br/>
基本クラス。

## <a name="remarks"></a>解説

基本クラスは、既定のコンストラクターを提供する必要があります。

次のコード例は、アクティブ`SimpleClassFactory`[にできるクラスウィズファクトリーEx](activatableclass-macros.md)マクロを使用する方法を示しています。

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

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="simpleclassfactorycreateinstance-method"></a><a name="createinstance"></a>メソッドを作成します。

指定したインターフェイスのインスタンスを作成します。

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

#### <a name="parameters"></a>パラメーター

*プンクアウター*<br/>
必要があります`nullptr`;それ以外の場合は、戻り値はCLASS_E_NOAGGREGATION。

集計をサポートしていません。 集約がサポートされ、作成されるオブジェクトが集約の一部であった場合 *、pUnkOuter*は集約の制御インターフェース`IUnknown`へのポインターになります。

*riid*<br/>
作成するオブジェクトのインターフェイス ID。

*オブジェクト*<br/>
この操作が完了すると *、riid*パラメーターで指定されたオブジェクトのインスタンスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

定義`__WRL_STRICT__`されている場合、クラス テンプレート パラメーターで指定された基本クラスが[RuntimeClass](runtimeclass-class.md)から派生していない場合、またはクラシック Com または WinRtClassicComMix[ランタイムクラスタイプ](runtimeclasstype-enumeration.md)の列挙値で構成されていない場合、アサート エラーが生成されます。
