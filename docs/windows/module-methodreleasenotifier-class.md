---
title: Module::methodreleasenotifier クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cee634ab62e699b4de6af54a57b0fe3d6b5e9a40
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606609"
---
# <a name="modulemethodreleasenotifier-class"></a>Module::MethodReleaseNotifier クラス

現在のモジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、オブジェクトとそのメソッドへのポインター メンバーによって指定されます。

## <a name="syntax"></a>構文

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>パラメーター

*T*  
メンバー関数は、イベント ハンドラー オブジェクトの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Module::MethodReleaseNotifier::MethodReleaseNotifier コンストラクター](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|新しいインスタンスを初期化、 **module::methodreleasenotifier**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Module::MethodReleaseNotifier::Invoke メソッド](../windows/module-methodreleasenotifier-invoke-method.md)|現在関連付けられているイベント ハンドラーを呼び出す**module::methodreleasenotifier**オブジェクト。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|name|説明|
|----------|-----------------|
|[Module::MethodReleaseNotifier::method_ データ メンバー](../windows/module-methodreleasenotifier-method-data-member.md)|現在のイベント ハンドラーへのポインターを保持**module::methodreleasenotifier**オブジェクト。|
|[Module::MethodReleaseNotifier::object_ データ メンバー](../windows/module-methodreleasenotifier-object-data-member.md)|メンバー関数は、現在のイベント ハンドラー オブジェクトへのポインターを保持**module::methodreleasenotifier**オブジェクト。|

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[Module クラス](../windows/module-class.md)