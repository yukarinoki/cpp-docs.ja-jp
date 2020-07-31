---
title: Module::MethodReleaseNotifier クラス
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
ms.openlocfilehash: 5b0e5766fda878acb1fdc54a79ce162444eb06de
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225723"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier クラス

現在のモジュールの最後のオブジェクトが解放されたときに、イベントハンドラーを呼び出します。 イベントハンドラーは、オブジェクトおよびそのポインターからメソッドへのメンバーによって指定されます。

## <a name="syntax"></a>構文

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
メンバー関数がイベントハンドラーであるオブジェクトの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                                                 | [説明]
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Module:: MethodReleaseNotifier:: MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | `Module::MethodReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                                   | [説明]
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Module:: MethodReleaseNotifier:: Invoke](#methodreleasenotifier-invoke) | 現在のオブジェクトに関連付けられているイベントハンドラーを呼び出し `Module::MethodReleaseNotifier` ます。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                                                    | [説明]
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Module:: MethodReleaseNotifier:: method_](#methodreleasenotifier-method) | 現在のオブジェクトのイベントハンドラーへのポインターを保持 `Module::MethodReleaseNotifier` します。
[Module:: MethodReleaseNotifier:: object_](#methodreleasenotifier-object) | メンバー関数が現在のオブジェクトのイベントハンドラーであるオブジェクトへのポインターを保持 `Module::MethodReleaseNotifier` します。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="modulemethodreleasenotifierinvoke"></a><a name="methodreleasenotifier-invoke"></a>Module:: MethodReleaseNotifier:: Invoke

現在のオブジェクトに関連付けられているイベントハンドラーを呼び出し `Module::MethodReleaseNotifier` ます。

```cpp
void Invoke();
```

## <a name="modulemethodreleasenotifiermethod_"></a><a name="methodreleasenotifier-method"></a>Module:: MethodReleaseNotifier:: method_

現在のオブジェクトのイベントハンドラーへのポインターを保持 `Module::MethodReleaseNotifier` します。

```cpp
void (T::* method_)();
```

## <a name="modulemethodreleasenotifiermethodreleasenotifier"></a><a name="methodreleasenotifier-methodreleasenotifier"></a>Module:: MethodReleaseNotifier:: MethodReleaseNotifier

`Module::MethodReleaseNotifier` クラスの新しいインスタンスを初期化します。

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>パラメーター

*object*<br/>
メンバー関数がイベントハンドラーであるオブジェクト。

*method*<br/>
イベントハンドラーである parameter*オブジェクト*のメンバー関数。

*解除*<br/>
**`true`** 基になる[Module:: ReleaseNotifier:: Release ()](module-releasenotifier-class.md#releasenotifier-release)メソッドの呼び出しを有効にする場合はを指定し、それ以外の場合はを指定し **`false`** ます。

## <a name="modulemethodreleasenotifierobject_"></a><a name="methodreleasenotifier-object"></a>Module:: MethodReleaseNotifier:: object_

メンバー関数が現在のオブジェクトのイベントハンドラーであるオブジェクトへのポインターを保持 `Module::MethodReleaseNotifier` します。

```cpp
T* object_;
```
