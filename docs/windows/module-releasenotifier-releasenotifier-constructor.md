---
title: Module::ReleaseNotifier::ReleaseNotifier コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- ReleaseNotifier, constructor
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e43abd46ccfb150936ff435360611289f18a1270
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405022"
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Module::ReleaseNotifier::ReleaseNotifier コンストラクター

新しいインスタンスを初期化、 **module::releasenotifier**クラス。

## <a name="syntax"></a>構文

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>パラメーター

*release*<br/>
**true**を削除するインスタンスこれ、`Release`メソッドが呼び出されます。**false**をこのインスタンスを削除できません。

## <a name="exceptions"></a>例外

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module::ReleaseNotifier クラス](../windows/module-releasenotifier-class.md)