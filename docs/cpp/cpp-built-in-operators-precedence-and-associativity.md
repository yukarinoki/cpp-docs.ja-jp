---
description: 詳細については、C++ の組み込み演算子、優先順位、および結合規則に関するページを参照してください。
title: C++ の組み込み演算子、優先順位、および結合規則
ms.date: 07/23/2020
helpviewer_keywords:
- operators (C++), hierarchy
- operator precedence
- precedence, operators
- operators (C++), associativity
- multiple operators [C++]
- associativity of operators [C++]
- operators [C++], precedence
- evaluation order
- hierarchy, operator
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
ms.openlocfilehash: 8f45b7e45597fde1deaa349db6fd098b0d7ac319
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236765"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++ の組み込み演算子、優先順位、および結合規則

C++ 言語には、C のすべての演算子が含まれており、いくつかの新しい演算子が追加されています。 演算子により、1 つまたは複数のオペランドに対して実行される評価が決まります。

## <a name="precedence-and-associativity"></a>優先順位と結合規則

演算子の *優先順位* では、複数の演算子を含む式での演算の順序を指定します。 演算子の *結合規則* では、同じ優先順位を持つ複数の演算子を含む式で、オペランドが左側または右側の演算子でグループ化されているかどうかを指定します。

## <a name="alternative-spellings"></a>その他のスペル

C++ では、一部の演算子に対して別のスペルを指定します。 C では、代替のスペルはマクロとしてヘッダーに記載されてい \<iso646.h> ます。 C++ では、これらの代替手段はキーワードであり、またはの使用は非推奨とされ \<iso646.h> \<ciso646> ます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 代替のスペルを有効にする必要があります。

## <a name="c-operator-precedence-and-associativity-table"></a>C++ 演算子の優先順位と結合規則の表

次の表では、C++ の演算子の優先順位と結合規則を示しています (演算子は優先順位の高いものから低いものの順に並んでいます)。 優先順位番号が同じ演算子は、別の関係がかっこで明示的に適用されない限り、同じ優先順位になります。

| 演算子の説明 | 演算子 | 代替手段 |
|--|--|--|
| **グループ1の優先順位、結合規則なし** |
| [スコープの解決](../cpp/scope-resolution-operator.md) | [`::`](../cpp/scope-resolution-operator.md) |
| **グループ2の優先順位、左から右への結合規則** |
| [メンバー選択 (オブジェクトまたはポインター)](../cpp/member-access-operators-dot-and.md) | [`.` もしくは `->`](../cpp/member-access-operators-dot-and.md) |
| [配列インデックス](../cpp/subscript-operator.md) | [`[]`](../cpp/subscript-operator.md) |
| [関数呼び出し](../cpp/function-call-operator-parens.md) | [`()`](../cpp/function-call-operator-parens.md) |
| [後置インクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) | [`++`](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) |
| [後置デクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) | [`--`](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) |
| [型名](../cpp/typeid-operator.md) | [`typeid`](../cpp/typeid-operator.md) |
| [const 型変換](../cpp/const-cast-operator.md) | [`const_cast`](../cpp/const-cast-operator.md) |
| [動的型変換](../cpp/dynamic-cast-operator.md) | [`dynamic_cast`](../cpp/dynamic-cast-operator.md) |
| [再解釈型変換](../cpp/reinterpret-cast-operator.md) | [`reinterpret_cast`](../cpp/reinterpret-cast-operator.md) |
| [静的型変換](../cpp/static-cast-operator.md) | [`static_cast`](../cpp/static-cast-operator.md) |
| **グループ3の優先順位、右から左の結合規則** |
| [オブジェクトまたは型のサイズ](../cpp/sizeof-operator.md) | [`sizeof`](../cpp/sizeof-operator.md) |
| [前置インクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) | [`++`](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) |
| [前置デクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) | [`--`](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) |
| [1の補数](../cpp/one-s-complement-operator-tilde.md) | [`~`](../cpp/one-s-complement-operator-tilde.md) | **`compl`** |
| [論理 not](../cpp/logical-negation-operator-exclpt.md) | [`!`](../cpp/logical-negation-operator-exclpt.md) | **`not`** |
| [単項否定](../cpp/unary-plus-and-negation-operators-plus-and.md) | [`-`](../cpp/unary-plus-and-negation-operators-plus-and.md) |
| [単項プラス](../cpp/unary-plus-and-negation-operators-plus-and.md) | [`+`](../cpp/unary-plus-and-negation-operators-plus-and.md) |
| [アドレス--](../cpp/address-of-operator-amp.md) | [`&`](../cpp/address-of-operator-amp.md) |
| [間接](../cpp/indirection-operator-star.md) | [`*`](../cpp/indirection-operator-star.md) |
| [オブジェクトの作成](../cpp/new-operator-cpp.md) | [`new`](../cpp/new-operator-cpp.md) |
| [オブジェクトの破棄](../cpp/delete-operator-cpp.md) | [`delete`](../cpp/delete-operator-cpp.md) |
| [Cast](../cpp/cast-operator-parens.md) | [`()`](../cpp/cast-operator-parens.md) |
| **グループ4の優先順位、左から右への結合規則** |
| [メンバーへのポインター (オブジェクトまたはポインター)](../cpp/pointer-to-member-operators-dot-star-and-star.md) | [`.*` もしくは `->*`](../cpp/pointer-to-member-operators-dot-star-and-star.md) |
| **グループ5の優先順位、左から右への結合規則** |
| [数学](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`*`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| [ディビジョン](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`/`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| [剰余](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`%`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| **グループ6の優先順位、左から右の結合規則** |
| [加わっ](../cpp/additive-operators-plus-and.md) | [`+`](../cpp/additive-operators-plus-and.md) |
| [減算](../cpp/additive-operators-plus-and.md) | [`-`](../cpp/additive-operators-plus-and.md) |
| **グループ7の優先順位、左から右への結合規則** |
| [左シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md) | [`<<`](../cpp/left-shift-and-right-shift-operators-input-and-output.md) |
| [右シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md) | [`>>`](../cpp/left-shift-and-right-shift-operators-input-and-output.md) |
| **グループ8の優先順位、左から右への結合規則** |
| [次の値より小さい](../cpp/relational-operators-equal-and-equal.md) | [`<`](../cpp/relational-operators-equal-and-equal.md) |
| [より大きい](../cpp/relational-operators-equal-and-equal.md) | [`>`](../cpp/relational-operators-equal-and-equal.md) |
| [次の値以下](../cpp/relational-operators-equal-and-equal.md) | [`<=`](../cpp/relational-operators-equal-and-equal.md) |
| [次の値以上](../cpp/relational-operators-equal-and-equal.md) | [`>=`](../cpp/relational-operators-equal-and-equal.md) |
| **グループ9の優先順位、左から右への結合規則** |
| [等](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | [`==`](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) |
| [等しく](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | [`!=`](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | **`not_eq`** |
| **グループ10の優先順位が左から右の結合規則** |
| [ビット演算子 AND](../cpp/bitwise-and-operator-amp.md) | [`&`](../cpp/bitwise-and-operator-amp.md) | **`bitand`** |
| **グループ11の優先順位、左から右への結合規則** |
| [ビット演算子排他的 OR](../cpp/bitwise-exclusive-or-operator-hat.md) | [`^`](../cpp/bitwise-exclusive-or-operator-hat.md) | **`xor`** |
| **グループ12の優先順位、左から右への結合規則** |
| [ビット演算子包含的 OR](../cpp/bitwise-inclusive-or-operator-pipe.md) | [`|`](../cpp/bitwise-inclusive-or-operator-pipe.md) | **`bitor`** |
| **グループ13の優先順位、左から右への結合規則** |
| [論理積](../cpp/logical-and-operator-amp-amp.md) | [`&&`](../cpp/logical-and-operator-amp-amp.md) | **`and`** |
| **グループ14の優先順位、左から右への結合規則** |
| [論理和](../cpp/logical-or-operator-pipe-pipe.md) | [`||`](../cpp/logical-or-operator-pipe-pipe.md) | **`or`** |
| **グループ15の優先順位、右から左の結合規則** |
| [条件付き](../cpp/conditional-operator-q.md) | [`? :`](../cpp/conditional-operator-q.md) |
| [割り当て](../cpp/assignment-operators.md) | [`=`](../cpp/assignment-operators.md) |
| [乗算代入](../cpp/assignment-operators.md) | [`*=`](../cpp/assignment-operators.md) |
| [除算代入](../cpp/assignment-operators.md) | [`/=`](../cpp/assignment-operators.md) |
| [剰余代入](../cpp/assignment-operators.md) | [`%=`](../cpp/assignment-operators.md) |
| [加算代入](../cpp/assignment-operators.md) | [`+=`](../cpp/assignment-operators.md) |
| [減算代入](../cpp/assignment-operators.md) | [`-=`](../cpp/assignment-operators.md) |
| [左シフト代入](../cpp/assignment-operators.md) | [`<<=`](../cpp/assignment-operators.md) |
| [右シフト代入](../cpp/assignment-operators.md) | [`>>=`](../cpp/assignment-operators.md) |
| [ビットごとの AND 代入](../cpp/assignment-operators.md) | [`&=`](../cpp/assignment-operators.md) | **`and_eq`** |
| [ビットごとの包括的 OR 代入](../cpp/assignment-operators.md) | [`|=`](../cpp/assignment-operators.md) | **`or_eq`** |
| [ビットごとの排他的 OR 代入](../cpp/assignment-operators.md) | [`^=`](../cpp/assignment-operators.md) | **`xor_eq`** |
| [throw 式](../cpp/try-throw-and-catch-statements-cpp.md) | [`throw`](../cpp/try-throw-and-catch-statements-cpp.md) |
| **グループ16の優先順位、左から右への結合規則** |
| [コンマ](../cpp/comma-operator.md) | [,](../cpp/comma-operator.md) |

## <a name="see-also"></a>関連項目

[演算子のオーバーロード](operator-overloading.md)
