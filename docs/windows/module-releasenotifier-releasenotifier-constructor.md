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
ms.openlocfilehash: f4ab2d5d03516147acda38ea2133d7445695de80
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598789"
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Module::ReleaseNotifier::ReleaseNotifier コンストラクター

新しいインスタンスを初期化、 **module::releasenotifier**クラス。

## <a name="syntax"></a>構文

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>パラメーター

*release*  
**true**を削除するインスタンスこれ、`Release`メソッドが呼び出されます。**false**をこのインスタンスを削除できません。

## <a name="exceptions"></a>例外

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module::ReleaseNotifier クラス](../windows/module-releasenotifier-class.md)