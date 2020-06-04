---
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
ms.openlocfilehash: 9cb4e166628a6b5e7671494446d467e73c9f8cc3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371387"
---
# <a name="invokehelper-structure"></a>InvokeHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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

*インターフェイス*<br/>
デリゲート インターフェイスの型。

*コールバック*<br/>
イベント ハンドラー関数の型。

*argカウント*<br/>
特殊化の引数の`InvokeHelper`数。

## <a name="remarks"></a>解説

指定した数と引数`Invoke()`の型に基づいてメソッドを実装します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前     | 説明
-------- | -----------------------------------------------------------------------------
`Traits` | 各イベント ハンドラー引数の型を定義するクラスのシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                        | 説明
------------------------------------------- | -------------------------------------------------------
[起動ヘルパー::起動ヘルパー](#invokehelper) | `InvokeHelper` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                            | 説明
------------------------------- | -----------------------------------------------------------------------------------
[起動ヘルパー::呼び出し](#invoke) | 指定した数の引数を含むシグネチャを持つイベント ハンドラーを呼び出します。

### <a name="public-data-members"></a>パブリック データ メンバー

名前                                 | 説明
------------------------------------ | ----------------------------------------------------------
[ヘルパーを呼び出します:callback_](#callback) | イベントが発生したときに呼び出すイベント ハンドラーを表します。

## <a name="inheritance-hierarchy"></a>継承階層

`InvokeHelper`

## <a name="requirements"></a>必要条件

**ヘッダー:** イベント.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="invokehelpercallback_"></a><a name="callback"></a>ヘルパーを呼び出します:callback_

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
TCallback callback_;
```

### <a name="remarks"></a>解説

イベントが発生したときに呼び出すイベント ハンドラーを表します。

テンプレート`TCallback`パラメーターは、イベント ハンドラーの型を指定します。

## <a name="invokehelperinvoke"></a><a name="invoke"></a>起動ヘルパー::呼び出し

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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
引数 1.

*arg2*<br/>
引数 2.

*arg3*<br/>
引数 3.

*arg4*<br/>
引数 4.

*arg5*<br/>
引数 5.

*arg6*<br/>
引数 6.

*arg7*<br/>
引数 7.

*arg8*<br/>
引数 8.

*arg9*<br/>
引数 9.

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、エラーを説明する HRESULT。

### <a name="remarks"></a>解説

指定した数の引数を含むシグネチャを持つイベント ハンドラーを呼び出します。

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a>起動ヘルパー::起動ヘルパー

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>パラメーター

*コールバック*<br/>
イベント ハンドラー。

### <a name="remarks"></a>解説

`InvokeHelper` クラスの新しいインスタンスを初期化します。

テンプレート`TCallback`パラメーターは、イベント ハンドラーの型を指定します。
