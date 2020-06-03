---
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
ms.openlocfilehash: 64b4124ba3c60fdcb53fc29c7b791c0f73a49579
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376228"
---
# <a name="runtimeclass-class"></a>RuntimeClass クラス

指定したインターフェイスを継承し、指定された Windows ランタイム、クラシック COM、および弱い参照のサポートを提供する WinRT または COM クラスを表します。

このクラスは、WinRT クラスと COM クラスの定型的な`QueryInterface`実装`AddRef`を`Release`提供し、モジュールの参照カウントを管理し、アクティブ化可能なオブジェクトのクラス ファクトリを提供するためのサポートを提供します。

## <a name="syntax"></a>構文

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>パラメーター

*クラスフラグ*<br/>
省略可能なパラメーター。 1 つ以上の[ランタイムクラスタイプ](runtimeclasstype-enumeration.md)列挙値の組み合わせ。 マクロ`__WRL_CONFIGURATION_LEGACY__`を定義して、プロジェクト内のすべてのランタイム クラスの classFlags の既定値を変更できます。 定義されている場合、既定では、RuntimeClass インスタンスは非アジャイルです。 定義されていない場合、既定では、RuntimeClass インスタンスはアジャイルです。 あいまいさを避けるために、常に in `Microsoft::WRL::FtmBase` `TInterfaces`または`RuntimeClassType::InhibitFtmBase`を指定します。 ただし、両方を使用すると、オブジェクトはアジャイルになります。

*T インターフェイス*<br/>
オブジェクトが実装するインターフェイスのリストは、 `IUnknown``IInspectable`を超えて実装されるか、[または RuntimeClassType](runtimeclasstype-enumeration.md)によって制御されるその他のインターフェイスです。 また、派生する他のクラスを列挙し、特に`Microsoft::WRL::FtmBase`オブジェクトをアジャイルにして実装`IMarshal`させる場合もあります。

## <a name="members"></a>メンバー

`RuntimeClassInitialize`<br/>
テンプレート関数を使用してオブジェクトを構築する`MakeAndInitialize`場合にオブジェクトを初期化する関数。 オブジェクトが正常に初期化された場合はS_OK、初期化に失敗した場合は COM エラー コードを返します。 COM エラー コードは、`MakeAndInitialize`の戻り値として伝達されます。 テンプレート関数を`RuntimeClassInitialize`使用してオブジェクトを構築する`Make`場合、メソッドは呼び出されません。

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前                                               | 説明                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [クラス::ランタイムクラス](#runtimeclass)        | クラスの現在のインスタンスを初期化`RuntimeClass`します。   |
| [ランタイムクラス:~ランタイムクラス](#tilde-runtimeclass) | クラスの現在のインスタンスを初期化解除`RuntimeClass`します。 |

### <a name="public-methods"></a>パブリック メソッド

| 名前                                                      | 説明                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [ランタイムクラス::AddRef](#addref)                           | 現在`RuntimeClass`のオブジェクトの参照カウントをインクリメントします。                              |
| [クラス::Dクレメントリファレンス](#decrementreference)   | 現在`RuntimeClass`のオブジェクトの参照カウントを減算します。                              |
| [ランタイムクラス::取得Ids](#getiids)                         | 現在`RuntimeClass`のオブジェクトによって実装されるインターフェイス ID を格納できる配列を取得します。 |
| [クラスクラス::取得ランタイムクラス名](#getruntimeclassname) | 現在`RuntimeClass`のオブジェクトのランタイム クラス名を取得します。                                  |
| [クラス::ゲットトラストレベル](#gettrustlevel)             | 現在`RuntimeClass`のオブジェクトの信頼レベルを取得します。                                         |
| [ランタイムクラス::ゲットウィークリファレンス](#getweakreference)       | 現在`RuntimeClass`のオブジェクトの弱参照オブジェクトへのポインターを取得します。                 |
| [クラス::内部追加Ref](#internaladdref)           | 現在`RuntimeClass`のオブジェクトへの参照カウントをインクリメントします。                               |
| [クラス::クエリインターフェイス](#queryinterface)           | 指定したインターフェイス ID へのポインターを取得します。                                                 |
| [ランタイムクラス::リリース](#release)                         | 現在`RuntimeClass`のオブジェクトに対して COM 解放操作を実行します。                             |

## <a name="inheritance-hierarchy"></a>継承階層

これは実装の詳細になります。

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** Microsoft::WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a>ランタイムクラス:~ランタイムクラス

クラスの現在のインスタンスを初期化解除`RuntimeClass`します。

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a>ランタイムクラス::AddRef

現在`RuntimeClass`のオブジェクトの参照カウントをインクリメントします。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a>クラス::Dクレメントリファレンス

現在`RuntimeClass`のオブジェクトの参照カウントを減算します。

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="runtimeclassgetiids"></a><a name="getiids"></a>ランタイムクラス::取得Ids

現在`RuntimeClass`のオブジェクトによって実装されるインターフェイス ID を格納できる配列を取得します。

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>パラメーター

*iidカウント*<br/>
この操作が完了すると、配列*iids*内の要素の合計数。

*Iid*<br/>
この操作が完了すると、インターフェイス ID の配列へのポインター。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、E_OUTOFMEMORY。

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a>クラスクラス::取得ランタイムクラス名

現在`RuntimeClass`のオブジェクトのランタイム クラス名を取得します。

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>パラメーター

*ランタイム名*<br/>
この操作が完了すると、ランタイム クラス名。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

定義されていない場合`__WRL_STRICT__`、アサート`__WRL_FORCE_INSPECTABLE_CLASS_MACRO__`エラーが発生します。

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a>クラス::ゲットトラストレベル

現在`RuntimeClass`のオブジェクトの信頼レベルを取得します。

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>パラメーター

*トラストルヴル*<br/>
この操作が完了すると、現在`RuntimeClass`のオブジェクトの信頼レベル。

### <a name="return-value"></a>戻り値

常にS_OK。

### <a name="remarks"></a>解説

定義されていない場合`__WRL_STRICT__`、アサート`__WRL_FORCE_INSPECTABLE_CLASS_MACRO__`エラーが発生します。

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a>ランタイムクラス::ゲットウィークリファレンス

現在`RuntimeClass`のオブジェクトの弱参照オブジェクトへのポインターを取得します。

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>パラメーター

*Weakreference*<br/>
この操作が完了すると、弱参照オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

常にS_OK。

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a>クラス::内部追加Ref

現在`RuntimeClass`のオブジェクトへの参照カウントをインクリメントします。

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>戻り値

結果の参照カウント。

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a>クラス::クエリインターフェイス

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

*オブジェクト*<br/>
このオペレーションが完了すると *、riid*パラメーターで指定されたインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="runtimeclassrelease"></a><a name="release"></a>ランタイムクラス::リリース

現在`RuntimeClass`のオブジェクトに対して COM 解放操作を実行します。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

### <a name="remarks"></a>解説

参照カウントがゼロになると、`RuntimeClass`オブジェクトは削除されます。

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a>クラス::ランタイムクラス

クラスの現在のインスタンスを初期化`RuntimeClass`します。

```cpp
RuntimeClass();
```
