---
title: 式エバリュエーター エラー CXX0064 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b16133484af5a2225f79c5d293a2c8edd948bdb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025894"
---
# <a name="expression-evaluator-error-cxx0064"></a>式エバリュエーター エラー CXX0064

バインドされている仮想メンバー関数にブレークポイントを設定することはできません。

ブレークポイントがなどのオブジェクトへのポインターを介して仮想メンバー関数に設定されました。

```
pClass->vfunc( int );
```

など、クラスを入力して、仮想関数にブレークポイントを設定できます。

```
Class::vfunc( int );
```

このエラーは、can0064 と同じものと同じです。