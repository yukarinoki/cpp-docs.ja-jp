---
title: Module::releasenotifier クラス |Microsoft Docs
ms.custom: ''
ms.date: 09/17/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c9af03549eec7b62cc34aec2840764c54d2a21e
ms.sourcegitcommit: 338e1ddc2f3869d92ba4b73599d35374cf1d5b69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494362"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス

モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。

## <a name="syntax"></a>構文

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                                | 説明
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Module::releasenotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | 現在のインスタンスの初期化を解除、`Module::ReleaseNotifier`クラス。
[Module::ReleaseNotifier::ReleaseNotifier](#releasenotifier-releasenotifier)        | `Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                         | 説明
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Module::releasenotifier:: 呼び出し](#releasenotifier-invoke)   | 実装された場合、モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。
[Module::ReleaseNotifier::Release](#releasenotifier-release) | 現在の削除`Module::ReleaseNotifier`オブジェクトのパラメーターを持つオブジェクトを構築したかどうかは`true`します。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="releasenotifier-tilde-releasenotifier"></a>Module::releasenotifier:: ~ ReleaseNotifier

現在のインスタンスの初期化を解除、`Module::ReleaseNotifier`クラス。

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="releasenotifier-invoke"></a>Module::releasenotifier:: 呼び出し

実装された場合、モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。

```cpp
virtual void Invoke() = 0;
```

## <a name="releasenotifier-release"></a>Module::ReleaseNotifier::Release

現在の削除`Module::ReleaseNotifier`オブジェクトのパラメーターを持つオブジェクトを構築したかどうかは`true`します。

```cpp
void Release() throw();
```

## <a name="releasenotifier-releasenotifier"></a>Module::ReleaseNotifier::ReleaseNotifier

`Module::ReleaseNotifier` クラスの新しいインスタンスを初期化します。

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>パラメーター

*release*  
`true` 削除するインスタンスこれ、`Release`メソッドが呼び出されます。`false`をこのインスタンスを削除できません。
