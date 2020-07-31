---
title: 単項演算子を含む式
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
ms.openlocfilehash: 032ebd99041de9308d16710b2a27e0db3cddd4df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233757"
---
# <a name="expressions-with-unary-operators"></a>単項演算子を含む式

単項演算子は、式の中で 1 つのオペランドに対してのみ作用します。 単項演算子は、次のとおりです。

- [間接演算子 (*)](../cpp/indirection-operator-star.md)

- [アドレス演算子 (&)](../cpp/address-of-operator-amp.md)

- [単項プラス演算子 (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [単項否定演算子 (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [論理否定演算子 (!)](../cpp/logical-negation-operator-exclpt.md)

- [1の補数演算子 (~)](../cpp/one-s-complement-operator-tilde.md)

- [前置インクリメント演算子 (++)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [前置デクリメント演算子 (--)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Cast 演算子 ()](../cpp/cast-operator-parens.md)

- [`sizeof`operator](../cpp/sizeof-operator.md)

- [`__uuidof`operator](../cpp/uuidof-operator.md)

- [`alignof`operator](../cpp/alignof-operator.md)

- [`new`operator](../cpp/new-operator-cpp.md)

- [`delete`operator](../cpp/delete-operator-cpp.md)

これらの演算子の結合規則は、右から左方向です。 単項式は構文では一般に後置式または 1 次式より優先されます。

以下は単項式の可能な形式です。

- *postfix-expression*

- `++` *unary-expression*

- `--` *unary-expression*

- *単項演算子*の*キャスト式*

- **`sizeof`***単項式*

- `sizeof(`*型名*`)`

- `decltype(` *式 (expression)* `)`

- *割り当て-式*

- *割り当て解除-式*

*後置式*は*単項式*と見なされ、任意のプライマリ式は*後置式*と見なされるため、すべてのプライマリ式は*単項式*と見なされます。 詳細については、「[後置式](../cpp/postfix-expressions.md)と[プライマリ式](../cpp/primary-expressions.md)」を参照してください。

*単項演算子*は、次の1つ以上の記号で構成されます。`* & + - ! ~`

*キャスト式*は、型を変更するためのオプションのキャストを含む単項式です。 詳細については、「 [Cast 演算子: ()](../cpp/cast-operator-parens.md)」を参照してください。

*式*には、任意の式を指定できます。 詳細については、「[式](../cpp/expressions-cpp.md)」を参照してください。

*割り当て式*は演算子を参照し **`new`** ます。 *割り当て解除式*は演算子を参照し **`delete`** ます。 詳細については、このトピックで前述したリンクを参照してください。

## <a name="see-also"></a>関連項目

[式の種類](../cpp/types-of-expressions.md)
