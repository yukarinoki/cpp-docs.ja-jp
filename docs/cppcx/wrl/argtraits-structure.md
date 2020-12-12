---
description: '詳細情報: ArgTraits 構造体'
title: ArgTraits 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: b44cd1ff8d5aa4355385629cc08321dfe353e24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175912"
---
# <a name="argtraits-structure"></a>ArgTraits 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>パラメーター

*TMemberFunction*<br/>
任意のメソッドシグネチャと一致しない ArgTraits 構造体の Typename パラメーター `Invoke` 。

*TDelegateInterface*<br/>
デリゲートインターフェイス。

*TArg1*<br/>
メソッドの第1引数の型 `Invoke` 。

*TArg2*<br/>
メソッドの2番目の引数の型 `Invoke` 。

*TArg3*<br/>
メソッドの3番目の引数の型 `Invoke` 。

*TArg4*<br/>
メソッドの4番目の引数の型 `Invoke` 。

*TArg5*<br/>
メソッドの5番目の引数の型 `Invoke` 。

*TArg6*<br/>
メソッドの6番目の引数の型 `Invoke` 。

*TArg7*<br/>
メソッドの7番目の引数の型 `Invoke` 。

*TArg8*<br/>
メソッドの8番目の引数の型 `Invoke` 。

*TArg9*<br/>
メソッドの9番目の引数の型 `Invoke` 。

## <a name="remarks"></a>解説

構造体は、指定された `ArgTraits` デリゲートインターフェイスと、指定された数のパラメーターを持つ匿名メンバー関数を宣言します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前       | 説明
---------- | ----------------------
`Arg1Type` | TArg1 の typedef。
`Arg2Type` | TArg2 の typedef。
`Arg3Type` | TArg3 の typedef。
`Arg4Type` | TArg4 の typedef。
`Arg5Type` | TArg5 の typedef。
`Arg6Type` | TArg6 の typedef。
`Arg7Type` | TArg7 の typedef。
`Arg8Type` | TArg8 の typedef。
`Arg9Type` | TArg9 の typedef。

### <a name="public-constants"></a>パブリック定数

名前                     | 説明
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits:: args](#args) | デリゲートインターフェイスのメソッドのパラメーター数のカウントを保持 `Invoke` します。

## <a name="inheritance-hierarchy"></a>継承階層

`ArgTraits`

## <a name="requirements"></a>要件

**ヘッダー:** イベント .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="argtraitsargs"></a><a name="args"></a> ArgTraits:: args

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
static const int args = -1;
```

### <a name="remarks"></a>解説

デリゲートインターフェイスのメソッドのパラメーター数のカウントを保持 `Invoke` します。 が `args` -1 の場合、メソッドシグネチャに一致することはできません `Invoke` 。
