---
title: C++ 定数式
ms.date: 11/04/2016
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
ms.openlocfilehash: 32d14650450d8047a5bc0e6cf7bb06788c9b3d81
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221758"
---
# <a name="c-constant-expressions"></a>C++ 定数式

*定数*値は、変更されないものです。 C++ には、あるオブジェクトを変更しないという意思表示をして、その意志を行使するための 2 つのキーワードが用意されています。

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
