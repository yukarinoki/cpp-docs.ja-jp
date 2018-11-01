---
title: コンパイラ エラー C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 9dfdee155e85bd772ed1d4ce22c525f8a4c79f5c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458748"
---
# <a name="compiler-error-c3551"></a>コンパイラ エラー C3551

"遅延指定の戻り値の型が必要です"

関数の戻り値の型のプレース ホルダーとして `auto` キーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 次の例では、関数 `myFunction` の遅延指定の戻り値の型は、型 `int`の 4 つの要素の配列へのポインターです。

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>関連項目

[auto](../../cpp/auto-cpp.md)