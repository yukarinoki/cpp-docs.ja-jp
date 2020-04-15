---
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
ms.openlocfilehash: 0655caeb3f49a18e9c57c78f0008901aaaedda4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368707"
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
0 番目のインターフェイス。

*I1*<br/>
最初のインターフェイス。

*I2*<br/>
2 番目のインターフェイス。

## <a name="remarks"></a>解説

`ActivationFactory`には、インターフェイスの登録メソッドと基本`IActivationFactory`機能が用意されています。 `ActivationFactory`また、カスタム ファクトリ実装を提供することもできます。

次のコードフラグメントは、ActivationFactory の使用方法をシンボル的に示しています。

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

次のコードは[、Implements](implements-structure.md)構造体を使用して 3 つ以上のインターフェイス ID を指定する方法を示しています。

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                       | 説明
---------------------------------------------------------- | ------------------------------------------
[アクティベーションファクトリー::アクティベーションファクトリー](#activationfactory) | `ActivationFactory` クラスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                           | 説明
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[アクティベーションファクトリー::AddRef](#addref)                           | 現在`ActivationFactory`のオブジェクトの参照カウントをインクリメントします。
[アクティベーションファクトリー::ゲットイイド](#getiids)                         | 実装されたインターフェイス ID の配列を取得します。
[アクティベーションファクトリー::ランタイムクラス名](#getruntimeclassname) | 現在`ActivationFactory`のインスタンスを作成するオブジェクトのランタイム クラス名を取得します。
[アクティベーションファクトリー::ゲットトラストレベル](#gettrustlevel)             | 現在`ActivationFactory`のインスタンスを作成するオブジェクトの信頼レベルを取得します。
[アクティベーションファクトリー::クエリインターフェイス](#queryinterface)           | 指定したインターフェイスへのポインターを取得します。
[アクティベーションファクトリー::リリース](#release)                         | 現在`ActivationFactory`のオブジェクトの参照カウントをデクリメントします。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a>アクティベーションファクトリー::アクティベーションファクトリー

`ActivationFactory` クラスを初期化します。

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a>アクティベーションファクトリー::AddRef

現在`ActivationFactory`のオブジェクトの参照カウントをインクリメントします。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="activationfactorygetiids"></a><a name="getiids"></a>アクティベーションファクトリー::ゲットイイド

実装されたインターフェイス ID の配列を取得します。

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>パラメーター

*iidカウント*<br/>
この操作が完了すると *、iids*配列内のインターエース ID の数。

*Iid*<br/>
この操作が完了すると、実装されたインターフェイス ID の配列。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 E_OUTOFMEMORYは、HRESULT の可能性があります。

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a>アクティベーションファクトリー::ランタイムクラス名

現在`ActivationFactory`のインスタンスを作成するオブジェクトのランタイム クラス名を取得します。

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>パラメーター

*ランタイム名*<br/>
この操作が完了すると、現在`ActivationFactory`のインスタンスを作成するオブジェクトのランタイム クラス名を含む文字列へのハンドル。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a>アクティベーションファクトリー::ゲットトラストレベル

現在`ActivationFactory`のインスタンスを作成するオブジェクトの信頼レベルを取得します。

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>パラメーター

*トラストルヴル*<br/>
この操作が完了すると、`ActivationFactory`インスタンス化するランタイム クラスの信頼レベル。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合はアサーション エラーが発生し *、trustLvl*が に`FullTrust`設定されます。

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a>アクティベーションファクトリー::クエリインターフェイス

指定したインターフェイスへのポインターを取得します。

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*オブジェクト*<br/>
この操作が完了すると、パラメータ*riid*で指定されたインターフェイスへのポインタ。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="activationfactoryrelease"></a><a name="release"></a>アクティベーションファクトリー::リリース

現在`ActivationFactory`のオブジェクトの参照カウントをデクリメントします。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。
