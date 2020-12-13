---
description: '詳細情報: RuntimeClass クラス'
title: RuntimeClass クラス
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: f62eec0b5ac9b8fc8ecac390ea07077743fdcb51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330759"
---
# <a name="runtimeclass-class"></a>RuntimeClass クラス

指定されたインターフェイスを継承し、指定された Windows ランタイム、クラシック COM、および弱い参照サポートを提供する WinRT クラスまたは COM クラスを表します。

このクラスは、、などの実装を提供する WinRT クラスと COM クラスの定型的な実装を提供 `QueryInterface` `AddRef` `Release` します。は、モジュールの参照カウントを管理し、アクティブ化可能なオブジェクトのクラスファクトリの提供をサポートしています。

## <a name="syntax"></a>構文

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>パラメーター

*classFlags*<br/>
省略可能なパラメーター。 1つ以上の [RuntimeClassType](runtimeclasstype-enumeration.md) 列挙値の組み合わせ。 マクロを定義すると、 `__WRL_CONFIGURATION_LEGACY__` プロジェクト内のすべてのランタイムクラスの classFlags の既定値を変更できます。 定義されている場合、RuntimeClass インスタンスは既定では非アジャイルです。 定義されていない場合、RuntimeClass インスタンスは既定でアジャイルになります。 あいまいさを避けるためには、常にまたはのを指定し `Microsoft::WRL::FtmBase` `TInterfaces` `RuntimeClassType::InhibitFtmBase` ます。 InhibitFtmBase と FtmBase の両方が使用されている場合、オブジェクトは agile になります。

*TInterfaces*<br/>
オブジェクトが実装するインターフェイスのリスト、 `IUnknown` `IInspectable` または [RuntimeClassType](runtimeclasstype-enumeration.md)によって制御される他のインターフェイスの一覧。 また、オブジェクトのアジャイルを作成して実装するために、から派生する他のクラスを一覧表示することもでき `Microsoft::WRL::FtmBase` `IMarshal` ます。

## <a name="members"></a>メンバー

`RuntimeClassInitialize`<br/>
`MakeAndInitialize`オブジェクトを構築するためにテンプレート関数が使用されている場合に、オブジェクトを初期化する関数。 オブジェクトが正常に初期化された場合は S_OK を返し、初期化に失敗した場合は COM エラーコードを返します。 COM エラーコードは、の戻り値として反映され `MakeAndInitialize` ます。 `RuntimeClassInitialize`テンプレート関数を使用してオブジェクトを構築する場合、メソッドは呼び出されないことに注意して `Make` ください。

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前                                               | 説明                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass:: RuntimeClass](#runtimeclass)        | クラスの現在のインスタンスを初期化し `RuntimeClass` ます。   |
| [RuntimeClass:: ~ RuntimeClass](#tilde-runtimeclass) | クラスの現在のインスタンスを初期化解除 `RuntimeClass` します。 |

### <a name="public-methods"></a>パブリック メソッド

| 名前                                                      | 説明                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass:: AddRef](#addref)                           | 現在のオブジェクトの参照カウントをインクリメントし `RuntimeClass` ます。                              |
| [RuntimeClass::D ecrementReference](#decrementreference)   | 現在のオブジェクトの参照カウントをデクリメントし `RuntimeClass` ます。                              |
| [RuntimeClass:: GetIids](#getiids)                         | 現在のオブジェクトによって実装されているインターフェイス Id を格納できる配列を取得し `RuntimeClass` ます。 |
| [RuntimeClass:: GetRuntimeClassName](#getruntimeclassname) | 現在のオブジェクトのランタイムクラス名を取得し `RuntimeClass` ます。                                  |
| [RuntimeClass:: GetTrustLevel](#gettrustlevel)             | 現在のオブジェクトの信頼レベルを取得し `RuntimeClass` ます。                                         |
| [RuntimeClass:: GetWeakReference](#getweakreference)       | 現在のオブジェクトの弱参照オブジェクトへのポインターを取得し `RuntimeClass` ます。                 |
| [RuntimeClass:: InternalAddRef](#internaladdref)           | 現在のオブジェクトに参照カウントをインクリメントし `RuntimeClass` ます。                               |
| [RuntimeClass:: QueryInterface](#queryinterface)           | 指定したインターフェイス ID へのポインターを取得します。                                                 |
| [RuntimeClass:: Release](#release)                         | 現在のオブジェクトに対して COM 解放操作を実行 `RuntimeClass` します。                             |

## <a name="inheritance-hierarchy"></a>継承階層

これは実装の詳細になります。

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a> RuntimeClass:: ~ RuntimeClass

クラスの現在のインスタンスを初期化解除 `RuntimeClass` します。

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a> RuntimeClass:: AddRef

現在のオブジェクトの参照カウントをインクリメントし `RuntimeClass` ます。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a> RuntimeClass::D ecrementReference

現在のオブジェクトの参照カウントをデクリメントし `RuntimeClass` ます。

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="runtimeclassgetiids"></a><a name="getiids"></a> RuntimeClass:: GetIids

現在のオブジェクトによって実装されているインターフェイス Id を格納できる配列を取得し `RuntimeClass` ます。

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>パラメーター

*iidCount*<br/>
この操作が完了すると、配列 *iid が* 内の要素の合計数になります。

*iid が*<br/>
この操作が完了したときに、インターフェイス Id の配列へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、E_OUTOFMEMORY ます。

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a> RuntimeClass:: GetRuntimeClassName

現在のオブジェクトのランタイムクラス名を取得し `RuntimeClass` ます。

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>パラメーター

*runtimeName*<br/>
この操作が完了すると、ランタイムクラス名が指定されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

Assert エラーは、またはが定義されていない場合に生成され `__WRL_STRICT__` `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` ます。

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a> RuntimeClass:: GetTrustLevel

現在のオブジェクトの信頼レベルを取得し `RuntimeClass` ます。

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>パラメーター

*trustLvl*<br/>
この操作が完了したときに、現在のオブジェクトの信頼レベル `RuntimeClass` 。

### <a name="return-value"></a>戻り値

常に S_OK します。

### <a name="remarks"></a>解説

Assert エラーは、またはが定義されていない場合に生成され `__WRL_STRICT__` `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` ます。

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a> RuntimeClass:: GetWeakReference

現在のオブジェクトの弱参照オブジェクトへのポインターを取得し `RuntimeClass` ます。

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>パラメーター

*weakReference*<br/>
この操作が完了したときに、弱い参照オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

常に S_OK します。

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a> RuntimeClass:: InternalAddRef

現在のオブジェクトに参照カウントをインクリメントし `RuntimeClass` ます。

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>戻り値

結果として得られる参照カウント。

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a> RuntimeClass:: QueryInterface

指定したインターフェイス ID へのポインターを取得します。

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ppvObject*<br/>
この処理が完了したときに、 *riid* パラメーターによって指定されたインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="runtimeclassrelease"></a><a name="release"></a> RuntimeClass:: Release

現在のオブジェクトに対して COM 解放操作を実行 `RuntimeClass` します。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

参照カウントがゼロになると、 `RuntimeClass` オブジェクトは削除されます。

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a> RuntimeClass:: RuntimeClass

クラスの現在のインスタンスを初期化し `RuntimeClass` ます。

```cpp
RuntimeClass();
```
