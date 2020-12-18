---
description: '詳細情報: 単純な代入 (C)'
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
ms.openlocfilehash: bf8637268c810ed6a75095774ca6ff7b7d3d9e67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229900"
---
# <a name="simple-assignment-c"></a>単純な代入 (C)

単純な代入演算子は左オペランドに右オペランドを代入します。 右オペランドの値は、代入式の型に変換され、左オペランドで指定されたオブジェクトに格納されている値を置き換えます。 代入の変換規則が適用されます (「[代入の変換](../c-language/assignment-conversions.md)」を参照)。

```
double x;
int y;

x = y;
```

この例では、`y` の値は **`double`** 型に変換され、`x` に代入されます。

## <a name="see-also"></a>関連項目

[C の代入演算子](../c-language/c-assignment-operators.md)
