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
ms.openlocfilehash: c641f150b6f029facffa62f7b47c7da32138735e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371288"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier クラス

現在のモジュールの最後のオブジェクトが解放されたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、オブジェクトとそのポインターからメソッドへのメンバーによって指定されます。

## <a name="syntax"></a>構文

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
メンバー関数がイベント ハンドラーであるオブジェクトの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                                                                 | 説明
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[モジュール::メソッドリリースNotifier::メソッドリリースNotifier](#methodreleasenotifier-methodreleasenotifier) | `Module::MethodReleaseNotifier` クラスの新しいインスタンスを初期化します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                                   | 説明
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[モジュール::メソッドリリースNotifier::呼び出し](#methodreleasenotifier-invoke) | 現在`Module::MethodReleaseNotifier`のオブジェクトに関連付けられているイベント ハンドラーを呼び出します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                                                                    | 説明
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[モジュール::メソッドリリースNotifier::method_](#methodreleasenotifier-method) | 現在`Module::MethodReleaseNotifier`のオブジェクトのイベント ハンドラーへのポインターを保持します。
[モジュール::メソッドリリースNotifier::object_](#methodreleasenotifier-object) | 現在`Module::MethodReleaseNotifier`のオブジェクトのイベント ハンドラーがメンバー関数であるオブジェクトへのポインターを保持します。

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>必要条件

**ヘッダー:** モジュール.h

**名前空間:** Microsoft::WRL

## <a name="modulemethodreleasenotifierinvoke"></a><a name="methodreleasenotifier-invoke"></a>モジュール::メソッドリリースNotifier::呼び出し

現在`Module::MethodReleaseNotifier`のオブジェクトに関連付けられているイベント ハンドラーを呼び出します。

```cpp
void Invoke();
```

## <a name="modulemethodreleasenotifiermethod_"></a><a name="methodreleasenotifier-method"></a>モジュール::メソッドリリースNotifier::method_

現在`Module::MethodReleaseNotifier`のオブジェクトのイベント ハンドラーへのポインターを保持します。

```cpp
void (T::* method_)();
```

## <a name="modulemethodreleasenotifiermethodreleasenotifier"></a><a name="methodreleasenotifier-methodreleasenotifier"></a>モジュール::メソッドリリースNotifier::メソッドリリースNotifier

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

*オブジェクト*<br/>
メンバー関数がイベント ハンドラーであるオブジェクト。

*method*<br/>
イベント ハンドラーであるパラメーター*オブジェクト*のメンバー関数。

*リリース*<br/>
基`true`になるモジュールの呼び出しを有効にすることを指定します: [:リリースNotifier::Release()](module-releasenotifier-class.md#releasenotifier-release)メソッド;それ以外の`false`場合は、 を指定します。

## <a name="modulemethodreleasenotifierobject_"></a><a name="methodreleasenotifier-object"></a>モジュール::メソッドリリースNotifier::object_

現在`Module::MethodReleaseNotifier`のオブジェクトのイベント ハンドラーがメンバー関数であるオブジェクトへのポインターを保持します。

```cpp
T* object_;
```
