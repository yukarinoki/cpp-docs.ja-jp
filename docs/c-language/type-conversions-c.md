---
title: 型変換 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 606ff0197f73a697aa3dad3bea779de80b060705
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020837"
---
# <a name="type-conversions-c"></a>型変換 (C)

型変換は、指定された演算子と、オペランドまたは演算子の型に依存します。 次の場合に型変換が実行されます。

- ある型の値が異なる型の変数に代入されるとき、または演算子が演算を実行する前にオペランドの型を変換するとき

- ある型の値が異なる型に明示的にキャストされるとき

- 値が関数に引数として渡されるとき、または型が関数から戻されるとき

文字、短整数、整数ビット フィールド (符号付きと符号なし)、または列挙型のオブジェクトは、整数が使用できる場所であれば式内のどこででも使用できます。 `int` が元の型のすべての値を表すことができる場合、値は `int` に変換されます。それ以外の場合は `unsigned int` に変換されます。 このプロセスを "整数の上位変換" といいます。 整数の上位変換では値が保持されます。 つまり、上位変換後の値が上位変換前と同じであることが保証されます。 詳細については、「[通常の算術変換](../c-language/usual-arithmetic-conversions.md)」をご覧ください。

## <a name="see-also"></a>参照

[式と代入](../c-language/expressions-and-assignments.md)