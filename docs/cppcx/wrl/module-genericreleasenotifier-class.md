---
title: Module::GenericReleaseNotifier クラス
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::callback_
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
- module/Microsoft::WRL::Module::GenericReleaseNotifier::Invoke
helpviewer_keywords:
- Microsoft::WRL::Module::GenericReleaseNotifier class
- Microsoft::WRL::Module::GenericReleaseNotifier::callback_ data member
- Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier, constructor
- Microsoft::WRL::Module::GenericReleaseNotifier::Invoke method
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
ms.openlocfilehash: e3cc8e33d596fb1d3ecc4a94fee7971a50ffe596
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371300"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier クラス

現在のモジュールの最後のオブジェクトが解放されたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダ、ファンクタ、または関数へのポインターで指定します。

## <a name="syntax"></a>構文

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
イベント ハンドラーの場所を格納するデータ メンバーの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                                                     | 説明
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[モジュール::ジェネリックリリースNotifier::ジェネリックリリースNotifier](#genericreleasenotifier-genericreleasenotifier) | `Module::GenericReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                                     | 説明
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[モジュール::ジェネリックリリースNotifier::呼び出し](#genericreleasenotifier-invoke) | 現在`Module::GenericReleaseNotifier`のオブジェクトに関連付けられているイベント ハンドラーを呼び出します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                                                          | 説明
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[モジュール::ジェネリックリリースNotifier::callback_](#genericreleasenotifier-callback) | 現在`Module::GenericReleaseNotifier`のオブジェクトに関連付けられているラムダ、ファンクタ、または関数へのポインターイベント ハンドラーを保持します。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="modulegenericreleasenotifiercallback_"></a><a name="genericreleasenotifier-callback"></a>モジュール::ジェネリックリリースNotifier::callback_

現在`Module::GenericReleaseNotifier`のオブジェクトに関連付けられているラムダ、ファンクタ、または関数へのポインターイベント ハンドラーを保持します。

```cpp
T callback_;
```

## <a name="modulegenericreleasenotifiergenericreleasenotifier"></a><a name="genericreleasenotifier-genericreleasenotifier"></a>モジュール::ジェネリックリリースNotifier::ジェネリックリリースNotifier

`Module::GenericReleaseNotifier` クラスの新しいインスタンスを初期化します。

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>パラメーター

*コールバック*<br/>
かっこ関数演算子 ( )`()`で呼び出すことができるラムダ、ファンクタ、または関数へのポインターのイベント ハンドラー。

*リリース*<br/>
基`true`になるモジュールの呼び出しを有効にすることを指定します: [:リリースNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release)メソッド;それ以外の`false`場合は、 を指定します。

## <a name="modulegenericreleasenotifierinvoke"></a><a name="genericreleasenotifier-invoke"></a>モジュール::ジェネリックリリースNotifier::呼び出し

現在`Module::GenericReleaseNotifier`のオブジェクトに関連付けられているイベント ハンドラーを呼び出します。

```cpp
void Invoke();
```
