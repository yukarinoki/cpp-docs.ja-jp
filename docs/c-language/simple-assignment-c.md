---
title: 単純な代入 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
ms.openlocfilehash: 76c48fc6774f97bab69f916ad7e5176e91d004ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574916"
---
# <a name="simple-assignment-c"></a>単純な代入 (C)

単純な代入演算子は左オペランドに右オペランドを代入します。 右オペランドの値は、代入式の型に変換され、左オペランドで指定されたオブジェクトに格納されている値を置き換えます。 代入の変換規則が適用されます (「[代入の変換](../c-language/assignment-conversions.md)」を参照)。

```
double x;
int y;

x = y;
```

この例では、`y` の値は **double** 型に変換され、`x` に割り当てます。

## <a name="see-also"></a>参照

[C の代入演算子](../c-language/c-assignment-operators.md)