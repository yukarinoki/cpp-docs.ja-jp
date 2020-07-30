---
title: Module クラス
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
- module/Microsoft::WRL::Module::Create
- module/Microsoft::WRL::Module::DecrementObjectCount
- module/Microsoft::WRL::Module::GetActivationFactory
- module/Microsoft::WRL::Module::GetClassObject
- module/Microsoft::WRL::Module::GetModule
- module/Microsoft::WRL::Module::GetObjectCount
- module/Microsoft::WRL::Module::IncrementObjectCount
- module/Microsoft::WRL::Module::Module
- module/Microsoft::WRL::Module::objectCount_Data
- module/Microsoft::WRL::Module::RegisterCOMObject
- module/Microsoft::WRL::Module::RegisterObjects
- module/Microsoft::WRL::Module::RegisterWinRTObject
- module/Microsoft::WRL::Module::releaseNotifier_
- module/Microsoft::WRL::Module::Terminate
- module/Microsoft::WRL::Module::~Module
- module/Microsoft::WRL::Module::UnregisterCOMObject
- module/Microsoft::WRL::Module::UnregisterObjects
- module/Microsoft::WRL::Module::UnregisterWinRTObject
helpviewer_keywords:
- Microsoft::WRL::Module class
- Microsoft::WRL::Module::Create method
- Microsoft::WRL::Module::DecrementObjectCount method
- Microsoft::WRL::Module::GetActivationFactory method
- Microsoft::WRL::Module::GetClassObject method
- Microsoft::WRL::Module::GetModule method
- Microsoft::WRL::Module::GetObjectCount method
- Microsoft::WRL::Module::IncrementObjectCount method
- Microsoft::WRL::Module::Module, constructor
- Microsoft::WRL::Module::objectCount_ data member
- Microsoft::WRL::Module::RegisterCOMObject method
- Microsoft::WRL::Module::RegisterObjects method
- Microsoft::WRL::Module::RegisterWinRTObject method
- Microsoft::WRL::Module::releaseNotifier_ data member
- Microsoft::WRL::Module::Terminate method
- Microsoft::WRL::Module::~Module, destructor
- Microsoft::WRL::Module::UnregisterCOMObject method
- Microsoft::WRL::Module::UnregisterObjects method
- Microsoft::WRL::Module::UnregisterWinRTObject method
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
ms.openlocfilehash: f7930247c979c111a7f4798e35ebe7aa95209f37
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225749"
---
# <a name="module-class"></a>Module クラス

関連するオブジェクトから成るコレクションを表します。

## <a name="syntax"></a>構文

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>パラメーター

*合成*<br/>
1つ以上の[ModuleType](moduletype-enumeration.md)列挙値の組み合わせ。

## <a name="members"></a>メンバー

### <a name="protected-classes"></a>プロテクトクラス

名前                                                                                | [説明]
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier](module-genericreleasenotifier-class.md) | 現在のモジュールの最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。 イベントハンドラーは、ラムダ、ファンクタ、またはポインターから関数によって指定されます。
[Module:: MethodReleaseNotifier](module-methodreleasenotifier-class.md)   | 現在のモジュールの最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。 イベントハンドラーは、オブジェクトおよびそのポインターからメソッドへのメンバーによって指定されます。
[Module:: ReleaseNotifier](module-releasenotifier-class.md)               | モジュール内の最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                             | [説明]
-------------------------------- | -----------------------------------------------------------
[Module:: ~ Module](#tilde-module) | クラスの現在のインスタンスを初期化解除 `Module` します。

### <a name="protected-constructors"></a>プロテクト コンストラクター

名前                      | [説明]
------------------------- | ---------------------------------------------------
[Module:: Module](#module) | `Module` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                    | [説明]
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Module:: Create](#create)                               | モジュールのインスタンスを作成します。
[モジュール::D ecrementObjectCount](#decrementobjectcount)   | モジュールによって追跡されるオブジェクトの数をデクリメントします。
[Module:: GetActivationFactory](#getactivationfactory)   | モジュールのアクティベーションファクトリを取得します。
[Module:: GetClassObject](#getclassobject)               | クラスファクトリのキャッシュを取得します。
[Module:: GetModule](#getmodule)                         | モジュールのインスタンスを作成します。
[Module:: GetObjectCount](#getobjectcount)               | このモジュールによって管理されるオブジェクトの数を取得します。
[Module:: IncrementObjectCount](#incrementobjectcount)   | モジュールによって追跡されるオブジェクトの数をインクリメントします。
[Module:: RegisterCOMObject](#registercomobject)         | 他のアプリケーションが接続できるように、1つまたは複数の COM オブジェクトを登録します。
[Module:: RegisterObjects](#registerobjects)             | 他のアプリケーションが接続できるように、COM オブジェクトまたは Windows ランタイムオブジェクトを登録します。
[Module:: RegisterWinRTObject](#registerwinrtobject)     | 他のアプリケーションが接続できるように、1つまたは複数の Windows ランタイムオブジェクトを登録します。
[Module:: Terminate](#terminate)                         | モジュールによってインスタンス化されたすべてのファクトリをシャットダウンさせます。
[Module:: UnregisterCOMObject](#unregistercomobject)     | 1つ以上の COM オブジェクトの登録を解除します。これにより、他のアプリケーションが接続できなくなります。
[Module:: UnregisterObjects](#unregisterobjects)         | 他のアプリケーションが接続できないように、指定したモジュール内のオブジェクトの登録を解除します。
[Module:: UnregisterWinRTObject](#unregisterwinrtobject) | 他のアプリケーションが接続できないように、1つまたは複数の Windows ランタイムオブジェクトの登録を解除します。

### <a name="protected-methods"></a>プロテクト メソッド

名前                      | [説明]
------------------------- | --------------------------------
[Module:: Create](#create) | モジュールのインスタンスを作成します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                         | [説明]
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Module:: objectCount_](#objectcount)         | [Make](make-function.md)関数で作成されたクラスの数を追跡します。
[Module:: releaseNotifier_](#releasenotifier) | オブジェクトへのポインターを保持 `ReleaseNotifier` します。

### <a name="macros"></a>[マクロ]

名前                                                                   | [説明]
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ActivatableClass](activatableclass-macros.md)              | 指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを作成します。 このマクロは、既定のファクトリおよびグループ ID パラメーターを指定します。
[ActivatableClassWithFactory](activatableclass-macros.md)   | 指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを作成します。 このマクロを使用すると、特定のファクトリパラメーターを指定できます。
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | 指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを作成します。 このマクロを使用すると、特定のファクトリおよびグループ ID パラメーターを指定できます。

## <a name="inheritance-hierarchy"></a>継承階層

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="modulemodule"></a><a name="tilde-module"></a>Module:: ~ Module

クラスの現在のインスタンスを初期化解除 `Module` します。

```cpp
virtual ~Module();
```

## <a name="modulecreate"></a><a name="create"></a>Module:: Create

モジュールのインスタンスを作成します。

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
モジュールの種類。

*コール*<br/>
モジュールの最後のインスタンスオブジェクトが解放されたときに呼び出されます。

*object*<br/>
*オブジェクト*と*メソッド*のパラメーターは、組み合わせて使用されます。 モジュール内の最後のインスタンスオブジェクトが解放されたときに、最後のインスタンスオブジェクトを指します。

*method*<br/>
*オブジェクト*と*メソッド*のパラメーターは、組み合わせて使用されます。 モジュール内の最後のインスタンスオブジェクトが解放されたときに、最後のインスタンスオブジェクトのメソッドをポイントします。

### <a name="return-value"></a>戻り値

モジュールへの参照。

## <a name="moduledecrementobjectcount"></a><a name="decrementobjectcount"></a>モジュール::D ecrementObjectCount

モジュールによって追跡されるオブジェクトの数をデクリメントします。

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>戻り値

デクリメント操作の前のカウント。

## <a name="modulegetactivationfactory"></a><a name="getactivationfactory"></a>Module:: GetActivationFactory

モジュールのアクティベーションファクトリを取得します。

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>パラメーター

*pActivatibleClassId*<br/>
ランタイムクラスの IID。

*ppIFactory*<br/>
指定されたランタイムクラスの IActivationFactory。

*Server*<br/>
現在のモジュールのクラスファクトリのサブセットの名前。 [ActivatableClassWithFactoryEx](activatableclass-macros.md)マクロで使用するサーバー名を指定するか、を指定して **`nullptr`** 既定のサーバー名を取得します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、GetActivationFactory によって返される HRESULT です。

## <a name="modulegetclassobject"></a><a name="getclassobject"></a>Module:: GetClassObject

クラスファクトリのキャッシュをキューを取得します。

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
クラス ID。

*riid*<br/>
要求するインターフェイス ID。

*ppv*<br/>
返されたオブジェクトへのポインター。

*Server*<br/>
、、またはのいずれかのマクロで指定されたサーバー名 `ActivatableClassWithFactory` `ActivatableClassWithFactoryEx` `ActivatableClass` **`nullptr`** 。既定のサーバー名を取得する場合は。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

このメソッドは、Windows ランタイムではなく、COM に対してのみ使用してください。 このメソッドは `IClassFactory` 、メソッドのみを公開します。

## <a name="modulegetmodule"></a><a name="getmodule"></a>Module:: GetModule

モジュールのインスタンスを作成します。

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>戻り値

モジュールへの参照。

## <a name="modulegetobjectcount"></a><a name="getobjectcount"></a>Module:: GetObjectCount

このモジュールによって管理されるオブジェクトの数を取得します。

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>戻り値

このモジュールによって管理されているオブジェクトの現在の数。

## <a name="moduleincrementobjectcount"></a><a name="incrementobjectcount"></a>Module:: IncrementObjectCount

モジュールによって追跡されるオブジェクトの数をインクリメントします。

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>戻り値

インクリメント操作の前のカウント。

## <a name="modulemodule"></a><a name="module"></a>Module:: Module

`Module` クラスの新しいインスタンスを初期化します。

```cpp
Module();
```

### <a name="remarks"></a>解説

このコンストラクターは保護されているため、キーワードを使用して呼び出すことはできません **`new`** 。 代わりに、 [module:: getmodule](#getmodule)または[Module:: Create](#create)を呼び出します。

## <a name="moduleobjectcount_"></a><a name="objectcount"></a>Module:: objectCount_

[Make](make-function.md)関数で作成されたクラスの数を追跡します。

```cpp
volatile long objectCount_;
```

## <a name="moduleregistercomobject"></a><a name="registercomobject"></a>Module:: RegisterCOMObject

他のアプリケーションが接続できるように、1つまたは複数の COM オブジェクトを登録します。

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>パラメーター

*Server*<br/>
サーバーの完全修飾名。

*clsid*<br/>
登録する Clsid の配列。

*factories*<br/>
可用性が公開されているクラスオブジェクトの IUnknown インターフェイスの配列。

*cookies*<br/>
操作が完了すると、登録されたクラスオブジェクトを識別する値へのポインターの配列。 これらの値は、後で登録を取り消すために使用されます。

*count*<br/>
登録する Clsid の数。

### <a name="return-value"></a>戻り値

If successfu; S_OKそれ以外の場合は、CO_E_OBJISREG などの HRESULT で、操作が失敗した理由を示します。

### <a name="remarks"></a>解説

COM オブジェクトは、CLSCTX 列挙の CLSCTX_LOCAL_SERVER 列挙子に登録されます。

登録されたオブジェクトへの接続の種類は、現在の*comflag*テンプレートパラメーターと、regcls 列挙の REGCLS_SUSPENDED 列挙子の組み合わせによって指定されます。

## <a name="moduleregisterobjects"></a><a name="registerobjects"></a>Module:: RegisterObjects

他のアプリケーションが接続できるように、COM オブジェクトまたは Windows ランタイムオブジェクトを登録します。

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>パラメーター

*第*<br/>
COM オブジェクトまたは Windows ランタイムオブジェクトの配列。

*Server*<br/>
オブジェクトを作成したサーバーの名前。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、操作が失敗した理由を示す HRESULT。

## <a name="moduleregisterwinrtobject"></a><a name="registerwinrtobject"></a>Module:: RegisterWinRTObject

他のアプリケーションが接続できるように、1つまたは複数の Windows ランタイムオブジェクトを登録します。

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>パラメーター

*Server*<br/>
この操作によって影響を受けるオブジェクトのサブセットを指定する名前。

*activatableClassIds*<br/>
登録するアクティブ化可能な Clsid の配列。

*cookie*<br/>
登録されたクラスオブジェクトを識別する値。 この値は、後で登録を取り消すために使用されます。

*count*<br/>
登録するオブジェクトの数。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、CO_E_OBJISREG など、操作が失敗した理由を示すエラー HRESULT が表示されます。

## <a name="modulereleasenotifier_"></a><a name="releasenotifier"></a>Module:: releaseNotifier_

オブジェクトへのポインターを保持 `ReleaseNotifier` します。

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="moduleterminate"></a><a name="terminate"></a>Module:: Terminate

モジュールによってインスタンス化されたすべてのファクトリをシャットダウンさせます。

```cpp
void Terminate();
```

### <a name="remarks"></a>解説

キャッシュ内のファクトリを解放します。

## <a name="moduleunregistercomobject"></a><a name="unregistercomobject"></a>Module:: UnregisterCOMObject

1つ以上の COM オブジェクトの登録を解除します。これにより、他のアプリケーションが接続できなくなります。

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>パラメーター

*Server*<br/>
未使用

*cookies*<br/>
登録を解除するクラスオブジェクトを識別する値へのポインターの配列。 配列は、 [RegisterCOMObject](#registercomobject)メソッドによって作成されました。

*count*<br/>
登録を解除するクラスの数。

### <a name="return-value"></a>戻り値

この操作が成功した場合は S_OK。それ以外の場合は、操作が失敗した理由を示すエラー HRESULT。

## <a name="moduleunregisterobjects"></a><a name="unregisterobjects"></a>Module:: UnregisterObjects

他のアプリケーションが接続できないように、指定したモジュール内のオブジェクトの登録を解除します。

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>パラメーター

*第*<br/>
モジュールへのポインター。

*Server*<br/>
この操作によって影響を受けるオブジェクトのサブセットを指定する修飾名。

### <a name="return-value"></a>戻り値

この操作が成功した場合は S_OK。それ以外の場合は、この操作が失敗した理由を示すエラー HRESULT。

## <a name="moduleunregisterwinrtobject"></a><a name="unregisterwinrtobject"></a>Module:: UnregisterWinRTObject

他のアプリケーションが接続できないように、1つまたは複数の Windows ランタイムオブジェクトの登録を解除します。

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>パラメーター

*cookie*<br/>
登録を取り消すクラスオブジェクトを識別する値へのポインター。
