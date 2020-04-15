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
ms.openlocfilehash: afd2edacefdf5d62b50a03c0a8c37f13ee5d9c9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371318"
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

*モジュールタイプ*<br/>
1 つ以上の[ModuleType](moduletype-enumeration.md)列挙値の組み合わせ。

## <a name="members"></a>メンバー

### <a name="protected-classes"></a>保護されたクラス

名前                                                                                | 説明
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[モジュール::ジェネリックリリースNotifier](module-genericreleasenotifier-class.md) | 現在のモジュールの最後のオブジェクトが解放されたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダ、ファンクタ、または関数へのポインターで指定します。
[モジュール::メソッドリリースNotifier](module-methodreleasenotifier-class.md)   | 現在のモジュールの最後のオブジェクトが解放されたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、オブジェクトとそのポインターからメソッドへのメンバーによって指定されます。
[モジュール::リリースNotifier](module-releasenotifier-class.md)               | モジュール内の最後のオブジェクトが解放されたときに、イベント ハンドラーを呼び出します。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                             | 説明
-------------------------------- | -----------------------------------------------------------
[モジュール::~モジュール](#tilde-module) | クラスの現在のインスタンスを初期化解除`Module`します。

### <a name="protected-constructors"></a>プロテクト コンストラクター

名前                      | 説明
------------------------- | ---------------------------------------------------
[モジュール::モジュール](#module) | `Module` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                    | 説明
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[モジュール::作成](#create)                               | モジュールのインスタンスを作成します。
[モジュール::Dオブジェクトカウント](#decrementobjectcount)   | モジュールによって追跡されるオブジェクトの数を減分します。
[モジュール::取得アクティベーションファクトリー](#getactivationfactory)   | モジュールのアクティベーション ファクトリを取得します。
[モジュール::Getクラスオブジェクト](#getclassobject)               | クラス ファクトリのキャッシュを取得します。
[モジュール::ゲットモジュール](#getmodule)                         | モジュールのインスタンスを作成します。
[モジュール::オブジェクト数](#getobjectcount)               | このモジュールによって管理されるオブジェクトの数を取得します。
[モジュール::インクリメントオブジェクトカウント](#incrementobjectcount)   | モジュールによって追跡されるオブジェクトの数をインクリメントします。
[モジュール::レジスタCOMオブジェクト](#registercomobject)         | 他のアプリケーションが COM オブジェクトに接続できるように、1 つ以上の COM オブジェクトを登録します。
[モジュール::レジスタオブジェクト](#registerobjects)             | COM オブジェクトまたは Windows ランタイム オブジェクトを登録し、他のアプリケーションが接続できるようにします。
[モジュール::レジスタウィンRTオブジェクト](#registerwinrtobject)     | 他のアプリケーションが接続できるように、1 つ以上の Windows ランタイム オブジェクトを登録します。
[モジュール::終了](#terminate)                         | モジュールによってインスタンス化されたすべてのファクトリをシャットダウンします。
[モジュール::COMオブジェクトの登録解除](#unregistercomobject)     | 1 つ以上の COM オブジェクトの登録を解除します。
[モジュール::オブジェクトの登録解除](#unregisterobjects)         | 指定したモジュール内のオブジェクトの登録を解除し、他のアプリケーションがオブジェクトに接続できないようにします。
[モジュール::登録解除WinRTオブジェクト](#unregisterwinrtobject) | 1 つ以上の Windows ランタイム オブジェクトの登録を解除して、他のアプリケーションがオブジェクトに接続できないようにします。

### <a name="protected-methods"></a>プロテクト メソッド

名前                      | 説明
------------------------- | --------------------------------
[モジュール::作成](#create) | モジュールのインスタンスを作成します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                         | 説明
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[モジュール::objectCount_](#objectcount)         | [Make](make-function.md)関数を使用して作成されたクラスの数を追跡します。
[モジュール::releaseNotifier_](#releasenotifier) | オブジェクトへのポインターを`ReleaseNotifier`保持します。

### <a name="macros"></a>マクロ

名前                                                                   | 説明
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ActivatableClass](activatableclass-macros.md)              | 指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを設定します。 このマクロは、デフォルトのファクトリパラメータとグループ ID パラメータを指定します。
[ActivatableClassWithFactory](activatableclass-macros.md)   | 指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを設定します。 このマクロを使用すると、特定のファクトリ パラメータを指定できます。
[ActivatableClassWithFactoryEx](activatableclass-macros.md) | 指定したクラスのインスタンスを作成できるファクトリを含む内部キャッシュを設定します。 このマクロを使用すると、特定のファクトリおよびグループ ID パラメータを指定できます。

## <a name="inheritance-hierarchy"></a>継承階層

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="modulemodule"></a><a name="tilde-module"></a>モジュール::~モジュール

クラスの現在のインスタンスを初期化解除`Module`します。

```cpp
virtual ~Module();
```

## <a name="modulecreate"></a><a name="create"></a>モジュール::作成

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

*コールバック*<br/>
モジュールの最後のインスタンス オブジェクトが解放されたときに呼び出されます。

*オブジェクト*<br/>
*オブジェクト*と*メソッド*のパラメータは組み合わせて使用されます。 モジュール内の最後のインスタンス オブジェクトが解放されたときの最後のインスタンス オブジェクトを指します。

*method*<br/>
*オブジェクト*と*メソッド*のパラメータは組み合わせて使用されます。 モジュール内の最後のインスタンス オブジェクトが解放されたときの最後のインスタンス オブジェクトのメソッドへのポイント。

### <a name="return-value"></a>戻り値

モジュールへの参照。

## <a name="moduledecrementobjectcount"></a><a name="decrementobjectcount"></a>モジュール::Dオブジェクトカウント

モジュールによって追跡されるオブジェクトの数を減分します。

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>戻り値

減分演算の前のカウント。

## <a name="modulegetactivationfactory"></a><a name="getactivationfactory"></a>モジュール::取得アクティベーションファクトリー

モジュールのアクティベーション ファクトリを取得します。

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ランタイム クラスの IID。

*ppIFactory*<br/>
指定したランタイム クラスの IActivationFactory。

*Servername*<br/>
現在のモジュール内のクラス ファクトリのサブセットの名前。 アクティブ`nullptr`[に使用](activatableclass-macros.md)されるサーバー名を指定します。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、GetActivationFactory によって返される HRESULT。

## <a name="modulegetclassobject"></a><a name="getclassobject"></a>モジュール::Getクラスオブジェクト

クラス ファクトリのキャッシュを取り返します。

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
クラス ID。

*riid*<br/>
要求するインターフェイス ID。

*Ppv*<br/>
返されたオブジェクトへのポインター。

*Servername*<br/>
`ActivatableClassWithFactory`マクロ 、 、 または`ActivatableClassWithFactoryEx``ActivatableClass`マクロのいずれかで指定されるサーバー名。または`nullptr`、既定のサーバー名を取得します。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

このメソッドは、Windows ランタイムではなく、COM に対してのみ使用します。 このメソッドはメソッドのみを`IClassFactory`公開します。

## <a name="modulegetmodule"></a><a name="getmodule"></a>モジュール::ゲットモジュール

モジュールのインスタンスを作成します。

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>戻り値

モジュールへの参照。

## <a name="modulegetobjectcount"></a><a name="getobjectcount"></a>モジュール::オブジェクト数

このモジュールによって管理されるオブジェクトの数を取得します。

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>戻り値

このモジュールによって管理されているオブジェクトの現在の数。

## <a name="moduleincrementobjectcount"></a><a name="incrementobjectcount"></a>モジュール::インクリメントオブジェクトカウント

モジュールによって追跡されるオブジェクトの数をインクリメントします。

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>戻り値

インクリメント操作の前のカウント。

## <a name="modulemodule"></a><a name="module"></a>モジュール::モジュール

`Module` クラスの新しいインスタンスを初期化します。

```cpp
Module();
```

### <a name="remarks"></a>解説

このコンストラクターは保護されており、`new`キーワードを使用して呼び出すことはできません。 代わりに、[モジュール::GetModule](#getmodule)または[モジュール::作成](#create)のいずれかを呼び出します。

## <a name="moduleobjectcount_"></a><a name="objectcount"></a>モジュール::objectCount_

[Make](make-function.md)関数を使用して作成されたクラスの数を追跡します。

```cpp
volatile long objectCount_;
```

## <a name="moduleregistercomobject"></a><a name="registercomobject"></a>モジュール::レジスタCOMオブジェクト

他のアプリケーションが COM オブジェクトに接続できるように、1 つ以上の COM オブジェクトを登録します。

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);
```

### <a name="parameters"></a>パラメーター

*Servername*<br/>
サーバーの完全修飾名。

*Clsid*<br/>
登録する CLID の配列。

*factories*<br/>
可用性が公開されているクラス オブジェクトの IUnknown インターフェイスの配列。

*cookies*<br/>
操作が完了すると、登録されたクラス オブジェクトを識別する値へのポインターの配列。 これらの値は、後で登録を取り消して使用されます。

*count*<br/>
登録する CLSID の数。

### <a name="return-value"></a>戻り値

S_OK成功の場合。それ以外の場合は、操作が失敗した理由を示す CO_E_OBJISREGなどの HRESULT。

### <a name="remarks"></a>解説

COM オブジェクトは、CLSCTX 列挙体のCLSCTX_LOCAL_SERVER列挙子に登録されます。

登録されたオブジェクトへの接続の種類は、現在の*comflag*テンプレート パラメーターと REGCLS 列挙体のREGCLS_SUSPENDED列挙子の組み合わせによって指定されます。

## <a name="moduleregisterobjects"></a><a name="registerobjects"></a>モジュール::レジスタオブジェクト

COM オブジェクトまたは Windows ランタイム オブジェクトを登録し、他のアプリケーションが接続できるようにします。

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>パラメーター

*モジュール*<br/>
COM または Windows ランタイム オブジェクトの配列。

*Servername*<br/>
オブジェクトを作成したサーバーの名前。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、操作が失敗した理由を示す HRESULT。

## <a name="moduleregisterwinrtobject"></a><a name="registerwinrtobject"></a>モジュール::レジスタウィンRTオブジェクト

他のアプリケーションが接続できるように、1 つ以上の Windows ランタイム オブジェクトを登録します。

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>パラメーター

*Servername*<br/>
この操作の影響を受けるオブジェクトのサブセットを指定する名前。

*アクティブ化可能なクラスId*<br/>
登録するアクティブ化可能な CLID の配列。

*クッキー*<br/>
登録されたクラス オブジェクトを識別する値。 この値は、後で登録を取り消すために使用されます。

*count*<br/>
登録するオブジェクトの数。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、操作が失敗した理由を示すエラー HRESULT (CO_E_OBJISREGなど)。

## <a name="modulereleasenotifier_"></a><a name="releasenotifier"></a>モジュール::releaseNotifier_

オブジェクトへのポインターを`ReleaseNotifier`保持します。

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="moduleterminate"></a><a name="terminate"></a>モジュール::終了

モジュールによってインスタンス化されたすべてのファクトリをシャットダウンします。

```cpp
void Terminate();
```

### <a name="remarks"></a>解説

キャッシュ内のファクトリを解放します。

## <a name="moduleunregistercomobject"></a><a name="unregistercomobject"></a>モジュール::COMオブジェクトの登録解除

1 つ以上の COM オブジェクトの登録を解除します。

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>パラメーター

*Servername*<br/>
(未使用)

*cookies*<br/>
登録解除するクラス オブジェクトを識別する値へのポインターの配列。 配列は[、RegisterCOMObject](#registercomobject)メソッドによって作成されました。

*count*<br/>
登録を解除するクラスの数。

### <a name="return-value"></a>戻り値

この操作が成功した場合はS_OK。それ以外の場合は、操作が失敗した理由を示すエラー HRESULT。

## <a name="moduleunregisterobjects"></a><a name="unregisterobjects"></a>モジュール::オブジェクトの登録解除

指定したモジュール内のオブジェクトの登録を解除し、他のアプリケーションがオブジェクトに接続できないようにします。

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>パラメーター

*モジュール*<br/>
モジュールへのポインター。

*Servername*<br/>
この操作の影響を受けるオブジェクトのサブセットを指定する修飾名。

### <a name="return-value"></a>戻り値

この操作が成功した場合はS_OK。それ以外の場合は、この操作が失敗した理由を示すエラー HRESULT。

## <a name="moduleunregisterwinrtobject"></a><a name="unregisterwinrtobject"></a>モジュール::登録解除WinRTオブジェクト

1 つ以上の Windows ランタイム オブジェクトの登録を解除して、他のアプリケーションがオブジェクトに接続できないようにします。

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>パラメーター

*クッキー*<br/>
登録を取り消すクラス オブジェクトを識別する値へのポインター。
