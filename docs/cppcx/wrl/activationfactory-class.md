---
description: '詳細情報: ActivationFactory クラス'
title: ActivationFactory クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 7204a3c2f981947a03efba648dd91b69d582fee1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287841"
---
# <a name="activationfactory-class"></a>ActivationFactory クラス

1 つ以上のクラスを Windows ランタイムによってアクティブ化できるようにします。

## <a name="syntax"></a>構文

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>パラメーター

*I0*<br/>
取り出しインターフェイス。

*I1*<br/>
最初のインターフェイス。

*I2*<br/>
2番目のインターフェイス。

## <a name="remarks"></a>解説

`ActivationFactory` インターフェイスの登録メソッドと基本機能を提供し `IActivationFactory` ます。 `ActivationFactory` では、カスタムファクトリ実装を提供することもできます。

次のコード片は、ActivationFactory の使用方法を示しています。

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

次のコードフラグメントは、 [Implements](implements-structure.md) 構造体を使用して3つ以上のインターフェイス id を指定する方法を示しています。

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                       | 説明
---------------------------------------------------------- | ------------------------------------------
[ActivationFactory:: ActivationFactory](#activationfactory) | `ActivationFactory` クラスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                           | 説明
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[ActivationFactory:: AddRef](#addref)                           | 現在のオブジェクトの参照カウントをインクリメントし `ActivationFactory` ます。
[ActivationFactory:: GetIids](#getiids)                         | 実装されたインターフェイス Id の配列を取得します。
[ActivationFactory:: GetRuntimeClassName](#getruntimeclassname) | 現在のがインスタンス化するオブジェクトのランタイムクラス名を取得し `ActivationFactory` ます。
[ActivationFactory:: GetTrustLevel](#gettrustlevel)             | 現在のがインスタンス化するオブジェクトの信頼レベルを取得し `ActivationFactory` ます。
[ActivationFactory:: QueryInterface](#queryinterface)           | 指定したインターフェイスへのポインターを取得します。
[ActivationFactory:: Release](#release)                         | 現在のオブジェクトの参照カウントをデクリメントし `ActivationFactory` ます。

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

## <a name="requirements"></a>要件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a> ActivationFactory:: ActivationFactory

`ActivationFactory` クラスを初期化します。

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a> ActivationFactory:: AddRef

現在のオブジェクトの参照カウントをインクリメントし `ActivationFactory` ます。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="activationfactorygetiids"></a><a name="getiids"></a> ActivationFactory:: GetIids

実装されたインターフェイス Id の配列を取得します。

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>パラメーター

*iidCount*<br/>
この操作が完了すると、 *iid が* 配列内の相互 ace id の数が表示されます。

*iid が*<br/>
この操作が完了すると、実装されているインターフェイス Id の配列。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 E_OUTOFMEMORY は、エラー HRESULT が発生する可能性があります。

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a> ActivationFactory:: GetRuntimeClassName

現在のがインスタンス化するオブジェクトのランタイムクラス名を取得し `ActivationFactory` ます。

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>パラメーター

*runtimeName*<br/>
この操作が完了すると、現在のがインスタンス化しているオブジェクトのランタイムクラス名を含む文字列へのハンドル `ActivationFactory` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a> ActivationFactory:: GetTrustLevel

現在のがインスタンス化するオブジェクトの信頼レベルを取得し `ActivationFactory` ます。

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>パラメーター

*trustLvl*<br/>
この操作が完了すると、がインスタンス化するランタイムクラスの信頼レベル `ActivationFactory` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、アサーションエラーが生成され、 *trustLvl* はに設定され `FullTrust` ます。

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a> ActivationFactory:: QueryInterface

指定したインターフェイスへのポインターを取得します。

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ppvObject*<br/>
この操作が完了したら、パラメーター *riid* によって指定されたインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="activationfactoryrelease"></a><a name="release"></a> ActivationFactory:: Release

現在のオブジェクトの参照カウントをデクリメントし `ActivationFactory` ます。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。
