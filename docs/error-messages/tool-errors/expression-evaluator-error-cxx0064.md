---
description: 詳細については、「式エバリュエーターエラー CXX0064」を参照してください。
title: 式エバリュエーター エラー CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: 58356a48fc52ee479c92cf5d65494763c3fc4adb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173195"
---
# <a name="expression-evaluator-error-cxx0064"></a>式エバリュエーター エラー CXX0064

バインドされた仮想メンバー関数にブレークポイントを設定できません

次のようなオブジェクトへのポインターを使用して、仮想メンバー関数にブレークポイントが設定されました。

```
pClass->vfunc( int );
```

ブレークポイントは、次のようなクラスを入力することによって、仮想関数に設定できます。

```
Class::vfunc( int );
```

このエラーは CAN0064 と同じです。
