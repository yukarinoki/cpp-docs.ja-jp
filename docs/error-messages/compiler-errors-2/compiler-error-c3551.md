---
title: コンパイラ エラー C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 1555817de6e50ea27a021718c8b094efeaebacde
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230845"
---
# <a name="compiler-error-c3551"></a>コンパイラ エラー C3551

"遅延指定の戻り値の型が必要です"

**`auto`** 関数の戻り値の型のプレースホルダーとしてキーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 次の例では、関数の遅延指定の戻り値の型 `myFunction` は、型の4つの要素の配列へのポインターです **`int`** 。

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>関連項目

[auto](../../cpp/auto-cpp.md)
