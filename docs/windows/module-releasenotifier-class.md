---
title: Module::releasenotifier クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier class
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6f720d0a918a22aee4a4cade6af1cb02a90e8d8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42588870"
---
# <a name="modulereleasenotifier-class"></a>Module::ReleaseNotifier クラス

モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。

## <a name="syntax"></a>構文

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Module::ReleaseNotifier::~ReleaseNotifier デストラクター](../windows/module-releasenotifier-tilde-releasenotifier-destructor.md)|現在のインスタンスの初期化を解除、 **module::releasenotifier**クラス。|
|[Module::ReleaseNotifier::ReleaseNotifier コンストラクター](../windows/module-releasenotifier-releasenotifier-constructor.md)|新しいインスタンスを初期化、 **module::releasenotifier**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Module::ReleaseNotifier::Invoke メソッド](../windows/module-releasenotifier-invoke-method.md)|実装された場合、モジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。|
|[Module::ReleaseNotifier::Release](../windows/module-releasenotifier-release.md)|現在の削除**module::releasenotifier**オブジェクトのパラメーターを持つオブジェクトを構築したかどうかは**true**します。|

## <a name="inheritance-hierarchy"></a>継承階層

`ReleaseNotifier`

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目
[Module クラス](../windows/module-class.md)