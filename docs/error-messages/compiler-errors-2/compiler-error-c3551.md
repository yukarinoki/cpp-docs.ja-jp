---
description: 詳細については、「コンパイラエラー C3551」を参照してください。
title: コンパイラ エラー C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 813d483b696d0829f05108a35e5731f93f6004ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223270"
---
# <a name="compiler-error-c3551"></a>コンパイラ エラー C3551

"遅延指定の戻り値の型が必要です"

**`auto`** 関数の戻り値の型のプレースホルダーとしてキーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 次の例では、関数の遅延指定の戻り値の型 `myFunction` は、型の4つの要素の配列へのポインターです **`int`** 。

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>関連項目

[auto](../../cpp/auto-cpp.md)
