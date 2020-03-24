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
ms.openlocfilehash: 60444ee3c55df39e6b7820ff9b9d7ad81017b0da
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188494"
---
# <a name="overloading-unary-operators"></a>単項演算子のオーバーロード

オーバーロードできる単項演算子は次のとおりです。

1. `!` ([論理 NOT](../cpp/logical-negation-operator-exclpt.md))

1. `&` ([アドレス/](../cpp/address-of-operator-amp.md))

1. `~` ([1 の補数](../cpp/one-s-complement-operator-tilde.md))

1. `*` ([ポインターの逆参照](../cpp/indirection-operator-star.md))

1. `+` ([単項プラス](../cpp/additive-operators-plus-and.md))

1. `-` ([単項否定](../cpp/additive-operators-plus-and.md))

1. `++` ([インクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. `--` ([デクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

9. 変換演算子

後置インクリメント演算子とデクリメント演算子 (`++` および `--`) は、[インクリメントとデクリメント](../cpp/increment-and-decrement-operator-overloading-cpp.md)で個別に処理されます。

変換演算子については、別のトピックでも説明します。「[ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)」を参照してください。

次の規則は他のすべての単項演算子に適用されます。 単項演算子関数を非静的メンバーとして宣言するには、次の形式で宣言する必要があります。

> *ret* **演算子** *op* **()**

ここで、 *ret 型*は戻り値の型、 *op*は前の表に示した演算子の1つです。

単項演算子関数をグローバル関数として宣言するには、次の形式で宣言する必要があります。

> *ret* **operator** *op* **(** *arg* **)**

ここで、 *ret 型*と*op*はメンバー演算子関数について説明されています。 *arg*は、操作対象のクラス型の引数です。

> [!NOTE]
>  単項演算子の戻り値の型に制限はありません。 たとえば、論理 NOT (`!`) が整数値を返すのは正しい使い方ですが、強制ではありません。

## <a name="see-also"></a>参照

[演算子のオーバーロード](../cpp/operator-overloading.md)
