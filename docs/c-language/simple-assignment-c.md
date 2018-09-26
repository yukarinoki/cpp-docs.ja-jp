---
title: 単純な代入 (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff4e032e205680da84369075514e3177fa5fb33e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051023"
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