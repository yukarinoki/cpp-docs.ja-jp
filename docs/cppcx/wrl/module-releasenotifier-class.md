---
title: Module::ReleaseNotifier クラス
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: 25fbb23ee7ecb7e55377aed74effe8bfa43a1597
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218365"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス

モジュール内の最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。

## <a name="syntax"></a>構文

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                                | 説明
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module:: ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | クラスの現在のインスタンスを初期化解除 `Module::ReleaseNotifier` します。
[Module:: ReleaseNotifier:: ReleaseNotifier](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                         | 説明
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module:: ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | 実装された場合、モジュール内の最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。
[Module::ReleaseNotifier::Release](#releasenotifier-release) | `Module::ReleaseNotifier`オブジェクトがのパラメーターを使用して構築されている場合、現在のオブジェクトを削除し **`true`** ます。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a>Module:: ReleaseNotifier:: ~ ReleaseNotifier

クラスの現在のインスタンスを初期化解除 `Module::ReleaseNotifier` します。

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a>Module:: ReleaseNotifier:: Invoke

実装された場合、モジュール内の最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a>Module:: ReleaseNotifier:: Release

`Module::ReleaseNotifier`オブジェクトがのパラメーターを使用して構築されている場合、現在のオブジェクトを削除し **`true`** ます。

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a>Module:: ReleaseNotifier:: ReleaseNotifier

`Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>パラメーター

*解除*<br/>
**`true`** メソッドが呼び出されたときにこのインスタンスを削除する場合 `Release` は。 **`false`** このインスタンスを削除しない場合は。
