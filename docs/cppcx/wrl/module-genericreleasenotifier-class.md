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
ms.openlocfilehash: 7437f4e1f6874d4c708780a146e1761ac6d98305
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225736"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier クラス

現在のモジュールの最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。 イベントハンドラーは、ラムダ、ファンクタ、またはポインターから関数によって指定されます。

## <a name="syntax"></a>構文

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
イベントハンドラーの場所を格納しているデータメンバーの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                                                     | [説明]
-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: GenericReleaseNotifier](#genericreleasenotifier-genericreleasenotifier) | `Module::GenericReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                                     | [説明]
------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: Invoke](#genericreleasenotifier-invoke) | 現在のオブジェクトに関連付けられているイベントハンドラーを呼び出し `Module::GenericReleaseNotifier` ます。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                                                          | [説明]
----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------
[Module:: GenericReleaseNotifier:: callback_](#genericreleasenotifier-callback) | 現在のオブジェクトに関連付けられているラムダ、ファンクタ、またはポインターから関数へのイベントハンドラーを保持し `Module::GenericReleaseNotifier` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="modulegenericreleasenotifiercallback_"></a><a name="genericreleasenotifier-callback"></a>Module:: GenericReleaseNotifier:: callback_

現在のオブジェクトに関連付けられているラムダ、ファンクタ、またはポインターから関数へのイベントハンドラーを保持し `Module::GenericReleaseNotifier` ます。

```cpp
T callback_;
```

## <a name="modulegenericreleasenotifiergenericreleasenotifier"></a><a name="genericreleasenotifier-genericreleasenotifier"></a>Module:: GenericReleaseNotifier:: GenericReleaseNotifier

`Module::GenericReleaseNotifier` クラスの新しいインスタンスを初期化します。

```cpp
GenericReleaseNotifier(
   T callback,
   bool release
) throw() : ReleaseNotifier(release), callback_(callback);
```

### <a name="parameters"></a>パラメーター

*コール*<br/>
かっこ関数演算子 () を使用して呼び出すことができるラムダ、ファンクタ、またはポインターから関数へのイベントハンドラー `()` 。

*解除*<br/>
**`true`** 基になる[Module:: ReleaseNotifier:: Release ()](module-releasenotifier-class.md#releasenotifier-release)メソッドの呼び出しを有効にする場合はを指定し、それ以外の場合はを指定し **`false`** ます。

## <a name="modulegenericreleasenotifierinvoke"></a><a name="genericreleasenotifier-invoke"></a>Module:: GenericReleaseNotifier:: Invoke

現在のオブジェクトに関連付けられているイベントハンドラーを呼び出し `Module::GenericReleaseNotifier` ます。

```cpp
void Invoke();
```
