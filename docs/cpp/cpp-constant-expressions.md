---
description: 詳細については、「C++ 定数式」を参照してください。
title: C++ 定数式
ms.date: 11/04/2016
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
ms.openlocfilehash: 9b7ca098ee5e8c41c2910f41df2031ce7320a514
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253937"
---
# <a name="c-constant-expressions"></a>C++ 定数式

*定数* 値は、変更されないものです。 C++ には、あるオブジェクトを変更しないという意思表示をして、その意志を行使するための 2 つのキーワードが用意されています。

C++ では、次の宣言に定数式 (定数に評価される式) が必要です。

- 配列の境界

- case ステートメントのセレクター

- ビット フィールドの長さの指定

- 列挙型の初期化子

定数式で有効なのは、次のオペランドのみです。

- リテラル

- 列挙定数

- 定数式で初期化され、const として宣言される値

- **`sizeof`** 式

定数式で有効にするには、非整数型の定数を (明示的または暗黙的に) 整数型に変換する必要があります。 したがって、次のコードは有効です。

```cpp
const double Size = 11.0;
char chArray[(int)Size];
```

定数式では、整数型への明示的な変換は有効です。演算子のオペランドとして使用されている場合を除き、他のすべての型と派生型は無効です **`sizeof`** 。

コンマ演算子および代入演算子は定数式では使用できません。

## <a name="see-also"></a>関連項目

[式の種類](../cpp/types-of-expressions.md)
