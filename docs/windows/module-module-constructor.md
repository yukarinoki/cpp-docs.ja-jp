---
title: Module::module コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e96e6cf984196cbca3051eec397ae06e48e2f1c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406660"
---
# <a name="modulemodule-constructor"></a>Module::Module コンストラクター

新しいインスタンスを初期化、**モジュール**クラス。

## <a name="syntax"></a>構文

```cpp
Module();
```

## <a name="remarks"></a>Remarks

このコンス トラクターは保護され、ということはできません、**新しい**キーワード。 代わりに、いずれかを呼び出す[module::getmodule メソッド](../windows/module-getmodule-method.md)または[module::create メソッド](../windows/module-create-method.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Module クラス](../windows/module-class.md)