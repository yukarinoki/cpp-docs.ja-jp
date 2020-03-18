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
ms.openlocfilehash: 5fc1b8965bf8bf2f86dd30f2195fa825f85f6d7e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423628"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス

モジュール内の最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。

## <a name="syntax"></a>構文

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

Name                                                                                | Description
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module:: ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | `Module::ReleaseNotifier` クラスの現在のインスタンスを初期化解除します。
[Module:: ReleaseNotifier:: ReleaseNotifier](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

Name                                                         | Description
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module:: ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | 実装された場合、モジュール内の最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。
[Module::ReleaseNotifier::Release](#releasenotifier-release) | パラメーターを**true**にしてオブジェクトが構築された場合、現在の `Module::ReleaseNotifier` オブジェクトを削除します。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Module:: ReleaseNotifier:: ~ ReleaseNotifier

`Module::ReleaseNotifier` クラスの現在のインスタンスを初期化解除します。

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Module:: ReleaseNotifier:: Invoke

実装された場合、モジュール内の最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。

```cpp
virtual void Invoke() = 0;
```

## <a name="releasenotifier-release"></a>Module:: ReleaseNotifier:: Release

パラメーターを**true**にしてオブジェクトが構築された場合、現在の `Module::ReleaseNotifier` オブジェクトを削除します。

```cpp
void Release() throw();
```

## <a name="releasenotifier-releasenotifier"></a>Module:: ReleaseNotifier:: ReleaseNotifier

`Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>パラメーター

*release*<br/>
`Release` メソッドが呼び出されたときに、このインスタンスを削除する `true` ます。このインスタンスを削除しないように `false` します。
