---
title: C++組み込み演算子、優先順位、および結合規則
ms.date: 11/04/2016
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
ms.openlocfilehash: 36e7ce77e24366be10b75f5bb4f8830363594301
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180408"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++組み込み演算子、優先順位、および結合規則

C++ 言語には、C のすべての演算子が含まれており、いくつかの新しい演算子が追加されています。 演算子により、1 つまたは複数のオペランドに対して実行される評価が決まります。

演算子の*優先順位*では、複数の演算子を含む式での演算の順序を指定します。 演算子の*結合規則*では、同じ優先順位を持つ複数の演算子を含む式で、オペランドが左側または右側の演算子でグループ化されているかどうかを指定します。 次の表では、C++ の演算子の優先順位と結合規則を示しています (演算子は優先順位の高いものから低いものの順に並んでいます)。 優先順位番号が同じ演算子は、別の関係がかっこで明示的に適用されない限り、同じ優先順位になります。

### <a name="c-operator-precedence-and-associativity"></a>C++ 演算子の優先順位と結合規則

|演算子の説明|演算子|
|--------------------------|--------------|
|**グループ1の優先順位、結合規則なし**|
|[スコープの解決](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**グループ2の優先順位、左から右への結合規則**|
|[メンバーの選択 (オブジェクトまたはポインター)](../cpp/member-access-operators-dot-and.md)|[.または->](../cpp/member-access-operators-dot-and.md)|
|[配列の添字](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[関数呼び出し](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[後置インクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[後置デクリメント](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[型名](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[定数型の変換](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[動的な型変換](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[解釈された型変換](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[静的な型変換](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**グループ3の優先順位、右から左の結合規則**|
|[オブジェクトまたは型のサイズ](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[前置インクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[前置デクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[1の補数](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[論理 not](../cpp/logical-negation-operator-exclpt.md)|[!](../cpp/logical-negation-operator-exclpt.md)|
|[単項マイナス符号](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[単項プラス](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[アドレス--](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[演算](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[オブジェクトの作成](../cpp/new-operator-cpp.md)|[新規](../cpp/new-operator-cpp.md)|
|[オブジェクトの破棄](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[CAST](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**グループ4の優先順位、左から右への結合規則**|
|[メンバーへのポインター (オブジェクトまたはポインター)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[.&#42;または->&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**グループ5の優先順位、左から右への結合規則**|
|[乗算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[除算](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[剰余](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**グループ6の優先順位、左から右の結合規則**|
|[加算](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[減算](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**グループ7の優先順位、左から右への結合規則**|
|[左シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[右シフト](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**グループ8の優先順位、左から右への結合規則**|
|[より小さい](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[より大きい](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[以下](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[以上](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**グループ9の優先順位、左から右への結合規則**|
|[等価](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[非等価](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**グループ10の優先順位が左から右の結合規則**|
|[ビットごとの AND](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**グループ11の優先順位、左から右への結合規則**|
|[ビットごとの排他的 OR](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**グループ12の優先順位、左から右への結合規則**|
|[ビットごとの包括的 OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**グループ13の優先順位、左から右への結合規則**|
|[論理積](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**グループ14の優先順位、左から右への結合規則**|
|[論理和](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**グループ15の優先順位、右から左の結合規則**|
|[付](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**グループ16の優先順位、右から左の結合規則**|
|[割り当て](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[乗算代入](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[除算代入](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[剰余代入](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[加算代入](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[減算代入](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[左シフト代入](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[右シフト代入](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[ビットごとの AND 代入](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[ビットごとの包括的 OR 代入](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[ビットごとの排他的 OR 代入](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**グループ17の優先順位、右から左の結合規則**|
|[throw 式](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**グループ18の優先順位、左から右への結合規則**|
|[コンマ](../cpp/comma-operator.md)|[、](../cpp/comma-operator.md)|

## <a name="see-also"></a>参照

[演算子のオーバーロード](operator-overloading.md)
