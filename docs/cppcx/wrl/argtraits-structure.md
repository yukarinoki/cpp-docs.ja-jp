---
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
ms.openlocfilehash: 16c44d861ebbbc98fa1bffb62a00d1989c0c803c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377170"
---
# <a name="argtraits-structure"></a>ArgTraits 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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

*関数*<br/>
メソッド`Invoke`シグネチャに一致しない ArgTraits 構造体の型名パラメーター。

*インターフェイス*<br/>
デリゲート インターフェイス。

*TArg1*<br/>
メソッドの最初の引数の`Invoke`型。

*TArg2*<br/>
メソッドの 2 番目の引数`Invoke`の型。

*TArg3*<br/>
メソッドの 3 番目の引数`Invoke`の型。

*TArg4*<br/>
メソッドの 4 番目の引数`Invoke`の型。

*TArg5*<br/>
メソッドの 5 番目の引数`Invoke`の型。

*TArg6*<br/>
メソッドの 6 番目の引数`Invoke`の型。

*TArg7*<br/>
メソッドの 7 番目の引数の`Invoke`型。

*TArg8*<br/>
メソッドの 8 番目の引数`Invoke`の型。

*TArg9*<br/>
メソッドの第 9 引数の`Invoke`型。

## <a name="remarks"></a>解説

構造体`ArgTraits`は、指定されたデリゲート インターフェイスと、指定した数のパラメーターを持つ匿名メンバー関数を宣言します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前       | 説明
---------- | ----------------------
`Arg1Type` | TArg1 の型定義。
`Arg2Type` | TArg2 の型定義。
`Arg3Type` | TArg3 の型定義。
`Arg4Type` | TArg4 の型定義。
`Arg5Type` | TArg5 の型定義。
`Arg6Type` | TArg6 の型定義。
`Arg7Type` | TArg7 の型定義。
`Arg8Type` | TArg8 の型定義。
`Arg9Type` | TArg9 の型定義。

### <a name="public-constants"></a>パブリック定数

名前                     | 説明
------------------------ | ---------------------------------------------------------------------------------------
[アルクトレイツ::アルゴス](#args) | デリゲート インターフェイスの`Invoke`メソッドのパラメーター数を保持します。

## <a name="inheritance-hierarchy"></a>継承階層

`ArgTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** イベント.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="argtraitsargs"></a><a name="args"></a>アルクトレイツ::アルゴス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
static const int args = -1;
```

### <a name="remarks"></a>解説

デリゲート インターフェイスの`Invoke`メソッドのパラメーター数を保持します。 1`args`と等しい場合、メソッド シグネチャに一致`Invoke`する値は存在しません。
