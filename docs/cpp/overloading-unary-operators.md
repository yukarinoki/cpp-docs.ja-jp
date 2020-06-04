---
title: 単項演算子のオーバーロード
ms.date: 11/04/2016
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
ms.openlocfilehash: 971ef08c5e79f851c502ea872c541517065797c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372028"
---
# <a name="overloading-unary-operators"></a>単項演算子のオーバーロード

オーバーロードできる単項演算子は次のとおりです。

1. `!`([論理式ではない](../cpp/logical-negation-operator-exclpt.md))

1. `&`([アドレスの )](../cpp/address-of-operator-amp.md)

1. `~`([補数](../cpp/one-s-complement-operator-tilde.md))

1. `*`([ポインタ逆参照](../cpp/indirection-operator-star.md))

1. `+`([単項プラス](../cpp/additive-operators-plus-and.md))

1. `-`([単項否定](../cpp/additive-operators-plus-and.md))

1. `++`([増分](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. `--`([デクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. 変換演算子

後置インクリメント演算子とデクリメント`++`演算子`--`( および ) は、[増分と減分](../cpp/increment-and-decrement-operator-overloading-cpp.md)で別々に扱われます。

変換演算子については、別のトピックでも説明します。[「ユーザー定義型変換](../cpp/user-defined-type-conversions-cpp.md)」を参照してください。

次の規則は他のすべての単項演算子に適用されます。 単項演算子関数を非静的メンバーとして宣言するには、次の形式で宣言する必要があります。

> *ret型***演算子** *op* **()**

ここで*ret-type*は戻り値の型で *、op*は前の表に示した演算子の 1 つです。

単項演算子関数をグローバル関数として宣言するには、次の形式で宣言する必要があります。

> *ret 型***演算子** *op* **(** *arg* **)**

ここで*ret-type*と*op*はメンバー演算子関数に対して記述されているとおりであり *、 arg*は操作するクラス型の引数です。

> [!NOTE]
> 単項演算子の戻り値の型に制限はありません。 たとえば、論理 NOT (`!`) が整数値を返すのは正しい使い方ですが、強制ではありません。

## <a name="see-also"></a>関連項目

[演算子のオーバーロード](../cpp/operator-overloading.md)
