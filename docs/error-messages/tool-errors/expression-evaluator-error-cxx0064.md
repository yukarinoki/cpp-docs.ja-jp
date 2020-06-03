---
title: 式エバリュエーター エラー CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: f763754299ed9257fb909b49a7a19c6f3ad58681
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184464"
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
