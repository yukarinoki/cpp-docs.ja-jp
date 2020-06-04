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
ms.openlocfilehash: f314d09c443d0d284e3a821b5c879bfb74baf812
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371272"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス

モジュール内の最後のオブジェクトが解放されたときに、イベント ハンドラーを呼び出します。

## <a name="syntax"></a>構文

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                                | 説明
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[モジュール::リリースNotifier::~リリースNotifier](#releasenotifier-tilde-releasenotifier) | クラスの現在のインスタンスを初期化解除`Module::ReleaseNotifier`します。
[モジュール::リリースNotifier::リリースNotifier](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                         | 説明
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[モジュール::リリースNotifier::呼び出し](#releasenotifier-invoke)   | 実装されると、モジュール内の最後のオブジェクトが解放されたときにイベント ハンドラーを呼び出します。
[Module::ReleaseNotifier::Release](#releasenotifier-release) | パラメータ true`Module::ReleaseNotifier`を指定してオブジェクトが構築されている場合は、**現在のオブジェクト**を削除します。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a>モジュール::リリースNotifier::~リリースNotifier

クラスの現在のインスタンスを初期化解除`Module::ReleaseNotifier`します。

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a>モジュール::リリースNotifier::呼び出し

実装されると、モジュール内の最後のオブジェクトが解放されたときにイベント ハンドラーを呼び出します。

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a>モジュール::リリースNotifier::リリース

パラメータ true`Module::ReleaseNotifier`を指定してオブジェクトが構築されている場合は、**現在のオブジェクト**を削除します。

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a>モジュール::リリースNotifier::リリースNotifier

`Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>パラメーター

*リリース*<br/>
`true`メソッドが呼び出されたときに`Release`このインスタンスを削除します。`false`このインスタンスを削除しないようにします。
