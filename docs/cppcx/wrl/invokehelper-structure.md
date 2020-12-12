---
description: 詳細については、「InvokeHelper 構造体」を参照してください。
title: InvokeHelper 構造体
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 0b9bb8abb59cce5a3c25d795d0946ffbe88d0076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299021"
---
# <a name="invokehelper-structure"></a>InvokeHelper 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>パラメーター

*TDelegateInterface*<br/>
デリゲートインターフェイス型。

*TCallback*<br/>
イベントハンドラー関数の型。

*argCount*<br/>
特殊化されたの引数の数 `InvokeHelper` 。

## <a name="remarks"></a>解説

`Invoke()`指定された引数の数と型に基づいて、メソッドの実装を提供します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前     | 説明
-------- | -----------------------------------------------------------------------------
`Traits` | 各イベントハンドラーの引数の型を定義するクラスのシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                        | 説明
------------------------------------------- | -------------------------------------------------------
[InvokeHelper:: InvokeHelper](#invokehelper) | `InvokeHelper` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                            | 説明
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper:: Invoke](#invoke) | 指定された数の引数を含むシグネチャを持つイベントハンドラーを呼び出します。

### <a name="public-data-members"></a>パブリック データ メンバー

名前                                 | 説明
------------------------------------ | ----------------------------------------------------------
[InvokeHelper:: callback_](#callback) | イベントが発生したときに呼び出されるイベントハンドラーを表します。

## <a name="inheritance-hierarchy"></a>継承階層

`InvokeHelper`

## <a name="requirements"></a>要件

**ヘッダー:** イベント .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="invokehelpercallback_"></a><a name="callback"></a> InvokeHelper:: callback_

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
TCallback callback_;
```

### <a name="remarks"></a>解説

イベントが発生したときに呼び出されるイベントハンドラーを表します。

`TCallback`テンプレートパラメーターは、イベントハンドラーの種類を指定します。

## <a name="invokehelperinvoke"></a><a name="invoke"></a> InvokeHelper:: Invoke

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>パラメーター

*arg1*<br/>
引数1。

*arg2*<br/>
引数2。

*arg3*<br/>
引数3。

*arg4*<br/>
引数4。

*arg5*<br/>
引数5。

*arg6*<br/>
引数6。

*arg7*<br/>
引数7。

*arg8*<br/>
引数8。

*arg9*<br/>
引数9。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーを説明する HRESULT です。

### <a name="remarks"></a>解説

指定された数の引数を含むシグネチャを持つイベントハンドラーを呼び出します。

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a> InvokeHelper:: InvokeHelper

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>パラメーター

*コール*<br/>
イベント ハンドラー。

### <a name="remarks"></a>解説

`InvokeHelper` クラスの新しいインスタンスを初期化します。

`TCallback`テンプレートパラメーターは、イベントハンドラーの種類を指定します。
