---
title: コンパイラ エラー C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: e9a4ce2276a602d59e495a2f336bb9d59dc0cc99
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200760"
---
# <a name="compiler-error-c3551"></a>コンパイラ エラー C3551

"遅延指定の戻り値の型が必要です"

関数の戻り値の型のプレース ホルダーとして `auto` キーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 次の例では、関数 `myFunction` の遅延指定の戻り値の型は、型 `int`の 4 つの要素の配列へのポインターです。

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>参照

[auto](../../cpp/auto-cpp.md)
