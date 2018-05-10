---
title: C++ 組み込み演算子、優先順位と結合 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4d2bb339d4147e6ea82c713d83a046e0e9780bb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++ 組み込み演算子、優先順位と結合規則

C++ 言語には、C のすべての演算子が含まれており、いくつかの新しい演算子が追加されています。 演算子により、1 つまたは複数のオペランドに対して実行される評価が決まります。

演算子*優先順位*を複数の演算子を含む式の操作の順序を指定します。 演算子*結合規則*、優先順位が同じ複数の演算子を含む式でオペランドがグループ化するかの左側に 1 つと、右側の 1 つです。 次の表では、C++ の演算子の優先順位と結合規則を示しています (演算子は優先順位の高いものから低いものの順に並んでいます)。 優先順位番号が同じ演算子は、別の関係がかっこで明示的に適用されない限り、同じ優先順位になります。

### <a name="c-operator-precedence-and-associativity"></a>C++ 演算子の優先順位と結合規則

|演算子の説明|演算子|
|--------------------------|--------------|
|**グループ 1 の優先順位、なしの結合規則**|
|[スコープ解決演算子](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**グループ 2 の優先順位、左右の結合規則から**|
|[メンバー選択 (オブジェクトまたはポインター)](../cpp/member-access-operators-dot-and.md)|[.または ->](../cpp/member-access-operators-dot-and.md)|
|[配列の添字](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[関数呼び出し](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[後置インクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[後置デクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[型名](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[定数の型変換](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[動的な型変換](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[再解釈型変換](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[静的な型変換](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**右左結合からの 3 つの優先順位をグループ化します。**|
|[オブジェクトまたは型のサイズ](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[前置インクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[前置デクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[1 の補数](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[論理 not](../cpp/logical-negation-operator-exclpt.md)|[!](../cpp/logical-negation-operator-exclpt.md)|
|[単項マイナス符号](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[単項プラス](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[アドレスの](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[間接参照](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[オブジェクトを作成します。](../cpp/new-operator-cpp.md)|[new](../cpp/new-operator-cpp.md)|
|[オブジェクトを破棄します。](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[キャスト](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**左から右方向に 4 つの優先順位をグループ化します。**|
|[ポインター メンバーへの (オブジェクトまたはポインター)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[.&#42;または ->&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**左から右方向に 5 つの優先順位をグループ化します。**|
|[乗算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[除算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[剰余](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**左から右方向に 6 つの優先順位をグループ化します。**|
|[加算](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[減算](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**左から右方向に 7 の優先順位をグループ化します。**|
|[左シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[右シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**8 のグループの優先順位、左右の結合規則から**|
|[より小さい](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[より大きい](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[以下](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[以上](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**左から右方向に 9 の優先順位をグループ化します。**|
|[等価](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[非等価](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**左右の結合規則からグループ 10 の優先順位**|
|[ビットごとの AND](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**左から右方向に 11 の優先順位をグループ化します。**|
|[ビットごとの排他的 OR](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**左右の結合規則から 12 の優先順位をグループ化します。**|
|[ビット演算子包含的 OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**左から右方向に 13 の優先順位をグループ化します。**|
|[論理 AND](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**グループ 14 の優先順位、左右の結合規則から**|
|[論理 OR](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**右左結合からの 15 の優先順位をグループ化します。**|
|[条件付き](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**右左結合から、16 の優先順位をグループ化します。**|
|[代入](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[乗算代入](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[除算代入](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[剰余代入](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[加算代入](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[減算代入](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[左シフト代入](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[右シフト代入](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[ビットごとの AND 代入](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[ビット演算子包含的 OR 代入](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[ビット演算子排他的 OR 代入](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**右左結合から、17 の優先順位をグループ化します。**|
|[throw 式](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**左から右方向に 18 の優先順位をグループ化します。**|
|[コンマ](../cpp/comma-operator.md)|[、](../cpp/comma-operator.md)|

## <a name="see-also"></a>関連項目

[演算子のオーバーロード](operator-overloading.md)


